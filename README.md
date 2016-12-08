# Computer-Security
8 Код для клиента и сервера, реализующий скрытый поток по времени с помощью сокетов
Сервер:
#!/usr/bin/python

import socket
import time

m='H'
s=''
m.lower()
print 'lol'
for i in m:
	s=s+(bin(ord(i)))
s=s.replace('0b','')
print (s)
timestart = time.clock()

for i in s:
	if i:		
		print time.clock()		
		sock=socket.socket(socket.AF_INET, 	socket.SOCK_STREAM)		
		sock.bind(('localhost', 9012))
		sock.listen(1)
		time.sleep(2)
		sock.close()
		
	else:
		time.sleep(2)
socker=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
socker.bind(('localhost', 6012))
socker.listen(1)
time.sleep(3)
socker.close()

Клиент:
#!/usr/bin/python

import socket
import time

s=''
print (s)
timestart = time.clock()
i=7
while i:
	try:
		sock=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
		sock.bind(('localhost', 9012))
		f=5		
	except:	
		f=6
	if (f==5):
		sock.close()
		time.sleep(2)
		s=s+'0'
		print 'v'		
	else:
		s=s+'1'
		time.sleep(2)
		print (i)
		print time.clock()
	try:
		socker=socket.socket(socket.AF_INET, socket.SOCK_STREAM)
		socker.bind(('localhost', 6012))
		socker.close()
		continue
	except:
		break
	i-=1
print(s)
