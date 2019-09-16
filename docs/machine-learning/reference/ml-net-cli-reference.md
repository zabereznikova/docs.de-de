---
title: Der Befehl „auto-train“ im ML.NET-CLI-Tool
description: Übersicht, Beispiele und Verweise für den Befehl „auto-train“ im ML.NET-CLI-Tool
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 8363a16ab5e793e715131ac37283106517850439
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929197"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="0fab2-103">Der Befehl „auto-train“ in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="0fab2-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="0fab2-104">Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="0fab2-105">Der `auto-train`-Befehl ist der Hauptbefehl des ML.NET-CLI-Tools.</span><span class="sxs-lookup"><span data-stu-id="0fab2-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="0fab2-106">Mit dem Befehl können Sie ein qualitativ hochwertiges ML.NET-Modell (serialisierte ZIP-Datei des Modells) plus den Beispiel-C#-Code generieren, um dieses Modell auszuführen/zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="0fab2-107">Darüber hinaus wird der C#-Code zum Erstellen/Trainieren dieses Modells generiert, sodass Sie suchen können, welcher Algorithmus und welche Einstellungen für dieses generierte „beste Modell“ verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="0fab2-108">Sie können diese Objekte aus Ihren eigenen Datasets generieren, ohne selbst zu codieren. Damit steigern Sie also auch Ihre Produktivität, selbst wenn Sie ML.NET bereits kennen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="0fab2-109">Derzeit unterstützt die ML.NET-CLI folgende Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="0fab2-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="0fab2-110">Zukünftig: weitere Machine Learning-Aufgaben wie</span><span class="sxs-lookup"><span data-stu-id="0fab2-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="0fab2-111">Beispiel für die Verwendung in der Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="0fab2-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="0fab2-112">Der Befehl `mlnet auto-train` generiert folgende Objekte:</span><span class="sxs-lookup"><span data-stu-id="0fab2-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="0fab2-113">Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0fab2-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="0fab2-114">C#-Code, um das generierte Modell auszuführen/zu bewerten (um mit diesem Modell Vorhersagen in Ihren Endbenutzer-Apps zu treffen).</span><span class="sxs-lookup"><span data-stu-id="0fab2-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="0fab2-115">C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird (zu Lernzwecken).</span><span class="sxs-lookup"><span data-stu-id="0fab2-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="0fab2-116">Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem generierten ML-Modell Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="0fab2-117">Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie untersuchen können, welchen spezifischen Trainer/Algorithmus und Hyperparameter die CLI und die ML.NET AutoML-Engine ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="0fab2-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-parameters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="0fab2-118">Der Befehl „auto-train“ verwendet die AutoML-Engine</span><span class="sxs-lookup"><span data-stu-id="0fab2-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="0fab2-119">Die CLI verwendet die ML.NET AutoML-Engine (NuGet-Paket), um intelligent nach den besten Modellen zu suchen, wie in der folgenden Abbildung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="0fab2-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="0fab2-120">![Bild](./media/ml-net-automl-working-diagram.png "AutoML-Engine arbeitet in der ML.NET-CLI")</span><span class="sxs-lookup"><span data-stu-id="0fab2-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="0fab2-121">Wenn Sie das ML.NET-CLI-Tool mit dem Befehl „auto-train“ ausführen, sehen Sie, wie das Tool zahlreiche Iterationen mit verschiedenen Algorithmen und Kombinationen der Konfiguration ausprobiert.</span><span class="sxs-lookup"><span data-stu-id="0fab2-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="0fab2-122">Verweis für den Befehl „auto-train“</span><span class="sxs-lookup"><span data-stu-id="0fab2-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="0fab2-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0fab2-123">Examples</span></span>

<span data-ttu-id="0fab2-124">Einfachster CLI-Befehl für ein binäres Klassifizierungsproblem (AutoML muss den Großteil der Konfiguration aus den bereitgestellten Daten ableiten):</span><span class="sxs-lookup"><span data-stu-id="0fab2-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="0fab2-125">Ein weiterer einfacher CLI-Befehl für ein Regressionsproblem:</span><span class="sxs-lookup"><span data-stu-id="0fab2-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="0fab2-126">Erstellen und trainieren Sie ein binäres Klassifizierungsmodell mit einem Trainingsdataset, einem Testdataset und weiteren benutzerdefinierten Argumenten:</span><span class="sxs-lookup"><span data-stu-id="0fab2-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="0fab2-127">name</span><span class="sxs-lookup"><span data-stu-id="0fab2-127">Name</span></span>

<span data-ttu-id="0fab2-128">`mlnet auto-train` -Trainiert mehrere Modelle ('n' Iterationen) basierend auf dem bereitgestellten Dataset und wählt schließlich das beste Modell aus, speichert es als serialisierte ZIP-Datei und generiert den zugehörigen C#-Code für Bewertung und Training.</span><span class="sxs-lookup"><span data-stu-id="0fab2-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0fab2-129">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0fab2-129">Synopsis</span></span>

```console
> mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

<span data-ttu-id="0fab2-130">Ungültige Eingabeoptionen sollten dazu führen, dass das CLI-Tool eine Liste gültiger Eingaben und eine Fehlermeldung ausgibt, aus der hervorgeht, welches Argument fehlt, falls dies der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="0fab2-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="0fab2-131">Optionen</span><span class="sxs-lookup"><span data-stu-id="0fab2-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="0fab2-132">`--task | --mltask | -T` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="0fab2-133">Eine einzelne Zeichenfolge, die das zu lösende ML-Problem enthält.</span><span class="sxs-lookup"><span data-stu-id="0fab2-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="0fab2-134">Zum Beispiel eine der folgenden Aufgaben (die CLI wird später alle in AutoML unterstützten Aufgaben unterstützen):</span><span class="sxs-lookup"><span data-stu-id="0fab2-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="0fab2-135">`regression` – Wählen Sie, ob das ML-Modell zur Vorhersage eines numerischen Werts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fab2-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="0fab2-136">`binary-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).</span><span class="sxs-lookup"><span data-stu-id="0fab2-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="0fab2-137">`multiclass-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).</span><span class="sxs-lookup"><span data-stu-id="0fab2-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="0fab2-138">In zukünftigen Releases werden zusätzliche ML-Aufgaben und Szenarien wie `recommendations`, `clustering` und `ranking` unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fab2-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="0fab2-139">In diesem Argument sollte nur eine ML-Aufgabe bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="0fab2-140">`--dataset | -d` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="0fab2-141">Dieses Argument stellt den Dateipfad zu einer der folgenden Optionen bereit:</span><span class="sxs-lookup"><span data-stu-id="0fab2-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="0fab2-142">*A: Die gesamte Datasetdatei:* Wenn Sie diese Option verwenden und der Benutzer das `--test-dataset` und das `--validation-dataset` nicht bereitstellt, werden intern Kreuzvalidierungen (k-fach, etc.) oder automatisierte Verfahren zur Aufteilung das Daten für die Validierung des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="0fab2-143">In diesem Fall muss der Benutzer nur den Dateipfad zum Dataset angeben.</span><span class="sxs-lookup"><span data-stu-id="0fab2-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="0fab2-144">*B: Die Datei für das Trainingsdataset:* Wenn der Benutzer auch Datasets für die Modellvalidierung bereitstellt (mit `--test-dataset` und optional `--validation-dataset`), dann bedeutet das Argument `--dataset`, dass nur das „Trainingsdataset“ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0fab2-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="0fab2-145">Wenn Sie beispielsweise 80%-20%ig-Ansatz zur Validierung der Modellqualität und zum Ermitteln von Genauigkeitsmetriken verwenden, enthält das „Trainingsdataset“ 80 % der Daten und das „Testdataset“ 20 % der Daten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-146">`--test-dataset | -t` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="0fab2-147">Dateipfad, der auf die Datei des Testdatasets zeigt, z.B. bei Verwendung eines 80%-20%-Ansatzes bei regelmäßigen Validierungen zur Ermittlung von Genauigkeitsmetriken.</span><span class="sxs-lookup"><span data-stu-id="0fab2-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="0fab2-148">Bei der Verwendung des `--test-dataset` ist auch das `--dataset` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fab2-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="0fab2-149">Das `--test-dataset`-Argument ist optional, sofern das „--validation-dataset“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0fab2-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="0fab2-150">In diesem Fall muss der Benutzer die drei Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-151">`--validation-dataset | -v` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="0fab2-152">Dateipfad, der auf die Datei für das Validierungsdataset zeigt.</span><span class="sxs-lookup"><span data-stu-id="0fab2-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="0fab2-153">Das Validierungsdataset ist in jedem Fall optional.</span><span class="sxs-lookup"><span data-stu-id="0fab2-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="0fab2-154">Bei der Verwendung des `validation dataset` sollte folgendes Verhalten auftreten:</span><span class="sxs-lookup"><span data-stu-id="0fab2-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="0fab2-155">Es sind auch die `test-dataset`- und `--dataset`-Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fab2-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="0fab2-156">Das `validation-dataset`-Dataset wird verwendet, um den Vorhersagefehler für die Modellauswahl zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="0fab2-157">Das `test-dataset` wird zur Beurteilung des Generalisierungsfehlers des endgültig ausgewählten Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="0fab2-158">Idealerweise sollte das Testset in einem „Tresor“ aufbewahrt werden und erst am Ende der Datenanalyse zur Anwendung kommen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="0fab2-159">Grundsätzlich wird bei die Validierungsphase bei Verwendung eines `validation dataset` plus des `test dataset` in zwei Teile aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="0fab2-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="0fab2-160">Im ersten Teil betrachten Sie einfach Ihre Modelle und wählen den leistungsstärksten Ansatz anhand der Validierungsdaten (=Validierung) aus.</span><span class="sxs-lookup"><span data-stu-id="0fab2-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="0fab2-161">Dann schätzen Sie die Genauigkeit des gewählten Ansatzes (=Test).</span><span class="sxs-lookup"><span data-stu-id="0fab2-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="0fab2-162">Daher sollten die Daten im Verhältnis 80/10/10 oder 75/15/10 geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="0fab2-163">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fab2-163">For example:</span></span>

- <span data-ttu-id="0fab2-164">Die Datei `training-dataset` sollte 75 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="0fab2-165">Die Datei `validation-dataset` sollte 15 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="0fab2-166">Die Datei `test-dataset` sollte 10 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="0fab2-167">In jedem Fall entscheidet der Benutzer anhand der CLI, die die bereits aufgeteilten Dateien bereitstellt, über die Prozentangaben.</span><span class="sxs-lookup"><span data-stu-id="0fab2-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-168">`--label-column-name | -n` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="0fab2-169">Mit diesem Argument kann eine bestimmte Objekt-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem der Name der Spalte im Header des Datasets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0fab2-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="0fab2-170">Dieses Argument wird nur für überwachte ML-Aufgaben verwendet, wie z.B. ein *Klassifizierungsproblem*.</span><span class="sxs-lookup"><span data-stu-id="0fab2-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="0fab2-171">Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.</span><span class="sxs-lookup"><span data-stu-id="0fab2-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-172">`--label-column-index | -i` (Ganzzahl)</span><span class="sxs-lookup"><span data-stu-id="0fab2-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="0fab2-173">Mit diesem Argument kann eine bestimmte Ziel-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem Sie den numerischen Index der Spalte in der Datasetdatei verwenden (Spaltenindexwerte beginnen bei 1).</span><span class="sxs-lookup"><span data-stu-id="0fab2-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="0fab2-174">*Hinweis*: Wenn der Benutzer auch `--label-column-name` verwendet, wird `--label-column-name` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="0fab2-175">Dieses Argument wird nur für eine überwachte ML-Aufgabe verwendet, wie z.B. ein *Klassifizierungsproblem*.</span><span class="sxs-lookup"><span data-stu-id="0fab2-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="0fab2-176">Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.</span><span class="sxs-lookup"><span data-stu-id="0fab2-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-177">`--ignore-columns | -I` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="0fab2-178">Mit diesem Argument können Sie vorhandene Spalten in der Datasetdatei ignorieren, sodass sie nicht geladen und nicht in den Trainingsprozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="0fab2-179">Geben Sie die Namen der Spalten an, die Sie ignorieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="0fab2-180">Verwenden Sie „, „ (Komma mit Leerzeichen) oder „ „ (Leerzeichen), um mehrere Spaltennamen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="0fab2-181">Sie können Anführungszeichen für Spaltennamen verwenden, die Leerzeichen enthalten (z.B. „ist angemeldet“).</span><span class="sxs-lookup"><span data-stu-id="0fab2-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="0fab2-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fab2-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="0fab2-183">`--has-header | -h` (Bool)</span><span class="sxs-lookup"><span data-stu-id="0fab2-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="0fab2-184">Geben Sie an, ob die Datasetdatei(en) eine Kopfzeile enthält/enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="0fab2-185">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="0fab2-185">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="0fab2-186">Der Standardwert ist `true`, wenn der Benutzer dieses Argument nicht angibt.</span><span class="sxs-lookup"><span data-stu-id="0fab2-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="0fab2-187">Um das `--label-column-name`-Argument zu verwenden, benötigen Sie in der Datasetdatei einen Header und `--has-header` muss auf `true` (Standardwert) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-188">`--max-exploration-time | -x` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="0fab2-189">Die maximale Untersuchungszeit beträgt standardmäßig 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="0fab2-189">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="0fab2-190">Dieses Argument legt die maximale Zeit (in Sekunden) für den Prozess fest, um mehrere Trainer und Konfigurationen zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="0fab2-191">Die konfigurierte Zeit kann überschritten werden, wenn die angegebene Zeit für eine einzelne Iteration zu kurz ist (z.B. 2 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="0fab2-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="0fab2-192">In diesem Fall ist die tatsächliche Zeit die erforderliche Zeit, um eine Modellkonfiguration in einer einzigen Iteration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="0fab2-193">Die für Iterationen benötigte Zeit kann je nach Größe des Datasets variieren.</span><span class="sxs-lookup"><span data-stu-id="0fab2-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-194">`--cache | -c` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="0fab2-195">Wenn Sie Caching verwenden, wird das gesamte Trainingsdataset im Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="0fab2-196">Bei kleinen und mittleren Datasets kann Caching die Trainingsleistung erheblich verbessern, sodass die Trainingszeit im Vergleich zu einem Training ohne Cache kürzer sein kann.</span><span class="sxs-lookup"><span data-stu-id="0fab2-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="0fab2-197">Bei großen Datasets kann das Laden aller Daten im Speicher jedoch negative Auswirkungen haben, da Sie unter Umständen nicht mehr genügend Speicher zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="0fab2-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="0fab2-198">Wenn Sie für das Training mit großen Datasetdateien arbeiten und keinen Cache verwenden, streamt ML.NET Datenblöcke vom Laufwerk, wenn während des Trainings mehr Daten geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="0fab2-199">Sie können folgende Werte angeben:</span><span class="sxs-lookup"><span data-stu-id="0fab2-199">You can specify the following values:</span></span>

<span data-ttu-id="0fab2-200">`on`: Erzwingt, dass während des Trainings der Cache verwendet wird</span><span class="sxs-lookup"><span data-stu-id="0fab2-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="0fab2-201">`off`: Erzwingt, dass während des Trainings der Cache nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="0fab2-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="0fab2-202">`auto`: Je nach AutoML-Heuristiken wird der Cache verwendet oder nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="0fab2-203">In der Regel verwenden kleine/mittlere Datasets den Cache, und große Datasets verwenden keinen Cache, wenn Sie die Option `auto` verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fab2-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="0fab2-204">Wenn Sie den `--cache`-Parameter nicht angeben, wird standardmäßig die Cachekonfiguration `auto` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-205">`--name | -N` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-205">`--name | -N` (string)</span></span>

<span data-ttu-id="0fab2-206">Der Name für das erstellte Ausgabeprojekt oder die erstellte Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="0fab2-206">The name for the created output project or solution.</span></span> <span data-ttu-id="0fab2-207">Wenn kein Name angegeben ist, wird der Name `sample-{mltask}` verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fab2-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="0fab2-208">Die ML.NET-Modelldatei (ZIP-Datei) erhält ebenfalls denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="0fab2-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-209">`--output-path | -o` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="0fab2-210">Stammspeicherort/-ordner für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0fab2-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="0fab2-211">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0fab2-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="0fab2-212">`--verbosity | -V` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="0fab2-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="0fab2-213">Legt den Ausführlichkeitsgrad für die Standardausgabe fest.</span><span class="sxs-lookup"><span data-stu-id="0fab2-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="0fab2-214">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0fab2-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="0fab2-215">`m[inimal]` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="0fab2-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="0fab2-216">`diag[nostic]` (Protokollierung der Informationsebene)</span><span class="sxs-lookup"><span data-stu-id="0fab2-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="0fab2-217">Standardmäßig sollte das CLI-Tool ein Mindestfeedback (minimal) anzeigen, wenn es funktioniert, wie z.B. die Angabe, dass es funktioniert und, wenn möglich, Angaben dazu, wie viel Zeit übrig ist oder wie viel Prozent der Zeit abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="0fab2-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="0fab2-218">Druckt die Hilfe für den Befehl und eine Beschreibung der einzelnen Parameter für den Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="0fab2-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="0fab2-219">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fab2-219">See also</span></span>

- [<span data-ttu-id="0fab2-220">Vorgehensweise: Installieren des ML.NET-CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="0fab2-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="0fab2-221">Automatisieren des Modelltrainings mit der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="0fab2-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="0fab2-222">Tutorial: Automatisches Generieren eines binären Klassifizierers mit der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="0fab2-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="0fab2-223">Telemetrie in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="0fab2-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
