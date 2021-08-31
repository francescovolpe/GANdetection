# GANdetection
GANdetection è un'applicazione in grado di distinguere volti di persone reali da volti creati attraverso le GAN.


#### Abstract
*I modelli generativi, come le GAN (generative adversarial network), sono ora in grado
di produrre immagini di elevata qualità tanto da poter trarre in inganno persino gli esseri
umani. Diversi metodi e modelli sono stati proposti negli ultimi anni, ma molti di essi
non sono in grado di generalizzare su architetture e dataset provenienti da sorgenti
sconosciute. In questo lavoro ci si è chiesto se fosse possibile costruire un rilevatore
universale che potesse distinguere immagini reali di volti umani da immagini generate
tramite GAN. Per raggiungere questo obiettivo sono stati costruiti dei modelli
utilizzando il dataset di una sola rete generativa avversaria e un dataset di immagini
reali. Viene dimostrato che, utilizzando immagini di una GAN con una diversa
variazione del “trucco del troncamento”, aumenta notevolmente la capacità di
generalizzazione dei modelli. I risultati ottenuti suggeriscono che molte GAN ad oggi
condividono gli stessi difetti che possono essere rilevati per consentire la distinzione di
immagini reali da immagini sintetiche.*


## Sperimentazione
I dataset di addestramento, validazione e valutazione sono stati pre-processati con il [face detect](https://github.com/francescovolpe/GANdetection/blob/main/Face_detect.ipynb) e successivamente [ridimensionati a 160x160](https://github.com/francescovolpe/GANdetection/blob/main/Resize_images.ipynb).
Composizione del dataset per l'addestramento e la validazione.
| Fake        | #F | Real           | #R |
| ------------- |-------------|-------------|-------------|
| StyleGAN  (CAHQ) 0.5    | 18.777 | CAHQ | 26.824 |
| StyleGAN  (CAHQ) 0.7    | 2.682 | 
| StyleGAN  (CAHQ) 1.0    | 5.365 | 

## Dataset
I dataset di addestramento, validazione e valutazione sono reperibili dal seguente [repository](https://github.com/francescovolpe/Dataset-GANdetection)

## Accuratezza modello
| Fake | StyleGAN (CAHQ) | Glow | ProGAN | StyleGAN 2 (FFHQ) | DiscoFaceGAN | FaceAPP DFFD |
| ------------- |-------------|-------------|-------------|------------- |-------------|-------------|
|  |99.6 | 56.2 | 99.1 | 98.8 | 99.9 | 99.4 |

| Real | CAHQ | FFHQ | CelebA | LFW | UTKFace |
| ------------- |-------------|-------------|-------------|------------- |------------- |
| | 100 | 2.9 | 100 | 100 | 99.7 |


## Test

1. [Scarica il modello](https://drive.google.com/file/d/1o7ApG_QclqaDDFuP0Rp2YefTuxCeJHsc/view?usp=sharing)
2. Preprocessa il dataset da valutare con il [face-detect](https://github.com/francescovolpe/GANdetection/blob/main/Face_detect.ipynb)
3. [Ridiminensiona](https://github.com/francescovolpe/GANdetection/blob/main/Resize_images.ipynb) a 160x160 (bicubic) il dataset preprocessato con il face detect
4. Esegui il notebook [Test.ipynb](https://github.com/francescovolpe/GANdetection/blob/main/Test.ipynb) modificando il percorso del dataset da valutare


## Librerie utilizzate
Si raccomanda l'uso di [Goole Colab](https://colab.research.google.com/)
- tensorflow 2.4.1
- keras 2.4.0
- numpy 1.19.5
- matplotlib 3.2.2
- face-recognition 1.2.3
- pillow 8.0.0

## Problemi visualizzazione notebook
Se riscontri problemi nella visualizzazione dei notebook a causa del rendering, puoi utilizzare [nbviewer](https://nbviewer.jupyter.org/)
