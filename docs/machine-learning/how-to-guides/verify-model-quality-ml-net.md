---
title: Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 2c7749205b862a42f42b857972057c441ab84364
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641098"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="3dd84-103">Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells</span><span class="sxs-lookup"><span data-stu-id="3dd84-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="3dd84-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3dd84-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3dd84-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="3dd84-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="3dd84-106">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="3dd84-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="3dd84-107">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="3dd84-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="3dd84-108">Wie bewerten Sie die Qualität nach dem Trainieren des Modells?</span><span class="sxs-lookup"><span data-stu-id="3dd84-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="3dd84-109">Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3dd84-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="3dd84-110">Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="3dd84-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
