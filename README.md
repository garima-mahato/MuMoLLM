# MuMoLLM
## Multi-Modal LLM for Chat GPT like Conversations

<div align="center" background-color="#8bd4e2">
    <h1 align="center"><a href="https://github.com/garima-mahato/MuMoLLM"><img src="https://raw.githubusercontent.com/garima-mahato/MuMoLLM/main/images/mumo_logo.png", alt="MuMo" border="0" style="margin: 0 auto; height: 200px;" /></a> </h1>
    <h2 align="center"> MuMo: Multi-Modal Chatter </h2>
    <h5 align="center"> If you like this project, please give a star ✨ on Github.  </h2>
    <h5 align="center"> Note: This version is not multilingual demo </h5>
    <div align="center">
        <div style="display:flex; gap: 0.25rem;" align="center">
            <a href='https://github.com/garima-mahato/MuMoLLM'><img src='https://img.shields.io/badge/Github-Code-blue'></a>
            <a href='https://github.com/garima-mahato/MuMoLLM/stargazers'><img src='https://img.shields.io/github/stars/garima-mahato/MuMoLLM.svg?style=social'></a>
            <a href='https://www.youtube.com/watch?v=0DCZLFmnV0s'><img src='https://img.shields.io/badge/youtube-badge'></a>
        </div>
    </div>
</div>
**Notice**: This runs on CPU and may take time in responding.

**We recommend only one image or video per conversation session.** 

If you want to start chatting with new images or videos, we recommend you to **CLEAR** the history to restart.

### Demo

[![](https://img.youtube.com/vi/0DCZLFmnV0s/0.jpg)](https://www.youtube.com/watch?v=0DCZLFmnV0s)


#### Input

##### 1) Context

> Text

> Audio

##### 2) Query

It is in text format

#### Output

Text

#### Model Description

Microsoft PHI2 model fine-tuned using QLORA is used.

The text context and text query are conactenated to form the text input. Text input is tokenized and then passed into this model to generate the answer. 

For audio input, whisperx model is used to transcribe the audio and get it in text format. This becomes the context. The query is taken from the user's next input in text format. The transcribed context text and query are contaneated to form the input text. Then, the same tokenizer, which was used for text input, is used for tokenizing the audio input. It is then passed to the PHI2 model to generate the answer.


#### Model Preparation

<b>PHI2 model fine-tuned using QLORA: Training Logs</b>

```
Step	Training Loss	Validation Loss
20	1.363600	1.701620
40	1.843700	1.677984
60	1.264700	1.680656
80	1.765800	1.663594
100	1.971700	1.672795
120	1.296200	1.659232
140	1.847100	1.648250
160	1.416500	1.651985
180	1.668800	1.643360
200	2.137700	1.657212
220	1.535600	1.648161
240	2.002000	1.640604
260	1.396000	1.647849
280	1.507700	1.639951
300	2.042600	1.642382
320	1.272600	1.645164
340	1.756600	1.636030
360	1.387000	1.643319
380	1.356700	1.637331
400	1.982500	1.640031
420	1.317300	1.640891
440	2.018100	1.631911
460	1.315400	1.643280
480	1.916700	1.631127
500	1.924300	1.640074
520	1.380500	1.638371
540	1.918100	1.632293
560	1.423600	1.639958
580	1.586600	1.632348
600	1.775900	1.635792
620	1.342800	1.635416
640	2.149800	1.628864
660	1.502400	1.637784
680	1.454000	1.630546
700	1.849300	1.635679
720	1.333400	1.639243
740	2.124600	1.628558
760	1.440700	1.632220
780	2.009900	1.629111
800	1.863200	1.637265
820	1.709900	1.631767
840	1.905100	1.624500
860	1.490100	1.633971
880	1.719300	1.626777
900	1.884900	1.630145
920	1.243200	1.631118
940	1.971700	1.622210
960	1.428400	1.629166
980	1.536600	1.627812
1000	1.811100	1.626576
1020	1.393900	1.637368
1040	1.801800	1.621389
1060	1.374300	1.628027
1080	1.728000	1.621455
1100	2.003300	1.629665
1120	1.345300	1.631998
1140	1.822400	1.623145
1160	1.329400	1.636522
1180	1.753300	1.622677
1200	1.664100	1.632285
1220	1.197200	1.629850
1240	1.987700	1.620458
1260	1.264500	1.628843
1280	1.395100	1.622678
1300	1.724800	1.626827
1320	1.543500	1.625276
1340	1.701800	1.620305
1360	1.384100	1.629156
1380	1.665900	1.622334
1400	1.574500	1.625185
1420	1.316800	1.629336
1440	2.032300	1.621219
1460	1.268400	1.628253
1480	1.719200	1.619434
1500	1.825700	1.629663
1520	1.187200	1.631416
1540	1.911900	1.619950
1560	1.326500	1.630483
1580	1.882000	1.621072
1600	1.994400	1.623250
1620	1.291400	1.623419
1640	2.021800	1.620903
1660	1.519400	1.635250
1680	1.495100	1.624114
1700	2.333600	1.630782
1720	1.446400	1.626262
1740	2.040700	1.619685
1760	1.527800	1.625534
1780	1.554200	1.622531
1800	2.002600	1.625943
1820	1.668500	1.622014
1840	1.764400	1.620637
1860	1.113000	1.622640
1880	1.453800	1.619375
1900	2.011300	1.626575
1920	1.511200	1.622729
1940	1.824300	1.617798
1960	1.646700	1.619327
```


## What could have been done better?

1) Better model and infrastructure for training and deployment
