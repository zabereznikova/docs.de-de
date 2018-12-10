---
title: 'Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET'
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149522"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET

Wie bewerten Sie die Qualität nach dem Trainieren des Modells? Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.

Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```