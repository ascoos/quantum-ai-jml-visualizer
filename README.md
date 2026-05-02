# Quantum AI JML Visualizer  
### Visualization of Quantum Decoherence & AI Drift Prediction using Ascoos OS Kernel 1.0.0

![License](https://img.shields.io/badge/license-AGL--F-blue.svg)
![PHP](https://img.shields.io/badge/PHP-8.4%2B-777BB4)
![Ascoos OS](https://img.shields.io/badge/Ascoos%20OS-Kernel%201.0.0-orange)

---

## Overview

This repository contains the **quantum-ai-jml-visualizer** case study for **Ascoos OS Kernel 1.0.0**.

It demonstrates how the kernel performs:

- **Quantum simulation** (Bell State |Φ+>, decoherence, Everett branching)  
- **Statistical analysis** (variance-based drift factor)  
- **Neural network prediction** (instability detection)  
- **JML-based UI rendering** (native, zero-dependency HTML generation)

Everything runs **natively**, without frameworks, without template engines, and without external libraries.

---

## Features

- Quantum state normalization & unitary evolution  
- Decoherence simulation using λ-parameter  
- Z-basis measurement with branching probabilities  
- Variance-based drift analysis  
- Neural network training & prediction (ReLU + Sigmoid)  
- JML dashboard rendering (dark mode, responsive grid)  
- Zero dependencies — powered entirely by Ascoos OS Kernel

---

## File Structure

```
/quantum-ai-jml-visualizer
│
├── quantum_ai_jml_visualizer.php   # Main case study file
├── LICENSE.md                      # AGL-G License
├── README.md                       # English documentation
└── README-GR.md                    # Greek documentation
```

---

## Running the Case Study

Requires:

- **PHP 8.4+**
- **Ascoos OS Kernel 1.0.0**

Run:

```bash
php quantum_ai_jml_visualizer.php
```

The script outputs a fully rendered **HTML dashboard** generated from JML.

---

## Quantum Logic (Snippet)

```php
$bellState = $quantum->normalize([
    [0.707, 0.0], [0.0, 0.0],
    [0.0, 0.0],   [0.707, 0.0]
]);

$lambda = 0.75;
$U = $math->tensor($I, $D);
$noisyState = $quantum->normalize(
    $quantum->applyUnitary($U, $bellState)
);
```

---

## Drift Analysis (Snippet)

```php
$driftFactor = (new TStatisticAnalysisHandler([
    $branchesZ[0]['probability'],
    $branchesZ[1]['probability']
]))->variance();
```

---

## AI Prediction (Snippet)

```php
$ai->compile([
    ['input'=>1,'output'=>4,'activation'=>'relu'],
    ['input'=>4,'output'=>1,'activation'=>'sigmoid']
]);

$ai->fit([[$driftFactor]], [($driftFactor > 0.2 ? 1 : 0)], epochs:100);
$prediction = $ai->predictNetwork([[$driftFactor]])[0];
```

---

## JML Dashboard (Snippet)

```jml
div:class('status-bar'),style('background:{$statusColor}') {
    `STATUS: {$statusText}`
}
```

The kernel converts this JML into HTML automatically.

---

## License

This project is licensed under the **AGL-F License**.

---

## Author

**Drogidis Christos**  
Creator of Ascoos OS  
[https://www.ascoos.com](https://www.ascoos.com)
