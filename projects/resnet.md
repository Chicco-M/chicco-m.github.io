---
layout: project
type: project
image: img/resnet/resnet-square.png
title: "ResNet Service Monitor"
date: 2025
published: true
labels:
  - Python
  - Raspberry Pi
  - Linux
  - REST API
summary: "A Raspberry Pi that turns open ResNet service requests into physical LED indicators so nothing sits in the queue unnoticed."
---

<div class="text-center p-4">
  <img width="200px" src="../img/resnet/resnet-pi.png" class="img-thumbnail" >
  <img width="200px" src="../img/resnet/resnet-lamps.png" class="img-thumbnail" >
  <img width="200px" src="../img/resnet/resnet-terminal.png" class="img-thumbnail" >
</div>

ResNet is the team that keeps wired and wireless service running in UH Mānoa's student housing. Requests come in through the Pilikia ticketing system, and as a Support Specialist my job was to notice them and act. In practice that meant a browser tab I refreshed between tasks, which is a poor way to catch the one ticket that says a whole floor has no internet.

So I built a Raspberry Pi that watches the queue for me. On an interval it authenticates to the ticketing API, pulls the open requests, and counts them by status. Each status maps to a physical indicator on the desk: a new request lights one lamp, a request waiting on a user lights another, an escalated request lights a third. Walk into the office and the state of the queue is visible before anyone logs in.

<hr>

The indicators are not wired to GPIO. They are ordinary USB lamps plugged into a powered hub, and the Pi controls them with [uhubctl](https://github.com/mvp/uhubctl), which toggles power to individual hub ports over the command line. The whole control layer is one function:

<pre>
def set_port(port, state):
    subprocess.run(
        ["uhubctl", "-l", HUB, "-p", str(port), "-a", state],
        check=True, capture_output=True,
    )

def refresh(session):
    counts = poll_status(session)

    for status, port in PORT_MAP.items():
        desired = "on" if counts.get(status, 0) &gt; 0 else "off"
        set_port(port, desired)

    return counts
</pre>

The script runs as a systemd service, so it survives reboots and restarts itself if the API times out. Failed polls leave the lamps in their last known state and log the error rather than blanking everything, which would look identical to an empty queue.

<hr>

The tradeoff is that USB power switching is slower and coarser than GPIO. You get on and off, nothing in between, and a port takes a moment to settle after toggling. In exchange, adding an indicator means plugging in another lamp and adding a line to <code>PORT_MAP</code>, with no soldering and nothing to break when the desk gets rearranged.

Source: <a href="https://github.com/chicco-m/resnet-monitor"><i class="large github icon "></i>chicco-m/resnet-monitor</a>
