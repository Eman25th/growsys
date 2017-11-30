# growsys
This project's focus is to produce and record accurite enviroment readings for each grow room. In turn the data will be used to adjust
and keep the room enviroment ideal for growth and to compare to past Harvest to fine tune growing methods.

Raspberry Pi 3 units with Humidity and temp sensors, connecting via wifi, reporting back to a host SQL database, Host then providing
webpage interface to view current and past readings, as well as Watchdog alerts for when a rooms readings are outside its limits.








________________________
Setup for adding a new Unit, 

	1. Change Device name, Pass, timezone, allow SSH, config Wifi & static IP
	2. Sudo apt-get update       Sudo apt-get upgrade
	3. sudo apt-get install build-essential python-dev python-openssl
	4. sudo apt-get install mysql-server python-mysqldb
	5. git clone https://github.com/adafruit/Adafruit_Python_DHT.git
	6. cd Adafruit_Python_DHT
	7. sudo python setup.py install
	8. cd /home/pi/Adafruit_Python_DHT/examples
	9. sudo ./AdafruitDHT.py 22 4
	10. sudo rm -r DHT22-TemperatureLogger/
	11. Create MySQL table for unit/room
	12. Edit DHT22logger.py & Config.json
	13. Upload to git and git clone https://github.com/Eman25th/growsys.git
	14. Crontab -e      */60 * * * * python /home/pi/growsys/DHT22logger.py
	15. Cp Room.php and edit on Unit01
________________________

If SQL host is down, restart service// sudo service mysql restart




