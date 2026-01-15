<img width="30%" src="https://github.com/user-attachments/assets/fb3076b9-f236-4315-8e74-741df752898b" />
<br/>

# Task1

<img width="30%" src="https://github.com/user-attachments/assets/04fe1760-5b70-49e9-9f6d-2d60b2d8f964">
<br/>
> Hint : Scan the host with nmap.
How many TCP ports are open?<br/>

해당 IP에 열린 포트가 있는지 확인하기 위해 nmap명령어를 사용한다<br/>
<br/>

```
nmap -p- -sV 10.10.10.245
```

-p- : 모든 포트를 스캔<br/>
-sV : 어떤 서비스인지, 어떤 버전인지 확인<br/>
너무 오래 걸리는 관계로 옵션을 바꾼다<br/>

<img width="30%" src="https://github.com/user-attachments/assets/71f142c6-d93d-42dc-abc7-fbf759f4af52">
```
nmap -p- -sS -sV --min-rate 5000 10.10.10.245
```
<br/>
-p- : 모든 포트를 스캔<br/>
-sS : SYN스캔<br/>
-sV : 어떤 서비스인지, 어떤 버전인지 확인<br/>
--min-rate 5000 : 초당 5,000패킷 보냄<br/>
위 명령어로 포트를 확인하니 열려있는 포트들의 개수를 확인할 수 있음<br/>

## flag

3
<br/>
<br/>
<br/>

# Task2

<img width="30%" src="https://github.com/user-attachments/assets/548695f5-505a-4dee-8d8c-cca2aad27a98">
<br/>
> Hint : Run a scan and look at the URL of the page you are redirected to. This part is the same every time.
After running a "Security Snapshot", the browser is redirected to a path of the format /[something]/[id], where [id] represents the id number of the scan. What is the [something]?<br/>

가상 환경에서 firefox로 10.10.10.245로 접속한다<br/>
<img width="30%" src="https://github.com/user-attachments/assets/72a8fd39-d551-4ca7-b902-5553f085b447">
Dashboard에서 Security Snapshot 화면에 가면 경로를 볼 수 있다<br/>

## flag

data
<br/>
<br/>
<br/>

# Task3

<img width="30%" src="https://github.com/user-attachments/assets/a7c58e58-bc52-465d-a9ec-5852d0bbaf71">
<br/>
> Hint : Try modifying the URL and see what happens. You could also fuzz with a tool like ffuf or wfuzz.
Are you able to get to other users' scans?<br/>

yes or no 문제라서 하나씩 해보면 되긴 한다.<br/>
하지만 Security Snapshot 화면에서 경로를 조작할 수 있어서 yes다<br/>

## flag

yes
<br/>
<br/>
<br/>

# Task4

<img width="30%" src="https://github.com/user-attachments/assets/4be825e9-e301-4b08-8d3c-7175894a43ee">
<br/>
> Hint : Download PCAP files and take a look.
What is the ID of the PCAP file that contains sensative data?<br/>
