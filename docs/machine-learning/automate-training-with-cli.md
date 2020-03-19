---
title: Automatisieren des Modelltrainings mit der ML.NET-CLI
description: Erfahren Sie, wie Sie mit dem ML.NET-CLI-Tool automatisch das beste Modell über die Befehlszeile trainieren können.
ms.date: 12/17/2019
ms.custom: how-to, mlnet-tooling
ms.openlocfilehash: 3344ed15266503d4d5c7cd9db0a0596f58a904fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79185884"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="364ea-103">Automatisieren des Modelltrainings mit der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="364ea-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="364ea-104">Die ML.NET-CLI automatisiert die Modellgenerierung für .NET-Entwickler.</span><span class="sxs-lookup"><span data-stu-id="364ea-104">The ML.NET CLI automates model generation for .NET developers.</span></span>

<span data-ttu-id="364ea-105">Um die ML.NET-API selbst zu verwenden (ohne ML.NET AutoML-CLI), müssen Sie einen Trainer (Implementierung eines Machine Learning-Algorithmus für eine bestimmte Aufgabe) und den Satz von Datentransformationen (Featureentwicklung) auswählen, die auf Ihre Daten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="364ea-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="364ea-106">Die optimale Pipeline variiert für jedes Dataset, und die Auswahl des optimalen Algorithmus aus allen Optionen erhöht die Komplexität.</span><span class="sxs-lookup"><span data-stu-id="364ea-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="364ea-107">Darüber hinaus muss für jeden Algorithmus ein Satz an Hyperparametern optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="364ea-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="364ea-108">Daher kann es manchmal Wochen oder Monate dauern, ein Machine Learning-Modell zu optimieren, um die beste Kombination aus Featureentwicklung, Lernalgorithmen und Hyperparametern zu finden.</span><span class="sxs-lookup"><span data-stu-id="364ea-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="364ea-109">Die ML.NET-CLI vereinfacht diesen Prozess mithilfe von automatisiertem Machine Learning (AutoML).</span><span class="sxs-lookup"><span data-stu-id="364ea-109">The ML.NET CLI simplifies this process using automated machine learning (AutoML).</span></span>

> [!NOTE]
> <span data-ttu-id="364ea-110">Dieses Thema bezieht sich auf die ML.NET-**CLI** und ML.NET **AutoML**, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="364ea-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="364ea-111">Was ist die ML.NET-Befehlszeilenschnittstelle (CLI)?</span><span class="sxs-lookup"><span data-stu-id="364ea-111">What is the ML.NET command-line interface (CLI)?</span></span>

<span data-ttu-id="364ea-112">Die ML.NET-CLI ist ein [.NET Core-Tool](../core/tools/global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="364ea-112">The ML.NET CLI is a [.NET Core tool](../core/tools/global-tools.md).</span></span> <span data-ttu-id="364ea-113">Nach der Installation erhalten Sie eine Machine Learning-Aufgabe und ein Trainingsdataset. Es werden ein ML.NET-Modell und der C#-Code generiert, der für die Verwendung des Modells in der Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="364ea-113">Once installed, you give it a machine learning task and a training dataset, and it generates an ML.NET model, as well as the C# code to run to use the model in your application.</span></span>

<span data-ttu-id="364ea-114">Wie in der folgenden Abbildung dargestellt, ist es einfach, ein qualitativ hochwertiges ML.NET-Modell (serialisierte ZIP-Datei des Modells) plus den Beispiel-C#-Code zu generieren, um dieses Modell auszuführen/zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="364ea-114">As shown in the following figure, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="364ea-115">Darüber hinaus wird der C#-Code zum Erstellen/Trainieren dieses Modells generiert, sodass Sie suchen und iterieren können, welcher Algorithmus und welche Einstellungen für dieses generierte „beste Modell“ verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="364ea-115">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span>

<span data-ttu-id="364ea-116">![Bild](media/automate-training-with-cli/cli-high-level-process.png "AutoML-Engine arbeitet in der ML.NET-CLI")</span><span class="sxs-lookup"><span data-stu-id="364ea-116">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="364ea-117">Sie können diese Objekte aus Ihren eigenen Datasets generieren, ohne selbst zu codieren. Damit steigern Sie also auch Ihre Produktivität, selbst wenn Sie ML.NET bereits kennen.</span><span class="sxs-lookup"><span data-stu-id="364ea-117">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="364ea-118">Derzeit unterstützt die ML.NET-CLI folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="364ea-118">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`
- <span data-ttu-id="364ea-119">Zukünftig: weitere Machine Learning-Aufgaben wie `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span><span class="sxs-lookup"><span data-stu-id="364ea-119">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="364ea-120">Beispiel für die Verwendung:</span><span class="sxs-lookup"><span data-stu-id="364ea-120">Example of usage:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![Bild](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="364ea-122">Sie können sie auf die gleiche Weise auf *Windows PowerShell*, \*macOS-/Linux-Bash oder *Windows CMD* ausführen.</span><span class="sxs-lookup"><span data-stu-id="364ea-122">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="364ea-123">Die tabellarische automatische Vervollständigung (Parametervorschläge) funktioniert jedoch nicht unter *Windows-CMD*.</span><span class="sxs-lookup"><span data-stu-id="364ea-123">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="364ea-124">Generierte Ausgabeobjekte</span><span class="sxs-lookup"><span data-stu-id="364ea-124">Output assets generated</span></span>

<span data-ttu-id="364ea-125">Der CLI-Befehl `auto-train` generiert die folgenden Objekte im Ausgabeordner:</span><span class="sxs-lookup"><span data-stu-id="364ea-125">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="364ea-126">Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort für die Ausführung von Vorhersagen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="364ea-126">A serialized model .zip ("best model") ready to use for running predictions.</span></span>
- <span data-ttu-id="364ea-127">C#-Lösung mit:</span><span class="sxs-lookup"><span data-stu-id="364ea-127">C# solution with:</span></span>
  - <span data-ttu-id="364ea-128">C#-Code, um das generierte Modell auszuführen/zu bewerten (um mit diesem Modell Vorhersagen in Ihren Endbenutzer-Apps zu treffen).</span><span class="sxs-lookup"><span data-stu-id="364ea-128">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
  - <span data-ttu-id="364ea-129">C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird (zu Lernzwecken oder zum erneuten Trainieren des Modells).</span><span class="sxs-lookup"><span data-stu-id="364ea-129">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="364ea-130">Protokolldatei mit Informationen über alle Iterationen/Sweep-Vorgänge über die verschiedenen ausgewerteten Algorithmen, einschließlich ihrer detaillierten Konfiguration/Pipeline.</span><span class="sxs-lookup"><span data-stu-id="364ea-130">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="364ea-131">Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem generierten ML-Modell Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="364ea-131">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="364ea-132">Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie Ihr Modell erneut trainieren und untersuchen und iterieren können, welchen spezifischen Trainer/Algorithmus und Hyperparameter die CLI und AutoML im Hintergrund ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="364ea-132">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span>

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="364ea-133">Verstehen der Qualität des Modells</span><span class="sxs-lookup"><span data-stu-id="364ea-133">Understanding the quality of the model</span></span>

<span data-ttu-id="364ea-134">Wenn Sie mit dem CLI-Tool ein „bestes Modell“ erstellen, werden Qualitätsmetriken angezeigt (wie Genauigkeit und Bestimmtheitsmaß), die für die von Ihnen angestrebte ML-Aufgabe geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="364ea-134">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy and R-Squared) as appropriate for the ML task you're targeting.</span></span>

<span data-ttu-id="364ea-135">Hier werden diese Metriken zusammengefasst, die nach ML-Aufgaben gruppiert sind, damit Sie die Qualität Ihres automatisch generierten „besten Modells“ verstehen können.</span><span class="sxs-lookup"><span data-stu-id="364ea-135">Here those metrics are summarized grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="364ea-136">Metriken für binäre Klassifizierungsmodelle</span><span class="sxs-lookup"><span data-stu-id="364ea-136">Metrics for Binary Classification models</span></span>

<span data-ttu-id="364ea-137">Im Folgenden wird die Metrikliste der binären ML-Klassifizierungsaufgaben für die fünf besten, von der CLI gefundenen Modelle angezeigt:</span><span class="sxs-lookup"><span data-stu-id="364ea-137">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span>

![Bild](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="364ea-139">Die Genauigkeit ist eine beliebte Metrik für Klassifizierungsprobleme. Allerdings ist die Genauigkeit nicht immer die beste Metrik, um das beste Modell auszuwählen, wie in den folgenden Referenzen erläutert.</span><span class="sxs-lookup"><span data-stu-id="364ea-139">Accuracy is a popular metric for classification problems, however accuracy isn't always the best metric to select the best model from as explained in the following references.</span></span> <span data-ttu-id="364ea-140">Es gibt Fälle, in denen Sie die Qualität Ihres Modells mit zusätzlichen Metriken bewerten müssen.</span><span class="sxs-lookup"><span data-stu-id="364ea-140">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="364ea-141">Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für die binäre Klassifizierung](resources/metrics.md#evaluation-metrics-for-binary-classification).</span><span class="sxs-lookup"><span data-stu-id="364ea-141">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for binary classification](resources/metrics.md#evaluation-metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="364ea-142">Metriken für Multiklassen-Klassifizierungsmodelle</span><span class="sxs-lookup"><span data-stu-id="364ea-142">Metrics for Multi-class Classification models</span></span>

<span data-ttu-id="364ea-143">Im Folgenden wird die Metrikliste der ML-Aufgabe für die Multiklassenklassifizierung für die fünf besten Modelle angezeigt, die von der CLI ermittelt wurden:</span><span class="sxs-lookup"><span data-stu-id="364ea-143">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span>

![Bild](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="364ea-145">Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für mehrklassige Klassifizierung](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span><span class="sxs-lookup"><span data-stu-id="364ea-145">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for multiclass classification](resources/metrics.md#evaluation-metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-and-recommendation-models"></a><span data-ttu-id="364ea-146">Metriken für Regressions- und Empfehlungsmodelle</span><span class="sxs-lookup"><span data-stu-id="364ea-146">Metrics for Regression and Recommendation models</span></span>

<span data-ttu-id="364ea-147">Ein Regressionsmodell eignet sich gut für die Daten, wenn die Unterschiede zwischen den beobachteten Werten und den vorhergesagten Werten des Modells klein und zufällig sind.</span><span class="sxs-lookup"><span data-stu-id="364ea-147">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="364ea-148">Die Regression kann mit bestimmten Metriken ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="364ea-148">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="364ea-149">Es wird eine ähnliche Metrikliste für die fünf besten, von der CLI gefundenen Modelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="364ea-149">You'll see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="364ea-150">In diesem speziellen Fall bezogen auf eine ML-Regressionsaufgabe:</span><span class="sxs-lookup"><span data-stu-id="364ea-150">In this particular case related to a regression ML task:</span></span>

![Bild](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="364ea-152">Um die Metriken zu untersuchen und zu verstehen, die von der CLI ausgegeben werden, lesen Sie [Auswertungsmetriken für die Regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span><span class="sxs-lookup"><span data-stu-id="364ea-152">To explore and understand the metrics that are output by the CLI, see [Evaluation metrics for regression](resources/metrics.md#evaluation-metrics-for-regression-and-recommendation).</span></span>

## <a name="see-also"></a><span data-ttu-id="364ea-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364ea-153">See also</span></span>

- [<span data-ttu-id="364ea-154">Vorgehensweise: Installieren des ML.NET-CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="364ea-154">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="364ea-155">Tutorial: Stimmungsanalyse mit der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="364ea-155">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="364ea-156">Befehlsreferenz für die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="364ea-156">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="364ea-157">Telemetrie in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="364ea-157">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)
