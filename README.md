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

## Campaign
![Camp1](https://user-images.githubusercontent.com/32926005/195973708-820906e3-21df-4aee-b843-c3d144bbde33.PNG)
![Camp2](https://user-images.githubusercontent.com/32926005/195973783-41891340-963e-46f6-b2d6-8784608e7b58.PNG)
![Camp3](https://user-images.githubusercontent.com/32926005/195973875-0a6e9f42-dd09-4990-b378-37f330fda05d.PNG)
![Camp4](https://user-images.githubusercontent.com/32926005/195973930-e65f2b8e-6d33-4819-ae7c-c40680c410fb.PNG)
