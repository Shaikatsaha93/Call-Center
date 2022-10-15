# Call-Center
## Carriers
### Registration String:
```
register => 09678771660:iptstest@203.76.96.85:5060/09678771660
```
### Account Entry:
```
[link3sip]
type=friend
username=09678771660
secret=iptstest
host=203.76.96.85
dtmfmode=rfc2833
dtmf=rfc2833
context=trunkinbound
insecure=invite,port
canreinvite=no
nat=yes
qualify=yes
disallow=all
allow=ulaw
allow=alaw
```
### Globals String:
```
TESTSIPTRUNK= SIP/link3sip
```
### Dialplan Entry:	
```
exten => _9X.,1,AGI(agi://127.0.0.1:4577/call_log)
exten => _9X.,2,SET(CALLERID(number)=09678771660)
exten => _9X.,3,Dial(${TESTSIPTRUNK}/${EXTEN:1},,tToR)
exten => _9X.,4,Hangup
```
### Final Sample
![Carriers](https://user-images.githubusercontent.com/32926005/195973031-bfca85d1-6b0a-4766-83e8-7f2539df19f5.PNG)
