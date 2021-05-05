#PY GO
#AI Python Assistant
import pyaudio
import pyttsx3
import speech_recognition as sr
import webbrowser
import os
import datetime
Assistant = pyttsx3.init('sapi5')
voices = Assistant.getProperty("voices")
Assistant.setProperty('voices',voices[0].id)
def Speak(audio):
    print("   ")
    Assistant.say(audio)
    print("   ")
    Assistant.runAndWait()
    return
def takecommand():
    command = sr.Recognizer()
    with sr.Microphone() as source:
        print("Listening...")
        command.pause_threshold = 1
        audio = command.listen(source)

        try:
            print("Recognizing...")
            query = command.recognize_google(audio,language='en-in')
            print(f"You Said : {query}")

        except Exception as Error:
            return "none"

        return query.lower()
    

Speak("Hello User. I am Robin. How may I help you?")
query = takecommand()
if 'open google' in query:
        os.startfile("C:\Program Files\Google\Chrome\Application\chrome.exe")

elif 'open edge' in query:
    os.startfile("C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe")

elif 'open youtube' in query:
    webbrowser.open("https://www.youtube.com/")

elif 'open amazon' in query:
    webbrowser.open("https://www.amazon.in/")
elif 'open hotstar' in query:
    webbrowser.open("https://www.hotstar.com/in")
elif 'open flower' in query:
    webbrowser.open("https://www.hotstar.com/in/movies/flubber/1260018196/watch")
elif 'open github' in query:
    webbrowser.open("https://github.com/")
elif 'open mail' in query:
    webbrowser.open("https://mail.google.com/mail/u/1/#inbox")
elif 'open hangouts' in query:
    webbrowser.open("https://hangouts.google.com/?authuser=1")
elif 'open facebook' in query:
    webbrowser.open("https://www.facebook.com/")
elif 'song one' in query:
    webbrowser.open("https://gaana.com/song/woh-din-arijit-singh-version")
elif 'how are you' in query:
    Speak("I am good.")
elif '123' in query:
    print(datetime.time())
elif 'greet me' in query:
    Speak("I compute to serve you my user.")
elif 'open twitter' in query:
    webbrowser.open("https://twitter.com/")

