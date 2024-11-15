---
layout: default
title: Using robot "offline"
description: How to configure the robot not to use OpenCore ( "offline" mode )
parent: What Is OpenRPA
nav_order: 6
---
## "Offline" mode

OpenRPA was made to work in tandem with OpenCore, but it can work in a standalone mode where it does not need to be connected to an OpenCore instance, but then you loose all the benefits from OpenCore.

Make sure the robot is not running, then open the file settings.json inside "Documents\OpenRPA"

Find the wsurl property and remove the current URL

![image-20200328100940556](offline/image-20200328100940556.png)

So it looks like this

![image-20200328101114001](offline/image-20200328101114001.png)

Be aware, if you re add an URL here, you need to manually import all workflows and detectors, so, create a copy of the OpenRPA folder after adding the URL and then import each workflow and detector from that folder