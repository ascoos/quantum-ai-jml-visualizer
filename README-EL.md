# Quantum AI JML Visualizer  
### Οπτικοποίηση Κβαντικής Αποσυνοχής & AI Drift Prediction με το Ascoos OS Kernel 1.0.0

![License](https://img.shields.io/badge/license-AGL--F-blue.svg)
![PHP](https://img.shields.io/badge/PHP-8.4%2B-777BB4)
![Ascoos OS](https://img.shields.io/badge/Ascoos%20OS-Kernel%201.0.0-orange)

---

## Επισκόπηση

Το repository περιέχει το case study **quantum-ai-jml-visualizer** για το **Ascoos OS Kernel 1.0.0**.

Το παράδειγμα δείχνει:

- **Κβαντική προσομοίωση** (Bell State |Φ+>, decoherence, Everett branching)  
- **Στατιστική ανάλυση** (variance drift factor)  
- **Πρόβλεψη AI** (ανίχνευση αστάθειας)  
- **JML UI rendering** (native HTML χωρίς εξαρτήσεις)

Όλα εκτελούνται **native**, χωρίς frameworks, χωρίς template engines, χωρίς εξωτερικές βιβλιοθήκες.

---

## Χαρακτηριστικά

- Κανονικοποίηση κβαντικών καταστάσεων  
- Προσομοίωση αποσυνοχής με παράγοντα λ  
- Μετρήσεις Z-basis  
- Υπολογισμός drift variance  
- Εκπαίδευση & πρόβλεψη νευρωνικού δικτύου  
- Απόδοση dashboard μέσω JML  
- Zero dependencies — μόνο Ascoos OS Kernel

---

## Δομή Αρχείων

```
/quantum-ai-jml-visualizer
│
├── quantum_ai_jml_visualizer.php   # Κύριο αρχείο case study
├── LICENSE.md                      # AGL-F License
├── README.md                       # Αγγλική τεκμηρίωση
└── README-GR.md                    # Ελληνική τεκμηρίωση
```

---

## Εκτέλεση

Απαιτεί:

- **PHP 8.4+**
- **Ascoos OS Kernel 1.0.0**

Εκτέλεση:

```bash
php quantum_ai_jml_visualizer.php
```

Το script παράγει ένα πλήρες **HTML dashboard** μέσω JML.

---

## Κβαντική Λογική (Snippet)

```php
$bellState = $quantum->normalize([
    [0.707, 0.0], [0.0, 0.0],
    [0.0, 0.0],   [0.707, 0.0]
]);
```

---

## Ανάλυση Drift (Snippet)

```php
$driftFactor = (new TStatisticAnalysisHandler([
    $branchesZ[0]['probability'],
    $branchesZ[1]['probability']
]))->variance();
```

---

## Πρόβλεψη AI (Snippet)

```php
$ai->compile([
    ['input'=>1,'output'=>4,'activation'=>'relu'],
    ['input'=>4,'output'=>1,'activation'=>'sigmoid']
]);
```

---

## JML Dashboard (Snippet)

```jml
div:class('status-bar'),style('background:{$statusColor}') {
    `STATUS: {$statusText}`
}
```

---

## Άδεια

Το project διανέμεται υπό την **AGL-F License**.

---

## Συγγραφέας

**Δρογκίδης Χρήστος**  
Δημιουργός του Ascoos OS  
[https://www.ascoos.com](https://www.ascoos.com)
