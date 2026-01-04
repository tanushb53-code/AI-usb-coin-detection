# AI-usb-coin-detection
This project is an ai object detection project that is designed for to detect coins and other circle object, this has been tested and will be again tested in FLL first lego league innovation project.
      This project uses and imac, a usb camera, and a rapsberry pi 4 or 5.
          You can use any usb camera and any imac and mac book that is not very old.
The command to start the notification system on imac or macbook is 
pip3 install flask
python3 imessage_server.py
and for the raspberry pi it is 
1️⃣ Update system
sudo apt update
sudo apt upgrade -y

2️⃣ Install system dependencies
sudo apt install -y python3 python3-pip python3-venv git v4l-utils

3️⃣ Create Python virtual environment
python3 -m venv ~/myenv

4️⃣ Activate virtual environment
source ~/myenv/bin/activate

5️⃣ Install Python packages
pip install --upgrade pip
pip install opencv-python pillow numpy requests flask

6️⃣ Verify camera exists
ls /dev/video*


(Optional test)

v4l2-ctl --list-devices

7️⃣ Create the Python file
nano ~/coin_gui.py


(Paste the Pi code you already have → save → exit)

8️⃣ Run the program
python3 ~/coin_gui.py

9️⃣ Stop the program
CTRL + C


or close the GUI window

🔟 If camera index fails

Edit:

nano ~/coin_gui.py


Change:

CAMERA_INDEX = 0


to:

CAMERA_INDEX = 1


Save → Exit → Run again:

python3 ~/coin_gui.py

1️⃣1️⃣ Test snapshot file
ls -lh /home/pi/artifact_snapshot.jpg

1️⃣2️⃣ Test message upload to Mac
curl -X POST http://MAC_IP:5000/send \
  -F phone="+15555555555" \
  -F text="TEST ARTIFACT" \
  -F image=@/home/pi/artifact_snapshot.jpg

1️⃣3️⃣ Auto-start on boot (optional)
crontab -e


Add:

@reboot source /home/pi/myenv/bin/activate && python3 /home/pi/coin_gui.py


Save → Exit

1️⃣4️⃣ Check logs (if auto-start)
journalctl -xe

1️⃣5️⃣ Deactivate environment
deactivate

