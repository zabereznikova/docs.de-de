---
title: 'Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET'
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: ad71f7da6981ac370e60725f88d3c70b1d5c5237
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679215"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells: ML.NET

> [!NOTE]
> Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden. Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).

Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**. Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).

Wie bewerten Sie die Qualität nach dem Trainieren des Modells? Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.

Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```