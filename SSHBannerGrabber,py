#This was developed with the help of the one and only patlopes, so check his GitHub: https://github.com/patlopes
#Here's a banner grabber for SSH that we've made to solve the Looking Glass TryHackMe Room 

import subprocess
from threading import Thread

INI_PORT = int(input("set initial port")) #The starting port
FIN_PORT = int(input("set final port port")) #The ending port 

def Grab_Banner(INI_PORT): 
    proc = subprocess.Popen(["ssh alice@10.10.44.81 -p {0} -o \"StrictHostKeyChecking no\"".format(str(INI_PORT))], stdout=subprocess.PIPE, shell=True)
    (out, err) = proc.communicate()
    with open('loginglass.txt',"a") as f:
        f.write ("program output:"+ out + str(INI_PORT) + "\n")

for INI_PORT in range(INI_PORT,FIN_PORT,1): 
    thread = Thread(target = Grab_Banner, args = (INI_PORT, ))
    thread.start()
    


