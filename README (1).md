# Evaluation of our Text to Speech Conversion Model

1)-Our Text to Speech conversion model comprises multiple models.

        1. Tacotron2 + MELGAN
        2. Tacotron2 + MELGAN+STFT
        3. Tacotron2 + MB-MELGAN
        4. Fastspeech + MB-MELGAN
        5. Fastspeech + MELGAN+STFT
        6. Fastspeech + MELGAN
        7. Fastspeech2 + MB-MELGAN
        8. Fastspeech2 + MELGAN+STFT
        9. Fastspeech 2 + MELGAN
        10. Google TTS
        11. Pyttsx
        12. Coqui Studio API

2)-Our models from model no.1 to mode.no9 are trained on the LJ dataset that is the voice of a single speaker who is female and we have
natural voice only in that case which makes it suitable for evaluation through MCD(Mel cepstral distortions) lower the MCD more the

synthesized speech closer to natural. For these models their MCD score and computation time are as follows:-
```
input_text = "The examination and testimony of the experts enabled the Commission to conclude
```
that five shots may have been fired,"


- Tacotron2 + MELGAN
```
o MCD score Tacotron2 + MELGAN= 16.
o Inference Time: 7.588048696517944 seconds
```
- Tacotron2 + MELGAN+STFT
```
o MCD score Tacotron2 + MELGAN-STFT= 16.
o Inference Time: 7.6723668575286865 seconds
```
- Tacotron2 + MB-MELGAN
```
o MCD score Tacotron2 + MB-MELGAN= 16.
o Inference Time: 7.249122381210327 seconds
```
- Fastspeech + MB-MELGAN
```
o MCD score FastSpeech + MB-MELGAN= 17.
o Inference Time: 1.4219391345977783 seconds
```
- Fastspeech + MELGAN+STFT
```
o MCD score FastSpeech + MELGAN-STFT= 17.
o Inference Time: 2.3506431579589844 seconds
```
- Fastspeech + MELGAN
```
o MCD score FastSpeech + MELGAN= 17.
o Inference Time: 3.2196388244628906 seconds
```
- Fastspeech2 + MB- MELGAN
```
o MCD score FastSpeech2 + MB-MELGAN= 11.
o Inference Time: 1.818901777267456 seconds
```
- Fastspeech2 + MELGAN-STFT
```
o MCD score FastSpeech2 + MELGAN-STFT= 11.
o Inference Time: 2.7945449352264404 seconds
```
- Fastspeech 2 + MELGAN
```
o MCD score FastSpeech2 + MELGAN= 11.
o Inference Time: 4.471189022064209 seconds
```
3)-Now for model no 10 GTTS we are only able to compute inference time
```
input_text = "The examination and testimony of the experts enabled the Commission to conclude
that five shots may have been fired,"
```
```
Inference Time: 0.35593628883361816 seconds
```
4)- Our Pyttsx3 is a library offer by python for text to speech conversion unlike other library it is available offline and offers output in 2
voices one is male and other one is female (speaker id=1 for male and speaker id= for female) so result for same input test are:-


- Male(id=0)

```
o Duration: 7.9760544217687075 seconds
o RMS (Volume): 0.
o Pitch: 122.
```

- Female(id=1)

```
o Duration: 8.298730158730159 seconds
o RMS (Volume): 0.
o Pitch: 125.
```
5)-Model no-11 comprises linguistic features implies it allows us to vary voices and languages. In total, it consists of 6 speakers in first 3 are
females, and rest are males for different speakers we measure 3 important parameters i.e pitch, volume or loudness, and duration for the
same input text are as follows:-
```
input_text ="Hello world!"
```
```
speaker0(F) : {'Pitch': 234.67723497146613, 'RMS (Volume)': 0.1620834, 'Duration': 1.489}
speaker1(F) : {'Pitch': 211.29828424349833, 'RMS (Volume)': 0.15190306, 'Duration': 1.633}
speaker2(F) : {'Pitch': 221.42887603911174, 'RMS (Volume)': 0.17056428, 'Duration': 1.489}
speaker3(M) : {'Pitch': 225.1808022728022, 'RMS (Volume)': 0.12335953, 'Duration': 1.297}
speaker4(M) : {'Pitch': 218.12079430504508, 'RMS (Volume)': 0.12076642, 'Duration': 1.329}
speaker5(M) : {'Pitch': 228.9117699312734, 'RMS (Volume)': 0.16833502, 'Duration': 1.185}
```

