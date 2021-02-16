# SecretMessage

Hello Hackers. 
----
My Challenge name is : *SecretMessage*
The challenge is not difficult, It is at the Mediuem level
..It appears that there is a public account "guest"
We will enter the chat page And check the source code

<img src="https://raw.githubusercontent.com/CaesarEG0x01/SecretMessage/main/Screenshot%20at%202021-02-17%2003-41-34.png">

````
<iframe src="chatroom/312/index.php" style="width: 555px;height: 630px;border: aliceblue;"></iframe>
````

<img src="https://raw.githubusercontent.com/CaesarEG0x01/SecretMessage/main/Screenshot%20at%202021-02-17%2003-41-48.png">

Some chat rooms store their messages in txt files instead of using databases and it is possible that one of these files has a secret message that can be accessed by the public 

<img src="https://raw.githubusercontent.com/CaesarEG0x01/SecretMessage/main/Screenshot%20at%202021-02-17%2003-42-24.png">

````
[03:12:56] 200 - 1018B  - /challenge/ctf2/chatroom/312/files/
````

Using the dirsearch tool
we aple to found this directory and Directory Listing is enabled 

>chatroom/312/files/messages/312-18674-448187.txt

The first message was sent in that chat room at a time

>Tuesday, February 16, 2021 11:11:21 PM

Now let's look in more depth at the name of the file that contains the messages
The first part is the room number, which can only have 3 numbers `312`
The second part is the timestamp number in weeks
The third part is the timestamp number in hours

As indicated in the comment, the flag was sent a day before this message
We will only adjust the timestamp from the following site 
*Convert from date to timestamp*
> https://www.timestampconvert.com/

We will put the date of the first message, but we will only reduce one day
from `Tuesday, February 16, 2021 11:11:21 PM` to `Tuesday, February 15, 2021 11:11:21 PM`
<img src="https://raw.githubusercontent.com/CaesarEG0x01/SecretMessage/main/Screenshot%20at%202021-02-17%2003-42-45.png">

>chatroom/312/files/messages/312-18674-448173.txt

It is clear that the secret message is not found in this room
The room number consists of numbers only that can be easily guessed 
I have reached this room number`430`
and try to read this file 

>chatroom/430/files/messages/430-18674-448173.txt

i get ‘403 forbidden’ message ,you can bypass it
type this command: 
>curl -H "Content-Length:0" -X POST http://127.0.0.1/challenge/ctf2/chatroom/430/files/messages/430-18673-448163.txt

Response

<img src="https://raw.githubusercontent.com/CaesarEG0x01/SecretMessage/main/Screenshot%20at%202021-02-17%2003-50-32.png">

Flag : Flag{3T0r3d_1nt0_PubTXT}
