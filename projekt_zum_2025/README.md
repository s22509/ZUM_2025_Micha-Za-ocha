# **Projekt zaliczeniowy – Zastosowania Uczenia Maszynowego**

## **1. Informacje ogólne**
**Nazwa projektu:**  
*Analiza emocji w tweetach (TweetEval)*  

**Autor:**  
Michał Załocha 

**Kierunek, rok i tryb studiów:**  
*Informatyka, semestr III, internetowe*  

**Data oddania projektu:**  
18.01.2026  

---

## **2. Opis projektu**
Celem projektu jest klasyfikacja emocji w tekstach z mediów społecznościowych. Projekt pozwala na analizę nastrojów użytkowników Twittera z wykorzystaniem metod NLP i uczenia maszynowego.  

---

## **3. Dane**
**Źródło danych: Kaggle**  

**Link do danych:**  
`https://www.kaggle.com/datasets/thedevastator/tweeteval-a-multi-task-classification-benchmark`  

**Opis danych:**  
- liczba próbek:  3223
- liczba cech / kolumn:  2
- format danych:  csv
- rodzaj etykiet / klas:  klasy emocji (anger, joy, sadness, optimism)
- licencja:  CC0: Public Domain

---

## **4. Cel projektu**
Cel badawczy: porównanie skuteczności trzech różnych podejść do klasyfikacji tekstu pod względem jakości predykcji emocji.

Model przypisuje jedną z czterech emocji do pojedynczego tweeta. Z projektu można się dowiedzieć, który model radzi sobie najlepiej z tego typu danymi.

---

## **5. Struktura projektu**
Projekt składa się z czterech głównych etapów, każdy w osobnym notatniku `.ipynb`:

| Etap | Nazwa pliku | Opis |
|------|--------------|------|
| 1 | `1_EDA.ipynb` | Analiza danych, wizualizacje, wnioski |
| 2 | `2_Preprocessing_Features.ipynb` | Czyszczenie danych, preprocessing, inżynieria cech |
| 3 | `3_Models_Training.ipynb` | Trening modeli klasycznego ML, sieci neuronowej i transformera |
| 4 | `4_Evaluation.ipynb` | Ewaluacja, porównanie modeli, wizualizacje wyników |

---

## **6. Modele**
Projekt obejmuje trzy różne podejścia do modelowania danych:

### **6.1 Model klasyczny ML**
- Algorytm: Logistic Regression
- Krótki opis działania: użycie wektoryzacji TF-IDF, aby przekształcić tweety na wersję numeryczną i uczenie się na powstałych wektorach
- Wyniki / metryki: F1-macro: 0.52

### **6.2 Sieć neuronowa zbudowana od zera**
- Architektura: Dense
- Liczba warstw / neuronów: 4
- Funkcje aktywacji i optymalizator:  softmax, Adam
- Wyniki: F1-macro: 0.59

### **6.3 Model transformerowy (fine-tuning)**
- Nazwa modelu: distilBERT
- Zastosowana biblioteka: HuggingFace Transformers
- Zakres dostosowania: pełny fine-tuning
- Wyniki: F1-macro: 0.79

---

## **7. Ewaluacja**
**Użyte metryki: accuracy, precision, recall, F1‑score (macro)**  
**  

**Porównanie modeli:**

| Model | Metryka główna | Wynik | Uwagi |
|--------|----------------|--------|--------|
| Klasyczny ML | F1-macro | 0.52 |  |
| Sieć neuronowa | F1-macro | 0.59 |  |
| Transformer | F1-macro | 0.79 | najlepszy |

**Wizualizacje:**  
- Macierz pomyłek  
- Krzywa ROC

---

## **8. Wnioski i podsumowanie**
Najlepsze wyniki uzyskał model transformerowy, co wynika z wykorzystania transfer learningu oraz wiedzy językowej zdobytej na dużych zbiorach danych.

Przykładowe zastosowania: analiza nastrojów w mediach społecznościowych
---

## **9. Struktura repozytorium**
```
projekt_zum_2025/
│
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 1_EDA.ipynb
│ ├── 2_Preprocessing_Features.ipynb
│ ├── 3_Models_Training.ipynb
│ └── 4_Evaluation.ipynb
├── models/
├── results/
├── README.md
└── requirements.txt
```
## **10. Technologia i biblioteki**
- Python 3.x  
- NumPy, Pandas, Matplotlib, Plotly, Seaborn, Joblib  
- scikit-learn  
- TensorFlow, PyTorch  
- HuggingFace Transformers  

---

## **11. Licencja projektu**
Projekt udostępniony na licencji:  CC0
 
Źródło danych: https://www.kaggle.com/datasets/thedevastator/tweeteval-a-multi-task-classification-benchmark.

