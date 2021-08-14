# Converting Speech to Text and Speech to Text using IBM Watson Assistant and Python




## 1. Open - [IBM Watson Assistant from here](https://cloud.ibm.com/catalog), then create your account if you don't have, if you already have one please login:




![image](https://user-images.githubusercontent.com/46464413/129443362-f6439f0a-1453-4daa-9dd4-89ab141b85f0.png)



## 2. Get your Credentials:


![image](https://user-images.githubusercontent.com/46464413/129443392-11e25c53-1359-4743-b069-0a8b9aa73c3c.png)




## 3. Clone IBM Watson Streaming STT Project:
For this step I used Pycharm IDE and created a new project, then I used its terminal to run this following code which clones the github project files into my pycharm project:

```
git clone https://github.com/IBM/watson-streaming-stt
```

![image](https://user-images.githubusercontent.com/46464413/129443839-9ecc8a3a-8ee4-4b81-a737-127ec082a426.png)



## 4. Install Dependencies:
Running this project requires specific packages written in (requirements.txt) file so use the following line of code to download then from the requirements file:

```
pip install pipwin
```

![image](https://user-images.githubusercontent.com/46464413/129443906-8a264da8-8ace-448b-8f00-513cb6a294c1.png)


```
pipwin install pyaudio
```

![image](https://user-images.githubusercontent.com/46464413/129443924-caa13d2f-897b-47fb-a6e8-50ef57a59ee0.png)



## 5. Update Region & API key:
In your cloned project, go to line number 2 in (speech.cfg) file, erase the old API and replace it with your own (the ones you got from step 2):

![image](https://user-images.githubusercontent.com/46464413/129443949-cdfef34f-bd45-4712-bfb0-fa9f8c1f248c.png)


![image](https://user-images.githubusercontent.com/46464413/129443960-eaef60d4-b37e-4c60-ac53-33499700d82a.png)


Then, go to line number 186 in (transcribe.py) file and erase the old region and replace it with your own (the ones you got from step 2):
you can git your region model [from here](https://cloud.ibm.com/docs/speech-to-text?topic=speech-to-text-models)
![image](https://user-images.githubusercontent.com/46464413/129444013-ba7ad88f-330f-43d8-a29b-20b4a48e498b.png)





## 6. Speech To Text File:
In the following lines of code I started by creating a text file named (STT.txt) followed by the function 'write' which writes the text content into the text file, and finally closing the file, and the text file will be found with the rest of the project files after running the code:

```
fo = open('STT.txt', 'w')
fo.write(transcript)
fo.close()
```

![image](https://user-images.githubusercontent.com/46464413/129444041-c5888e53-09a1-4a99-991e-45afd6281b65.png)




## 7. Text To Speeh (TTS):

In the step we want to convert our text into an audio using the following code lines, I started by creating passing the text into gTTS function which will convert the text into the audio file and then save it under the name (TTS.mp3) and the mp3 file will be found with the rest of the project files after running the code:


```
output = gTTS(text=transcript, lang='en', slow=False)
output.save("TTS.mp3")
```

![image](https://user-images.githubusercontent.com/46464413/129444055-36ed9c85-b639-4019-83d4-81d7490c89ab.png)



## 8. Run The Code:
Now that everything is ready we will run the code using the following command where we use -t to specify how long we want to record (ex: 20 sec)
Note: mke sure you are in the correct directory otherwise use (cd ./watson-streaming-stt) 

```
python transcribe.py -t 20
```


## 9. SPEECH:
As i run the program i started speaking and the program started showing my speech in the terminal, and it showed a correct result as i was saying (hello how are you what are languages you can speak what is your name how old are you)


https://user-images.githubusercontent.com/46464413/129444700-335fdff7-f694-43a7-8d80-5e6860e6f199.mp4




## 10. MP3 FILE:
After running the program it converted the output text automatically into mp3 file as you can hear in this video:


https://user-images.githubusercontent.com/46464413/129444865-a2cdeebf-3c72-49d0-a327-bd856b98d7df.mp4





## 11. TEXT FILE:
After running the program it converted my final speech automatically into a text file 

![image](https://user-images.githubusercontent.com/46464413/129444750-704777f5-483f-42af-8c08-9c1922e6dc52.png)

