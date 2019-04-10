---
title: Leitfaden zu ML.NET-Inhalt
description: Erfahren Sie mehr über das Erstellen von benutzerdefinierten KI-Lösungen, und integrieren Sie sie mithilfe von ML.NET in Ihre .NET-Anwendungen.
ms.date: 04/05/2019
ms.custom: seodec18
ms.openlocfilehash: de681daea5a29a121d350271ced4ccc2c0b1b533
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231330"
---
# <a name="mlnet-content-guide"></a><span data-ttu-id="12414-103">Leitfaden zu ML.NET-Inhalt</span><span class="sxs-lookup"><span data-stu-id="12414-103">ML.NET Content Guide</span></span>

<span data-ttu-id="12414-104">Dieser Leitfaden erläutert grundlegende Konzepte und stellt Tutorials und eine API-Referenz zur Arbeit mit ML.NET bereit.</span><span class="sxs-lookup"><span data-stu-id="12414-104">This guide explains basic concepts and provides tutorials and an API reference for working with ML.NET.</span></span>

> [!NOTE]
> <span data-ttu-id="12414-105">Diese Dokumentation bezieht sich auf ML.NET, das sich zurzeit in der Vorschau befindet.</span><span class="sxs-lookup"><span data-stu-id="12414-105">This documentation refers to ML.NET, which is currently in Preview.</span></span> <span data-ttu-id="12414-106">Änderungen am Material vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="12414-106">Material may be subject to change.</span></span> <span data-ttu-id="12414-107">Weitere Informationen finden Sie in der [ML.NET-Einführung](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="12414-107">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="get-started"></a><span data-ttu-id="12414-108">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="12414-108">Get started</span></span>

<span data-ttu-id="12414-109">Bearbeiten Sie zur Installation und zum Einstieg in ML.NET das [Tutorial: Erste Schritte](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span><span class="sxs-lookup"><span data-stu-id="12414-109">To install and start building in ML.NET, follow the [Get started tutorial](https://www.microsoft.com/net/learn/machinelearning-ai/ml-dotnet-get-started-tutorial).</span></span>

<span data-ttu-id="12414-110">Weitere Informationen zu ML.NET erhalten Sie unter [Was ist ML.NET?](what-is-mldotnet.md)</span><span class="sxs-lookup"><span data-stu-id="12414-110">To learn about ML.NET, see [What is ML.NET?](what-is-mldotnet.md)</span></span>

<span data-ttu-id="12414-111">Grundlegende Informationen finden Sie unter [Basiskonzepte für das Modelltraining in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span><span class="sxs-lookup"><span data-stu-id="12414-111">To understand basics, see [Basic concepts for model training in ML.NET](basic-concepts-model-training-in-mldotnet.md).</span></span>

## <a name="tutorials"></a><span data-ttu-id="12414-112">Tutorials</span><span class="sxs-lookup"><span data-stu-id="12414-112">Tutorials</span></span>

<span data-ttu-id="12414-113">[Standpunktanalyse mit einem Modell zur binären Klassifizierung](./tutorials/sentiment-analysis.md): Hier wird gezeigt, wie Sie eine App entwickeln, die ermittelt, ob eine Stimmung positiv oder negativ ist.</span><span class="sxs-lookup"><span data-stu-id="12414-113">[Analyze sentiment using a binary classification model](./tutorials/sentiment-analysis.md) shows you how to build an app that determines whether sentiment is positive or negative.</span></span>

<span data-ttu-id="12414-114">[Klassifizieren von GitHub-Problemen mit einem Modell zur mehrklassigen Klassifizierung](./tutorials/github-issue-classification.md): Hier wird gezeigt, wie Sie eine App entwickeln, die die Bezeichnung „Bereich“ für ein GitHub-Problem bestimmt.</span><span class="sxs-lookup"><span data-stu-id="12414-114">[Classify GitHub issues using a multiclass classification model](./tutorials/github-issue-classification.md) shows you how to build an app that determines the Area label for a GitHub issue.</span></span>

<span data-ttu-id="12414-115">[Vorhersage von Preisen mit einem Regressionsmodell](./tutorials/taxi-fare.md): Hier wird gezeigt, wie Sie eine Vorhersage-App erstellen, die zum Bestimmen der Antwort verschiedene Faktoren aus Verlaufsdaten nutzt.</span><span class="sxs-lookup"><span data-stu-id="12414-115">[Predict prices using a regression model](./tutorials/taxi-fare.md) shows you how to build a predictive app that uses many factors from historical data to determine the answer.</span></span>

<span data-ttu-id="12414-116">[Klassifizierung nach Merkmalen unter Verwendung des Iris-Beispiels](./tutorials/iris-clustering.md): Hier wird gezeigt, wie Sie ein Clusteringmodell zum Analysieren des Iris-Datasets verwenden.</span><span class="sxs-lookup"><span data-stu-id="12414-116">[Classify iris flowers by features](./tutorials/iris-clustering.md) shows you how to use a clustering model to analyze the iris data set.</span></span>

<span data-ttu-id="12414-117">[Erstellen eines Filmempfehlungssystems mit ML.NET](./tutorials/movie-recommmendation.md): Hier erfahren Sie, wie eine Empfehlungs-App erstellen, mit der Sie den Benutzern anhand des Benutzerverlaufs Filme empfehlen können.</span><span class="sxs-lookup"><span data-stu-id="12414-117">[Create a Movie Recommender with ML.NET](./tutorials/movie-recommmendation.md) shows you how to build a recommendation app to recommend movies to users based on their history.</span></span>

<span data-ttu-id="12414-118">[Erstellen einer benutzerdefinierten Image-Klassifizierung mit ML.NET und TensorFlow](./tutorials/image-classification.md): Veranschaulicht, wie ein vorhandenes Tensorflow-Modell zum Erstellen einer benutzerdefinierten Image-Klassifizierung mithilfe von ML.NET erneut trainiert wird.</span><span class="sxs-lookup"><span data-stu-id="12414-118">[Build an ML.NET custom image classifier with TensorFlow](./tutorials/image-classification.md): demonstrates how to retrain an existing Tensorflow model to create a custom image classifier using ML.NET.</span></span>

## <a name="how-to-guide"></a><span data-ttu-id="12414-119">Schrittanleitung</span><span class="sxs-lookup"><span data-stu-id="12414-119">How to guide</span></span>

<span data-ttu-id="12414-120">[Erstellen einer App für eine Spielerrangliste mit Infer.NET und probabilistischer Programmierung](./how-to-guides/matchup-app-infer-net.md): Hier wird gezeigt, wie Sie eine vereinfachte Version einer Spielerrangliste erstellen, wie sie in einem Xbox-Spiel angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="12414-120">[Build a game match-up list app with Infer.NET and probabilistic programming](./how-to-guides/matchup-app-infer-net.md) shows you how to build a simplified version of a match-up app like you'd see in an Xbox game.</span></span>

## <a name="resources"></a><span data-ttu-id="12414-121">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="12414-121">Resources</span></span>

<span data-ttu-id="12414-122">[Machine Learning-Glossar](./resources/glossary.md): Definition der Schlüsselterminologie.</span><span class="sxs-lookup"><span data-stu-id="12414-122">[Machine learning glossary](./resources/glossary.md) defines key terminology.</span></span>

<span data-ttu-id="12414-123">[Machine Learning-Aufgaben](./resources/tasks.md): Beschreibt Aufgaben wie z.B. Klassifizierung und Anomalieerkennung.</span><span class="sxs-lookup"><span data-stu-id="12414-123">[Machine learning tasks](./resources/tasks.md) describes tasks, such as classification and anomaly detection.</span></span> 

<span data-ttu-id="12414-124">[Datentransformationen](./resources/transforms.md): Beschreiben die Funktionen zur Datenvorbereitung in ML.NET.</span><span class="sxs-lookup"><span data-stu-id="12414-124">[Data transforms](./resources/transforms.md) describes data preparation capabilities in ML.NET.</span></span>

## <a name="api-reference"></a><span data-ttu-id="12414-125">API-Verweis</span><span class="sxs-lookup"><span data-stu-id="12414-125">API reference</span></span>

<span data-ttu-id="12414-126">In der [ML.NET-API-Referenz](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) finden Sie die gesamte Auswahl verfügbarer APIs.</span><span class="sxs-lookup"><span data-stu-id="12414-126">[ML.NET API Reference](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet) describes the breadth of APIs available.</span></span>
