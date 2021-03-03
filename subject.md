# How to create J.A.R.V.I.S

## Description

You've already heard about the famous artificial intelligent **J.A.R.V.I.S** in
the film Iron-man.

Today in this workshop you will learn how to recreate this artificial intelligence.

All this will be done on the Windows 10 platform with python and some other modules.

## Step 1

For the begining, you need to use the module : **pyttsx3** to computer talk.

    >>> pip install pyttsx3


## Step 2

For the second step, you need to use **datetime** module to get the 
time and the day of today.

    >>> pip install datetime

And with *pyttsx3* say it.

## Step 3

Now, one of the most important part you need that Jarvis recognize your voice
we need modules : **pipwin**, **pyaudio** et
**speechrocognition**.

    >>> pip install pipwin
    >>> pipwin install pyaudio
    >>> pip install speechrocognition

You create a fonction that recognize your voice and print or just let 
Jarvis say it.

## Step Bonus

In this bonus step you need to orgonize your code like that with the **main** 
fonction:

    #!/bin/python3
    import pyttsx3
    import datetime
    import speech_recognition as sr

    # La fontion qui permet de parler
    def speak(audio):
        engine = pyttsx3.init()
        engine.say(audio)
        engine.runAndWait()

    # La fonction qui donne l'heure
    def timeh():
    h = datetime.datetime.now().strftime('%I:%M')
    hour = int(datetime.datetime.now().hour)
    speak(h)
    if (hour >= 0 and hour <= 12):
        speak("du matin")
    else:
        speak("de l'aprem")
    
    # La fonction qui donne la date
    def date():
    year = int(datetime.datetime.now().year)
    month = int(datetime.datetime.now().month)
    dayn = int(datetime.datetime.now().day)

    speak(dayn)
    speak(month)
    speak(year)

    # Une petite fonction de salution
    def helloh():
    speak("Salut on est le ")
    date()
    speak('a')
    time()

    # La fonction qui permet de récupérer la voix
    def rec_voice():
        r = sr.Recognizer()

        with sr.Microphone() as source:
            speak("Donnez moi un ordre ...")
            r.pause_threshold = 1
            r.energy_threshold = 5400
            voice = r.listen(source)
            # Avec tout sa sa vas nous permettre de recupérer notre voix
        try:
            request = r.recognize_google(voice, language='fr-FR')
            print(request)
        except Exception as e:
            print(e)
            speak("Je n'ai pas compris votre demande reformulez la ...")
            return 'None'
        return request
    
    # La fonction principale
    def main():
    helloh()

    while True:
        request = rec_voice().lower()
        # Ce if chercher si dans request il y a heure
        if ("heure" in request):
            timeh()
        elif ("date" in req):
            date()
        elif ("fermer" in req):
            exit()
    
    # Ici on définie la fonction principal qui est le main
    if (__name == "__main__"):
        main()

Voià maintenant que votre code est réorganiser on vas pouvoir passer 
a la suite.

## Step 4

In this step we go to research in wikipedia with the module name: **wikipedia**.
When you talk with jarvis and you say : "wikipedia bill gates", you need 
to transform your string in lowercase and delete the word 
"wikipedia" and resume bill gates, for exemple,in 2 sentence.


I hope you're still here and if so we'll move on.

## Step 5

Now an easy step with the module : **webbroser**, we go in your default application
web broser and you say to jarvis you want to open a website like "twitter.com"
tt opens a new tab in twitter.com, for exempl

## Step 6

Another easy step with the module **os**, you need to tell at Jarvis that you want to shutdown,
lock or reboot your computer.

Another easy step, isn't it?

## Step 7


One more easy step, don't worry, we will play music from a folder always with the : **os** module.
I let you do that.


## Step 8

Now we will learn how to create a note and make *Jarvis* read it.

As you can see here we already have a predefined file. But after having how 
to paste 2 strings together
but also put them back in the string. You can go further and give Jarvis the 
file you want to write to and read from.

## Step 9

It's been a long time we haven't installed a new module good for this part you'll need : **pyautogui**.

    >>> pip install pyautogui

With this module and in this part we will be able to make screenshots.

## Step 10

We are finally at the last stage and this stage consists in having the information
of the battery but also of the processor.

Therefore, a new module which is : **psutil**.

    >>> pip install psutil

# BONUS

Congratulations to you for getting here. You finally have time to fix your code. 
and yes it makes a lot of elif that you have there!

I can suggest you other things to do if you want to go further with Jarvis:
* Allow Jarvis to send an email to anyone she wants.
* Make HTTP requests on the Epitech intranet to either subscribe to a 
activities, get your schedule back etc ...
* You can also analyze the security on your computer like firewalls etc...

Basically you have infinite possibilities, Your Jarvis will remain your Jarvis if you leave. 
at the end of the thing

Thank you for following me throughout this workshop and I look forward to seeing you again.