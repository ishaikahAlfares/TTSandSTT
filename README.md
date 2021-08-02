# speech to text 
* install pyaudio and websocket-client.
* add the api key and the region of your speech to text service in speech.cfg file.
* in order to save the final text detected in a txt file i added this code to on_message method: 
    FinalTranscripts= data['results'][0]['alternatives'][0]['transcript']
        file = open("Output.txt","w")
        Transcripts_String = repr(FinalTranscripts)
        file.write("FinalTranscripts ="+Transcripts_String +"\n")
        file.colse()
        
# text to speech
* install ibm_watson and ibm_cloud_sdk_core.
* add the api key and api url of you text to speech service in variables.
* import TextToSpeechV1 and IAMAuthenticator.
* write this code to convert any text to audio and save it in the desired destination:
   with open('./speech1.mp3','wb') as audio_file:
    res=tts.synthesize('hello world', accept='audio/mp3',voice='en-US_AllisonV3Voice').get_result()
    audio_file.write(res.content)
