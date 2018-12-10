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
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a><span data-ttu-id="a2fc6-103">Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET</span><span class="sxs-lookup"><span data-stu-id="a2fc6-103">Calculate metrics to evaluate machine learning model quality - ML.NET</span></span>

<span data-ttu-id="a2fc6-104">Wie bewerten Sie die Qualität nach dem Trainieren des Modells?</span><span class="sxs-lookup"><span data-stu-id="a2fc6-104">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="a2fc6-105">Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a2fc6-105">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="a2fc6-106">Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="a2fc6-106">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```