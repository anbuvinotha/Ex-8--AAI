# EX-08 Implementation of Speech Recognition
### Aim:
To implement the conversion of live speech to text.
### Description:
Speech recognition is a technology that converts spoken language into text, enabling hands-free interactions with devices. It powers virtual assistants, transcription tools, and accessibility applications by interpreting words from audio input.
### Algorithm:
**Step 1**: Import the `speech_recognition` library.  
**Step 2**: Initialize the Recognizer.  
**Step 3**: Create an instance of the Recognizer class, which will be used for recognizing speech.  
**Step 4**: Set the duration for audio capture.  
**Step 5**: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.  
**Step 6**: Display a message in the console to prompt the user to speak.  
**Step 7**: Capture audio from the default microphone.  
**Step 8**: Use the default microphone as the audio source.  
**Step 9**: Record audio for the specified duration using the Recognizer instance.  
**Step 10**: Perform speech recognition with exception handling:  
   - Attempt to recognize speech from the captured audio using the Google Speech Recognition service.  
   - If successful, print the recognized text.  
   - Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.  
   - A generic exception block captures any other unexpected errors.  
<table>
<tr>
<td width=40%>
  
### Program:
**Developed By: ROSELIN MARY JOVITA S - 212222230122**
```Python
import speech_recognition as sr
import pyaudio
def record_audio():
    r=sr.Recognizer()
    r.energy_threshold = 6000
    voicedata=''
    try:
        with sr.Microphone() as source:
            audio=r.listen(source)
            voicedata=r.recognize_google(audio)            
    except sr.UnknownValueError:
        print("Unable to Recognize Audio")
    except sr.RequestError:
        print("Unable to find the Resource")
    return voicedata
while True:
    print("Say Something ....")
    text=record_audio()
    print(text)
    if text=="stop" or text=="close" or text=="exit":
        exit(1)
```

</td> 
<td>

### Output:


![Screenshot 2024-11-15 130146](https://github.com/user-attachments/assets/720625d1-b94a-481d-ae86-90c56717d993)



</td>
</tr> 
</table>

### Result:
Thus, we have implemented a program that will transcribe the audio file in the file variable and print the transcribed text on the console, one line at a time.<br>

