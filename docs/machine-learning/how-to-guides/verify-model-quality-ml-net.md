---
title: Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells
description: Erfahren Sie, wie Sie ML.NET Metriken zum Bewerten und Überprüfen der Qualität des Machine Learning-Modells berechnen
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 3e55c329ff12ffdbec41716ca95b4a77d5d082c8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64655190"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality"></a><span data-ttu-id="ebfa0-103">Berechnen von Metriken zum Bewerten der Qualität des Machine Learning-Modells</span><span class="sxs-lookup"><span data-stu-id="ebfa0-103">Calculate metrics to evaluate machine learning model quality</span></span> 

> [!NOTE]
> <span data-ttu-id="ebfa0-104">Dieses Thema bezieht sich auf ML.NET, was derzeit als Vorschau verfügbar ist, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ebfa0-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ebfa0-105">Weitere Informationen finden Sie in [der ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="ebfa0-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ebfa0-106">Diese Anleitung und das dazugehörte Beispiel verwenden derzeit **ML.NET Version 0.10**.</span><span class="sxs-lookup"><span data-stu-id="ebfa0-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="ebfa0-107">Weitere Informationen finden Sie in den Anmerkungen zur Version im [Dotnet/Machinelearning-GitHub-Repository](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="ebfa0-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="ebfa0-108">Wie bewerten Sie die Qualität nach dem Trainieren des Modells?</span><span class="sxs-lookup"><span data-stu-id="ebfa0-108">How do you evaluate quality after you train the model?</span></span> <span data-ttu-id="ebfa0-109">Jede maschinelle Lernaufgabe macht Metriken zur Qualitätsbewertung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ebfa0-109">Each machine learning task exposes metrics for quality evaluation.</span></span>

<span data-ttu-id="ebfa0-110">Sie können den entsprechenden „Kontext“ der Aufgabe verwenden, um das Modell wie im folgenden Beispiel zu bewerten:</span><span class="sxs-lookup"><span data-stu-id="ebfa0-110">You can use the corresponding 'context' of the task to evaluate the model, as in the following example:</span></span>

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```