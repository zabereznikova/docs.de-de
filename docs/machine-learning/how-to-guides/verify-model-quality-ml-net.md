---
title: 'Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET'
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2018
ms.locfileid: "52297567"
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