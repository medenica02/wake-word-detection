# Wake Word Detection

## Opis projekta

Projekat iz predmeta **Računarska inteligencija** čiji je cilj detekcija aktivacione reči (*wake word*) „stop“ korišćenjem metoda mašinskog učenja i dubokih neuronskih mreža.

U okviru projekta analizirane su dve reprezentacije audio signala:

- MFCC (Mel-Frequency Cepstral Coefficients)
- LFCC (Linear Frequency Cepstral Coefficients)

Za obe reprezentacije izdvojene su karakteristike iz audio zapisa, nakon čega je trenirana konvoluciona neuronska mreža (CNN) za zadatak binarne klasifikacije:

- 1 – prisutna ključna reč „stop“
- 0 – odsustvo ključne reči

Cilj projekta bio je poređenje uspešnosti MFCC i LFCC reprezentacija u zadatku detekcije aktivacione reči.

## Korišćene tehnologije

- Python
- PyTorch
- Torchaudio
- Librosa
- NumPy
- Scikit-Learn
- Matplotlib
- Jupyter Notebook

## Arhitektura modela

Model se sastoji od:

- tri konvoluciona sloja
- Batch Normalization slojeva
- ReLU aktivacionih funkcija
- MaxPooling slojeva
- Adaptive Average Pooling sloja
- Dropout sloja
- dva potpuno povezana (Fully Connected) sloja
- izlaznog linearnog sloja sa jednim logitom za binarnu klasifikaciju

Za optimizaciju je korišćen Adam optimizer, dok je funkcija gubitka Binary Cross Entropy (BCEWithLogitsLoss).

## Evaluacija

Performanse modela procenjivane su korišćenjem sledećih metrika:

- Accuracy
- Precision
- Recall
- F1-score
- ROC kriva i AUC
- Precision–Recall kriva i Average Precision (AP)

## Rezultati

### MFCC model

| Metrika | Vrednost |
|----------|----------|
| Accuracy | 99.45% |
| Precision | 0.98 |
| Recall | 0.94 |
| F1-score | 0.96 |
| ROC AUC | 0.9954 |
| AP | 0.9592 |

### LFCC model

| Metrika | Vrednost |
|----------|----------|
| Accuracy | 98.41% |
| Precision | 0.93 |
| Recall | 0.83 |
| F1-score | 0.87 |
| ROC AUC | 0.9776 |
| AP | 0.8284 |

## Poređenje MFCC i LFCC pristupa

Dobijeni rezultati pokazuju da je MFCC reprezentacija ostvarila bolje performanse u zadatku detekcije aktivacione reči „stop“. MFCC model postiže više vrednosti precision, recall i F1-score metrike, kao i veću površinu ispod ROC i Precision–Recall krive.

LFCC model je takođe ostvario veoma dobre rezultate, ali je pokazao veću sklonost propuštanju pozitivnih primera, što se ogleda u nižoj recall vrednosti. Razlog tome je što Mel skala bolje odgovara načinu na koji ljudsko uho percipira frekvencije, pa efikasnije izdvaja karakteristike relevantne za govor.

## Struktura repozitorijuma

```text
.
├── documentation/
│   ├── documentation.tex
│   ├── documentation.pdf
│   └── images/
├── main.ipynb
└── README.md
```

## Autori

- Jovana Medenica (364/2022)
- Iva Milutinović (262/2021)
