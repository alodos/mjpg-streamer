mjpg-streamer
=============

Install mjpg-streamer as service with Init Script LSB (Linux Standard Base).


Install
=======

1. Install mjpg-streamer with cmake (see documentation).

2. Copy init script (need sudo):

	cp mjpg-streamer-experimental/scripts/mjpg_streamer.init /etc/init.d/mjpg_streamer
	chmod +x /etc/init.d/mjpg_streamer
	update-rc.d mjpg_streamer defaults


Usage
=====

	service mjpg_streamer {start [device] | stop | status | restart [device] | force-reload [device] }


Examples
========

1. Start stream all connected and supported by v4l video devices:

	service mjpg_streamer start

2. Stream only selected video devices:

	service mjpg_streamer start /dev/video0 /dev/video1

3. Restart with only selected devices 

	service mjpg_streamer restart /dev/video1

4. Stop

	service mjpg_streamer stop

5. Status (shows process pid and command line is started)

	service mjpg_streamer status
