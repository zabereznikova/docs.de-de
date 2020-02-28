---
title: Befehlsreferenz für die ML.NET-CLI
description: Übersicht, Beispiele und Verweise für den Befehl „auto-train“ im ML.NET-CLI-Tool
ms.date: 12/18/2019
ms.openlocfilehash: 537f8d361c170378f5fe8cf454320831d7c8cbf2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449698"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="53cb0-103">Befehlsreferenz für die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="53cb0-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="53cb0-104">Der `auto-train`-Befehl ist der Hauptbefehl des ML.NET-CLI-Tools.</span><span class="sxs-lookup"><span data-stu-id="53cb0-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="53cb0-105">Mit dem Befehl können Sie ein qualitativ hochwertiges ML.NET-Modell mithilfe von automatisiertem maschinellen Lernen (AutoML) sowie den C#-Beispielcode generieren, um dieses Modell auszuführen bzw. zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="53cb0-106">Außerdem wird der C#-Code zum Trainieren des Modells für Sie generiert, damit Sie den Algorithmus und die Einstellungen des Modells untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="53cb0-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="53cb0-107">Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="53cb0-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="53cb0-108">Overview</span></span>

<span data-ttu-id="53cb0-109">Verwendungsbeispiel:</span><span class="sxs-lookup"><span data-stu-id="53cb0-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="53cb0-110">Der Befehl `mlnet auto-train` generiert folgende Objekte:</span><span class="sxs-lookup"><span data-stu-id="53cb0-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="53cb0-111">Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="53cb0-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="53cb0-112">C#-Code zum Ausführen/Bewerten des generierten Modells.</span><span class="sxs-lookup"><span data-stu-id="53cb0-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="53cb0-113">C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53cb0-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="53cb0-114">Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem Modell Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="53cb0-115">Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie den spezifischen Algorithmus und die Einstellungen des Modells untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="53cb0-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="53cb0-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="53cb0-116">Examples</span></span>

<span data-ttu-id="53cb0-117">Der einfachste CLI-Befehl für ein binäres Klassifizierungsproblem (AutoML leitet den Großteil der Konfiguration aus den bereitgestellten Daten ab):</span><span class="sxs-lookup"><span data-stu-id="53cb0-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="53cb0-118">Ein weiterer einfacher CLI-Befehl für ein Regressionsproblem:</span><span class="sxs-lookup"><span data-stu-id="53cb0-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="53cb0-119">Erstellen und trainieren Sie ein binäres Klassifizierungsmodell mit einem Trainingsdataset, einem Testdataset und weiteren benutzerdefinierten Argumenten:</span><span class="sxs-lookup"><span data-stu-id="53cb0-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="53cb0-120">Befehlsoptionen</span><span class="sxs-lookup"><span data-stu-id="53cb0-120">Command options</span></span>

<span data-ttu-id="53cb0-121">`mlnet auto-train`: Trainiert mehrere Modelle basierend auf dem bereitgestellten Dataset und wählt schließlich das beste Modell aus, speichert es als serialisierte ZIP-Datei und generiert außerdem den zugehörigen C#-Code für Bewertung und Training.</span><span class="sxs-lookup"><span data-stu-id="53cb0-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

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

<span data-ttu-id="53cb0-122">Ungültige Eingabeoptionen bewirken, dass das CLI-Tool eine Liste gültiger Eingaben und eine Fehlermeldung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="53cb0-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="53cb0-123">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="53cb0-123">Task</span></span>

<span data-ttu-id="53cb0-124">`--task | --mltask | -T` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="53cb0-125">Eine einzelne Zeichenfolge, die das zu lösende ML-Problem enthält.</span><span class="sxs-lookup"><span data-stu-id="53cb0-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="53cb0-126">Zum Beispiel eine der folgenden Aufgaben (die CLI wird später alle in AutoML unterstützten Aufgaben unterstützen):</span><span class="sxs-lookup"><span data-stu-id="53cb0-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="53cb0-127">`regression` – Wählen Sie, ob das ML-Modell zur Vorhersage eines numerischen Werts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="53cb0-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="53cb0-128">`binary-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).</span><span class="sxs-lookup"><span data-stu-id="53cb0-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="53cb0-129">`multiclass-classification` –Wählen Sie, ob das Ergebnis des ML-Modells zwei mögliche kategorische boolesche Werte hat (0 oder 1).</span><span class="sxs-lookup"><span data-stu-id="53cb0-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="53cb0-130">In diesem Argument sollte nur eine ML-Aufgabe bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="53cb0-131">DataSet</span><span class="sxs-lookup"><span data-stu-id="53cb0-131">Dataset</span></span>

<span data-ttu-id="53cb0-132">`--dataset | -d` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="53cb0-133">Dieses Argument stellt den Dateipfad zu einer der folgenden Optionen bereit:</span><span class="sxs-lookup"><span data-stu-id="53cb0-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="53cb0-134">*A: Die gesamte Datasetdatei:* Wenn Sie diese Option verwenden und der Benutzer das `--test-dataset` und das `--validation-dataset` nicht bereitstellt, werden intern Kreuzvalidierungen (k-fach, etc.) oder automatisierte Verfahren zur Aufteilung das Daten für die Validierung des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="53cb0-135">In diesem Fall muss der Benutzer nur den Dateipfad zum Dataset angeben.</span><span class="sxs-lookup"><span data-stu-id="53cb0-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="53cb0-136">*B: Die Datei für das Trainingsdataset:* Wenn der Benutzer auch Datasets für die Modellvalidierung bereitstellt (mit `--test-dataset` und optional `--validation-dataset`), dann bedeutet das Argument `--dataset`, dass nur das „Trainingsdataset“ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="53cb0-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="53cb0-137">Wenn Sie beispielsweise 80%-20%ig-Ansatz zur Validierung der Modellqualität und zum Ermitteln von Genauigkeitsmetriken verwenden, enthält das „Trainingsdataset“ 80 % der Daten und das „Testdataset“ 20 % der Daten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="53cb0-138">Testdataset</span><span class="sxs-lookup"><span data-stu-id="53cb0-138">Test dataset</span></span>

<span data-ttu-id="53cb0-139">`--test-dataset | -t` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="53cb0-140">Dateipfad, der auf die Datei des Testdatasets zeigt, z.B. bei Verwendung eines 80%-20%-Ansatzes bei regelmäßigen Validierungen zur Ermittlung von Genauigkeitsmetriken.</span><span class="sxs-lookup"><span data-stu-id="53cb0-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="53cb0-141">Bei der Verwendung des `--test-dataset` ist auch das `--dataset` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53cb0-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="53cb0-142">Das `--test-dataset`-Argument ist optional, sofern das „--validation-dataset“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53cb0-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="53cb0-143">In diesem Fall muss der Benutzer die drei Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="53cb0-144">Validierungsdataset</span><span class="sxs-lookup"><span data-stu-id="53cb0-144">Validation dataset</span></span>

<span data-ttu-id="53cb0-145">`--validation-dataset | -v` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="53cb0-146">Dateipfad, der auf die Datei für das Validierungsdataset zeigt.</span><span class="sxs-lookup"><span data-stu-id="53cb0-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="53cb0-147">Das Validierungsdataset ist in jedem Fall optional.</span><span class="sxs-lookup"><span data-stu-id="53cb0-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="53cb0-148">Bei der Verwendung des `validation dataset` sollte folgendes Verhalten auftreten:</span><span class="sxs-lookup"><span data-stu-id="53cb0-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="53cb0-149">Es sind auch die `test-dataset`- und `--dataset`-Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="53cb0-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="53cb0-150">Das `validation-dataset`-Dataset wird verwendet, um den Vorhersagefehler für die Modellauswahl zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="53cb0-151">Das `test-dataset` wird zur Beurteilung des Generalisierungsfehlers des endgültig ausgewählten Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="53cb0-152">Idealerweise sollte das Testset in einem „Tresor“ aufbewahrt werden und erst am Ende der Datenanalyse zur Anwendung kommen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="53cb0-153">Grundsätzlich wird bei die Validierungsphase bei Verwendung eines `validation dataset` plus des `test dataset` in zwei Teile aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="53cb0-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="53cb0-154">Im ersten Teil betrachten Sie einfach Ihre Modelle und wählen den leistungsstärksten Ansatz anhand der Validierungsdaten (=Validierung) aus.</span><span class="sxs-lookup"><span data-stu-id="53cb0-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="53cb0-155">Dann schätzen Sie die Genauigkeit des gewählten Ansatzes (=Test).</span><span class="sxs-lookup"><span data-stu-id="53cb0-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="53cb0-156">Daher sollten die Daten im Verhältnis 80/10/10 oder 75/15/10 geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="53cb0-157">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53cb0-157">For example:</span></span>

- <span data-ttu-id="53cb0-158">Die Datei `training-dataset` sollte 75 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="53cb0-159">Die Datei `validation-dataset` sollte 15 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="53cb0-160">Die Datei `test-dataset` sollte 10 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="53cb0-161">In jedem Fall entscheidet der Benutzer anhand der CLI, die die bereits aufgeteilten Dateien bereitstellt, über die Prozentangaben.</span><span class="sxs-lookup"><span data-stu-id="53cb0-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="53cb0-162">Bezeichnung Spaltenname</span><span class="sxs-lookup"><span data-stu-id="53cb0-162">Label column name</span></span>

<span data-ttu-id="53cb0-163">`--label-column-name | -n` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="53cb0-164">Mit diesem Argument kann eine bestimmte Objekt-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem der Name der Spalte im Header des Datasets verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="53cb0-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="53cb0-165">Dieses Argument wird nur für überwachte ML-Aufgaben verwendet, wie z.B. ein *Klassifizierungsproblem*.</span><span class="sxs-lookup"><span data-stu-id="53cb0-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="53cb0-166">Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.</span><span class="sxs-lookup"><span data-stu-id="53cb0-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="53cb0-167">Bezeichnung Spaltenindex</span><span class="sxs-lookup"><span data-stu-id="53cb0-167">Label column index</span></span>

<span data-ttu-id="53cb0-168">`--label-column-index | -i` (Ganzzahl)</span><span class="sxs-lookup"><span data-stu-id="53cb0-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="53cb0-169">Mit diesem Argument kann eine bestimmte Ziel-/Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem Sie den numerischen Index der Spalte in der Datasetdatei verwenden (Spaltenindexwerte beginnen bei 1).</span><span class="sxs-lookup"><span data-stu-id="53cb0-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="53cb0-170">*Hinweis*: Wenn der Benutzer auch `--label-column-name` verwendet, wird `--label-column-name` verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="53cb0-171">Dieses Argument wird nur für eine überwachte ML-Aufgabe verwendet, wie z.B. ein *Klassifizierungsproblem*.</span><span class="sxs-lookup"><span data-stu-id="53cb0-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="53cb0-172">Es kann nicht für nicht überwachte ML-Aufgaben verwendet werden, wie z.B. *Clustering*.</span><span class="sxs-lookup"><span data-stu-id="53cb0-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="53cb0-173">Spalten ignorieren</span><span class="sxs-lookup"><span data-stu-id="53cb0-173">Ignore columns</span></span>

<span data-ttu-id="53cb0-174">`--ignore-columns | -I` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="53cb0-175">Mit diesem Argument können Sie vorhandene Spalten in der Datasetdatei ignorieren, sodass sie nicht geladen und nicht in den Trainingsprozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="53cb0-176">Geben Sie die Namen der Spalten an, die Sie ignorieren möchten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="53cb0-177">Verwenden Sie „, „ (Komma mit Leerzeichen) oder „ „ (Leerzeichen), um mehrere Spaltennamen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="53cb0-178">Sie können Anführungszeichen für Spaltennamen verwenden, die Leerzeichen enthalten (z.B. „ist angemeldet“).</span><span class="sxs-lookup"><span data-stu-id="53cb0-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="53cb0-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="53cb0-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="53cb0-180">Hat Header</span><span class="sxs-lookup"><span data-stu-id="53cb0-180">Has header</span></span>

<span data-ttu-id="53cb0-181">`--has-header | -h` (Bool)</span><span class="sxs-lookup"><span data-stu-id="53cb0-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="53cb0-182">Geben Sie an, ob die Datasetdatei(en) eine Kopfzeile enthält/enthalten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="53cb0-183">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="53cb0-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="53cb0-184">Der Standardwert ist `true`, wenn der Benutzer dieses Argument nicht angibt.</span><span class="sxs-lookup"><span data-stu-id="53cb0-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="53cb0-185">Um das `--label-column-name`-Argument zu verwenden, benötigen Sie in der Datasetdatei einen Header und `--has-header` muss auf `true` (Standardwert) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="53cb0-186">Maximale Auswertungszeit</span><span class="sxs-lookup"><span data-stu-id="53cb0-186">Max exploration time</span></span>

<span data-ttu-id="53cb0-187">`--max-exploration-time | -x` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="53cb0-188">Die maximale Untersuchungszeit beträgt standardmäßig 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="53cb0-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="53cb0-189">Dieses Argument legt die maximale Zeit (in Sekunden) für den Prozess fest, um mehrere Trainer und Konfigurationen zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="53cb0-190">Die konfigurierte Zeit kann überschritten werden, wenn die angegebene Zeit für eine einzelne Iteration zu kurz ist (z.B. 2 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="53cb0-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="53cb0-191">In diesem Fall ist die tatsächliche Zeit die erforderliche Zeit, um eine Modellkonfiguration in einer einzigen Iteration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="53cb0-192">Die für Iterationen benötigte Zeit kann je nach Größe des Datasets variieren.</span><span class="sxs-lookup"><span data-stu-id="53cb0-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="53cb0-193">cache</span><span class="sxs-lookup"><span data-stu-id="53cb0-193">Cache</span></span>

<span data-ttu-id="53cb0-194">`--cache | -c` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="53cb0-195">Wenn Sie Caching verwenden, wird das gesamte Trainingsdataset im Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="53cb0-196">Bei kleinen und mittleren Datasets kann Caching die Trainingsleistung erheblich verbessern, sodass die Trainingszeit im Vergleich zu einem Training ohne Cache kürzer sein kann.</span><span class="sxs-lookup"><span data-stu-id="53cb0-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="53cb0-197">Bei großen Datasets kann das Laden aller Daten im Speicher jedoch negative Auswirkungen haben, da Sie unter Umständen nicht mehr genügend Speicher zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="53cb0-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="53cb0-198">Wenn Sie für das Training mit großen Datasetdateien arbeiten und keinen Cache verwenden, streamt ML.NET Datenblöcke vom Laufwerk, wenn während des Trainings mehr Daten geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="53cb0-199">Sie können folgende Werte angeben:</span><span class="sxs-lookup"><span data-stu-id="53cb0-199">You can specify the following values:</span></span>

<span data-ttu-id="53cb0-200">`on`: Erzwingt, dass während des Trainings der Cache verwendet wird</span><span class="sxs-lookup"><span data-stu-id="53cb0-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="53cb0-201">`off`: Erzwingt, dass während des Trainings der Cache nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="53cb0-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="53cb0-202">`auto`: Je nach AutoML-Heuristiken wird der Cache verwendet oder nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="53cb0-203">In der Regel verwenden kleine/mittlere Datasets den Cache, und große Datasets verwenden keinen Cache, wenn Sie die Option `auto` verwenden.</span><span class="sxs-lookup"><span data-stu-id="53cb0-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="53cb0-204">Wenn Sie den `--cache`-Parameter nicht angeben, wird standardmäßig die Cachekonfiguration `auto` verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="53cb0-205">name</span><span class="sxs-lookup"><span data-stu-id="53cb0-205">Name</span></span>

<span data-ttu-id="53cb0-206">`--name | -N` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-206">`--name | -N` (string)</span></span>

<span data-ttu-id="53cb0-207">Der Name für das erstellte Ausgabeprojekt oder die erstellte Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="53cb0-207">The name for the created output project or solution.</span></span> <span data-ttu-id="53cb0-208">Wenn kein Name angegeben ist, wird der Name `sample-{mltask}` verwendet.</span><span class="sxs-lookup"><span data-stu-id="53cb0-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="53cb0-209">Die ML.NET-Modelldatei (ZIP-Datei) erhält ebenfalls denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="53cb0-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="53cb0-210">Ausgabepfad</span><span class="sxs-lookup"><span data-stu-id="53cb0-210">Output path</span></span>

<span data-ttu-id="53cb0-211">`--output-path | -o` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="53cb0-212">Stammspeicherort/-ordner für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="53cb0-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="53cb0-213">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="53cb0-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="53cb0-214">Ausführlichkeit</span><span class="sxs-lookup"><span data-stu-id="53cb0-214">Verbosity</span></span>

<span data-ttu-id="53cb0-215">`--verbosity | -V` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="53cb0-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="53cb0-216">Legt den Ausführlichkeitsgrad für die Standardausgabe fest.</span><span class="sxs-lookup"><span data-stu-id="53cb0-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="53cb0-217">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="53cb0-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="53cb0-218">`m[inimal]` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="53cb0-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="53cb0-219">`diag[nostic]` (Protokollierung der Informationsebene)</span><span class="sxs-lookup"><span data-stu-id="53cb0-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="53cb0-220">Standardmäßig sollte das CLI-Tool ein Mindestfeedback (minimal) anzeigen, wenn es funktioniert, wie z.B. die Angabe, dass es funktioniert und, wenn möglich, Angaben dazu, wie viel Zeit übrig ist oder wie viel Prozent der Zeit abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="53cb0-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="53cb0-221">Hilfe</span><span class="sxs-lookup"><span data-stu-id="53cb0-221">Help</span></span>

`-h|--help`

<span data-ttu-id="53cb0-222">Druckt die Hilfe für den Befehl und eine Beschreibung der einzelnen Parameter für den Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="53cb0-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="53cb0-223">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53cb0-223">See also</span></span>

- [<span data-ttu-id="53cb0-224">Vorgehensweise: Installieren des ML.NET-CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="53cb0-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="53cb0-225">Übersicht über die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="53cb0-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="53cb0-226">Tutorial: Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="53cb0-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="53cb0-227">Telemetrie in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="53cb0-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
