---
title: Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: d6409307cd283ae67d7546c4dc6e19e6089a0766
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73975838"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a>Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie auf der Seite [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Wie bewerten Sie die Qualität nach dem Trainieren des Modells? Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.

Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
