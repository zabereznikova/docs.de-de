---
title: Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 529003913b166c966e131b006800f944096605b7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855567"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="976d8-103">Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells</span><span class="sxs-lookup"><span data-stu-id="976d8-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="976d8-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="976d8-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="976d8-105">Weitere Informationen finden Sie auf der Seite [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="976d8-105">For more information, visit the [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) page.</span></span>

<span data-ttu-id="976d8-106">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="976d8-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="976d8-107">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="976d8-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="976d8-108">Wie bewerten Sie die Qualität nach dem Trainieren des Modells?</span><span class="sxs-lookup"><span data-stu-id="976d8-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="976d8-109">Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="976d8-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="976d8-110">Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="976d8-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
