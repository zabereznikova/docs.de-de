---
title: Befehlsreferenz für die ML.NET-CLI
description: Übersicht, Beispiele und Verweise für den Befehl „auto-train“ im ML.NET-CLI-Tool
ms.date: 06/03/2020
ms.custom: mlnet-tooling
ms.openlocfilehash: 6f07cd8b4237f8931bbc0ec97bc0bbe18c488f16
ms.sourcegitcommit: e395fabeeea5c705d243d246fa64446839ac85b6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2021
ms.locfileid: "97856067"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="4e15e-103">Befehlsreferenz für die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="4e15e-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="4e15e-104">Die Befehle `classification`, `regression` und `recommendation` sind die Hauptbefehle, die vom ML.NET-CLI-Tool bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-104">The `classification`, `regression`, and `recommendation` commands are the main commands provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="4e15e-105">Mit diesen Befehlen können Sie ein qualitativ hochwertiges ML.NET-Modell für Klassifizierungs-, Regressions- und Empfehlungsmodelle mithilfe von automatisiertem maschinellen Lernen (AutoML) sowie den C#-Beispielcode generieren, um dieses Modell auszuführen bzw. zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-105">These commands allow you to generate good quality ML.NET models for classification, regression, and recommendation models using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="4e15e-106">Außerdem wird der C#-Code zum Trainieren des Modells für Sie generiert, damit Sie den Algorithmus und die Einstellungen des Modells untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="4e15e-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="4e15e-107">Dieses Thema bezieht sich auf die ML.NET-CLI und ML.NET AutoML, die derzeit als Vorschau verfügbar sind, und das Material kann jederzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="4e15e-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4e15e-108">Overview</span></span>

<span data-ttu-id="4e15e-109">Verwendungsbeispiel:</span><span class="sxs-lookup"><span data-stu-id="4e15e-109">Example usage:</span></span>

```console
mlnet regression --dataset "cars.csv" --label-col price
```

<span data-ttu-id="4e15e-110">Mit den `mlnet`-Befehlen für ML-Tasks (`classification`, `regression` und `recommendation`) werden die folgenden Objekte generiert:</span><span class="sxs-lookup"><span data-stu-id="4e15e-110">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) generate the following assets:</span></span>

- <span data-ttu-id="4e15e-111">Eine serialisierte ZIP-Datei des Modells („bestes Modell“), die sofort verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4e15e-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="4e15e-112">C#-Code zum Ausführen/Bewerten des generierten Modells.</span><span class="sxs-lookup"><span data-stu-id="4e15e-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="4e15e-113">C#-Code mit dem Trainingscode, der zur Erstellung dieses Modells verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e15e-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="4e15e-114">Die ersten beiden Objekte können direkt in Ihren Endbenutzer-App (ASP.NET Core-Web-App, Dienste, Desktop-App usw.) verwendet werden, um mit dem Modell Vorhersagen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="4e15e-115">Das dritte Objekt, der Trainingscode, zeigt Ihnen, welchen ML.NET-API-Code die CLI zum Trainieren des generierten Modells verwendet hat, sodass Sie den spezifischen Algorithmus und die Einstellungen des Modells untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="4e15e-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="4e15e-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4e15e-116">Examples</span></span>

<span data-ttu-id="4e15e-117">Der einfachste CLI-Befehl für ein Klassifizierungsproblem (AutoML leitet den Großteil der Konfiguration aus den bereitgestellten Daten ab):</span><span class="sxs-lookup"><span data-stu-id="4e15e-117">The simplest CLI command for a classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet classification --dataset "customer-feedback.tsv" --label-col Sentiment
```

<span data-ttu-id="4e15e-118">Ein weiterer einfacher CLI-Befehl für ein Regressionsproblem:</span><span class="sxs-lookup"><span data-stu-id="4e15e-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet regression --dataset "cars.csv" --label-col Price
```

<span data-ttu-id="4e15e-119">Erstellen und trainieren Sie ein Klassifizierungsmodell mit einem Trainingsdataset, einem Testdataset und weiteren expliziten Anpassungsargumenten:</span><span class="sxs-lookup"><span data-stu-id="4e15e-119">Create and train a classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-col "InsuranceRisk" --cache on --train-time 600
```

## <a name="command-options"></a><span data-ttu-id="4e15e-120">Befehlsoptionen</span><span class="sxs-lookup"><span data-stu-id="4e15e-120">Command options</span></span>

<span data-ttu-id="4e15e-121">Die `mlnet`-Befehle für ML-Tasks (`classification`, `regression` und `recommendation`) trainieren mehrere Modelle basierend auf dem bereitgestellten Dataset und den bereitgestellten ML.NET-CLI-Optionen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-121">The `mlnet` ML task commands (`classification`, `regression`, and `recommendation`) train multiple models based on the provided dataset and ML.NET CLI options.</span></span> <span data-ttu-id="4e15e-122">Diese Befehle wählen außerdem das beste Modell aus, speichern das Modell als serialisierte ZIP-Datei und generieren zugehörigen C#-Code für die Bewertung und das Training.</span><span class="sxs-lookup"><span data-stu-id="4e15e-122">These commands also select the best model, save the model as a serialized .zip file, and generate related C# code for scoring and training.</span></span>

### <a name="classification-options"></a><span data-ttu-id="4e15e-123">Klassifizierungsoptionen</span><span class="sxs-lookup"><span data-stu-id="4e15e-123">Classification options</span></span>

<span data-ttu-id="4e15e-124">Durch das Ausführen von `mlnet classification` wird ein Klassifizierungsmodell trainiert.</span><span class="sxs-lookup"><span data-stu-id="4e15e-124">Running `mlnet classification` will train a classification model.</span></span> <span data-ttu-id="4e15e-125">Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell Daten in mindestens zwei Klassen kategorisiert (z. B. bei der Standpunktanalyse).</span><span class="sxs-lookup"><span data-stu-id="4e15e-125">Choose this command if you want an ML Model to categorize data into 2 or more classes (e.g. sentiment analysis).</span></span>

```console
mlnet classification

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="regression-options"></a><span data-ttu-id="4e15e-126">Regressionsoptionen</span><span class="sxs-lookup"><span data-stu-id="4e15e-126">Regression options</span></span>

<span data-ttu-id="4e15e-127">Durch das Ausführen von `mlnet regression` wird ein Regressionsmodell trainiert.</span><span class="sxs-lookup"><span data-stu-id="4e15e-127">Running `mlnet regression` will train a regression model.</span></span> <span data-ttu-id="4e15e-128">Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell einen numerischen Wert vorhersagt (z. B. Preisvorhersage).</span><span class="sxs-lookup"><span data-stu-id="4e15e-128">Choose this command if you want an ML Model to predict a numeric value (e.g. price prediction).</span></span>

```console
mlnet regression

--dataset <path> (REQUIRED)

--label-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--ignore-cols <cols>

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

### <a name="recommendation-options"></a><span data-ttu-id="4e15e-129">Empfehlungsoptionen</span><span class="sxs-lookup"><span data-stu-id="4e15e-129">Recommendation options</span></span>

<span data-ttu-id="4e15e-130">Durch das Ausführen von `mlnet recommendation` wird ein Empfehlungsmodell trainiert.</span><span class="sxs-lookup"><span data-stu-id="4e15e-130">Running `mlnet recommendation` will train a recommendation model.</span></span>  <span data-ttu-id="4e15e-131">Wählen Sie diesen Befehl aus, wenn Sie möchten, dass ein ML-Modell Benutzern Artikel auf der Grundlage von Bewertungen (z. B. Produktempfehlungen) empfiehlt.</span><span class="sxs-lookup"><span data-stu-id="4e15e-131">Choose this command if you want an ML Model to recommend items to users based on ratings (e.g. product recommendation).</span></span>

```console
mlnet recommendation

--dataset <path> (REQUIRED)

--item-col <col> (REQUIRED)

--rating-col <col> (REQUIRED)

--user-col <col> (REQUIRED)

--cache <option>

--has-header (Default: true)

--log-file-path <path>

--name <name>

-o, --output <path>

--test-dataset <path>

--train-time <time> (Default: 30 minutes, in seconds)

--validation-dataset <path>

-v, --verbosity <v>

-?, -h, --help

```

<span data-ttu-id="4e15e-132">Ungültige Eingabeoptionen bewirken, dass das CLI-Tool eine Liste gültiger Eingaben und eine Fehlermeldung ausgibt.</span><span class="sxs-lookup"><span data-stu-id="4e15e-132">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="dataset"></a><span data-ttu-id="4e15e-133">DataSet</span><span class="sxs-lookup"><span data-stu-id="4e15e-133">Dataset</span></span>

<span data-ttu-id="4e15e-134">`--dataset | -d` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-134">`--dataset | -d` (string)</span></span>

<span data-ttu-id="4e15e-135">Dieses Argument stellt den Dateipfad zu einer der folgenden Optionen bereit:</span><span class="sxs-lookup"><span data-stu-id="4e15e-135">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="4e15e-136">*A: Die gesamte Datasetdatei:* Wenn Sie diese Option verwenden und der Benutzer das `--test-dataset` und das `--validation-dataset` nicht bereitstellt, werden intern Kreuzvalidierungen (k-fach, etc.) oder automatisierte Verfahren zur Aufteilung das Daten für die Validierung des Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-136">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="4e15e-137">In diesem Fall muss der Benutzer nur den Dateipfad zum Dataset angeben.</span><span class="sxs-lookup"><span data-stu-id="4e15e-137">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="4e15e-138">*B: Die Datei für das Trainingsdataset:* Wenn der Benutzer auch Datasets für die Modellvalidierung bereitstellt (mit `--test-dataset` und optional `--validation-dataset`), dann bedeutet das Argument `--dataset`, dass nur das „Trainingsdataset“ vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4e15e-138">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="4e15e-139">Wenn Sie beispielsweise 80%-20%ig-Ansatz zur Validierung der Modellqualität und zum Ermitteln von Genauigkeitsmetriken verwenden, enthält das „Trainingsdataset“ 80 % der Daten und das „Testdataset“ 20 % der Daten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-139">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="4e15e-140">Testdataset</span><span class="sxs-lookup"><span data-stu-id="4e15e-140">Test dataset</span></span>

<span data-ttu-id="4e15e-141">`--test-dataset | -t` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-141">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="4e15e-142">Dateipfad, der auf die Datei des Testdatasets zeigt, z.B. bei Verwendung eines 80%-20%-Ansatzes bei regelmäßigen Validierungen zur Ermittlung von Genauigkeitsmetriken.</span><span class="sxs-lookup"><span data-stu-id="4e15e-142">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="4e15e-143">Bei der Verwendung des `--test-dataset` ist auch das `--dataset` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e15e-143">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="4e15e-144">Das `--test-dataset`-Argument ist optional, sofern das „--validation-dataset“ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e15e-144">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="4e15e-145">In diesem Fall muss der Benutzer die drei Argumente verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-145">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="4e15e-146">Validierungsdataset</span><span class="sxs-lookup"><span data-stu-id="4e15e-146">Validation dataset</span></span>

<span data-ttu-id="4e15e-147">`--validation-dataset | -v` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-147">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="4e15e-148">Dateipfad, der auf die Datei für das Validierungsdataset zeigt.</span><span class="sxs-lookup"><span data-stu-id="4e15e-148">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="4e15e-149">Das Validierungsdataset ist in jedem Fall optional.</span><span class="sxs-lookup"><span data-stu-id="4e15e-149">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="4e15e-150">Bei der Verwendung des `validation dataset` sollte folgendes Verhalten auftreten:</span><span class="sxs-lookup"><span data-stu-id="4e15e-150">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="4e15e-151">Es sind auch die `test-dataset`- und `--dataset`-Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e15e-151">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="4e15e-152">Das `validation-dataset`-Dataset wird verwendet, um den Vorhersagefehler für die Modellauswahl zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-152">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="4e15e-153">Das `test-dataset` wird zur Beurteilung des Generalisierungsfehlers des endgültig ausgewählten Modells verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-153">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="4e15e-154">Idealerweise sollte das Testset in einem „Tresor“ aufbewahrt werden und erst am Ende der Datenanalyse zur Anwendung kommen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-154">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="4e15e-155">Grundsätzlich wird bei die Validierungsphase bei Verwendung eines `validation dataset` plus des `test dataset` in zwei Teile aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="4e15e-155">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="4e15e-156">Im ersten Teil betrachten Sie einfach Ihre Modelle und wählen den leistungsstärksten Ansatz anhand der Validierungsdaten (=Validierung) aus.</span><span class="sxs-lookup"><span data-stu-id="4e15e-156">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="4e15e-157">Dann schätzen Sie die Genauigkeit des gewählten Ansatzes (=Test).</span><span class="sxs-lookup"><span data-stu-id="4e15e-157">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="4e15e-158">Daher sollten die Daten im Verhältnis 80/10/10 oder 75/15/10 geteilt werden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-158">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="4e15e-159">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e15e-159">For example:</span></span>

- <span data-ttu-id="4e15e-160">Die Datei `training-dataset` sollte 75 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-160">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="4e15e-161">Die Datei `validation-dataset` sollte 15 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-161">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="4e15e-162">Die Datei `test-dataset` sollte 10 % der Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-162">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="4e15e-163">In jedem Fall entscheidet der Benutzer anhand der CLI, die die bereits aufgeteilten Dateien bereitstellt, über die Prozentangaben.</span><span class="sxs-lookup"><span data-stu-id="4e15e-163">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column"></a><span data-ttu-id="4e15e-164">Bezeichnungsspalte</span><span class="sxs-lookup"><span data-stu-id="4e15e-164">Label column</span></span>

<span data-ttu-id="4e15e-165">`--label-col` (ganze Zahl oder Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-165">`--label-col` (int or string)</span></span>

<span data-ttu-id="4e15e-166">Mit diesem Argument kann eine bestimmte Zielspalte (die Variable, die Sie vorhersagen möchten) angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-166">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="4e15e-167">Dieses Argument wird für Probleme bei der *Klassifizierung* und der *Regression* verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-167">This argument is used for *classification* and *regression* problems.</span></span>

## <a name="item-column"></a><span data-ttu-id="4e15e-168">Artikelspalte</span><span class="sxs-lookup"><span data-stu-id="4e15e-168">Item column</span></span>

<span data-ttu-id="4e15e-169">`--item-col` (ganze Zahl oder Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-169">`--item-col` (int or string)</span></span>

<span data-ttu-id="4e15e-170">Die Artikelspalte enthält die Liste der Artikel, die von Benutzern bewertet werden (Artikel werden Benutzern empfohlen).</span><span class="sxs-lookup"><span data-stu-id="4e15e-170">The item column has the list of items that users rate (items are recommended to users).</span></span> <span data-ttu-id="4e15e-171">Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-171">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="4e15e-172">Dieses Argument wird nur für den *Empfehlungstask* verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-172">This argument is used only for the *recommendation* task.</span></span>

## <a name="rating-column"></a><span data-ttu-id="4e15e-173">Bewertungsspalte</span><span class="sxs-lookup"><span data-stu-id="4e15e-173">Rating column</span></span>

<span data-ttu-id="4e15e-174">`--rating-col` (ganze Zahl oder Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-174">`--rating-col` (int or string)</span></span>

<span data-ttu-id="4e15e-175">Die Bewertungsspalte enthält die Liste der Bewertungen, die Benutzer für Artikel abgeben.</span><span class="sxs-lookup"><span data-stu-id="4e15e-175">The rating column has the list of ratings that are given to items by users.</span></span> <span data-ttu-id="4e15e-176">Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-176">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="4e15e-177">Dieses Argument wird nur für den *Empfehlungstask* verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-177">This argument is used only for the *recommendation* task.</span></span>

## <a name="user-column"></a><span data-ttu-id="4e15e-178">Benutzerspalte</span><span class="sxs-lookup"><span data-stu-id="4e15e-178">User column</span></span>

<span data-ttu-id="4e15e-179">`--user-col` (ganze Zahl oder Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-179">`--user-col` (int or string)</span></span>

<span data-ttu-id="4e15e-180">Die Benutzerspalte enthält die Liste der Benutzer, die Bewertungen für Artikel abgeben.</span><span class="sxs-lookup"><span data-stu-id="4e15e-180">The user column has the list of users that give ratings to items.</span></span> <span data-ttu-id="4e15e-181">Diese Spalte kann angegeben werden, indem Sie den im Header des Dataset festgelegten Namen der Spalte oder den numerischen Index der Spalte in der Datasetdatei (Spaltenindexwerte beginnen bei 0) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-181">This column can be specified by using the column's name set in the dataset's header or the column's numeric index in the dataset's file (the column index values start at 0).</span></span>

<span data-ttu-id="4e15e-182">Dieses Argument wird nur für den *Empfehlungstask* verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-182">This argument is used only for the *recommendation* task.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="4e15e-183">Spalten ignorieren</span><span class="sxs-lookup"><span data-stu-id="4e15e-183">Ignore columns</span></span>

<span data-ttu-id="4e15e-184">`--ignore-columns` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-184">`--ignore-columns` (string)</span></span>

<span data-ttu-id="4e15e-185">Mit diesem Argument können Sie vorhandene Spalten in der Datasetdatei ignorieren, sodass sie nicht geladen und nicht in den Trainingsprozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-185">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="4e15e-186">Geben Sie die Namen der Spalten an, die Sie ignorieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-186">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="4e15e-187">Verwenden Sie „, „ (Komma mit Leerzeichen) oder „ „ (Leerzeichen), um mehrere Spaltennamen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-187">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="4e15e-188">Sie können Anführungszeichen für Spaltennamen verwenden, die Leerzeichen enthalten (z.B. „ist angemeldet“).</span><span class="sxs-lookup"><span data-stu-id="4e15e-188">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="4e15e-189">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e15e-189">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="4e15e-190">Hat Header</span><span class="sxs-lookup"><span data-stu-id="4e15e-190">Has header</span></span>

<span data-ttu-id="4e15e-191">`--has-header` (Bool)</span><span class="sxs-lookup"><span data-stu-id="4e15e-191">`--has-header` (bool)</span></span>

<span data-ttu-id="4e15e-192">Geben Sie an, ob die Datasetdatei(en) eine Kopfzeile enthält/enthalten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-192">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="4e15e-193">Dabei sind folgende Werte möglich:</span><span class="sxs-lookup"><span data-stu-id="4e15e-193">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="4e15e-194">Die ML.NET-CLI versucht, diese Eigenschaft zu erkennen, wenn dieses Argument vom Benutzer nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4e15e-194">The ML.NET CLI will try to detect this property if this argument is not specified by the user.</span></span>

## <a name="train-time"></a><span data-ttu-id="4e15e-195">Trainingszeit</span><span class="sxs-lookup"><span data-stu-id="4e15e-195">Train time</span></span>

<span data-ttu-id="4e15e-196">`--train-time` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-196">`--train-time` (string)</span></span>

<span data-ttu-id="4e15e-197">Die maximale Untersuchungs-/Trainingszeit beträgt standardmäßig 30 Minuten.</span><span class="sxs-lookup"><span data-stu-id="4e15e-197">By default, the maximum exploration / train time is 30 minutes.</span></span>

<span data-ttu-id="4e15e-198">Dieses Argument legt die maximale Zeit (in Sekunden) für den Prozess fest, um mehrere Trainer und Konfigurationen zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-198">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="4e15e-199">Die konfigurierte Zeit kann überschritten werden, wenn die angegebene Zeit für eine einzelne Iteration zu kurz ist (z.B. 2 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="4e15e-199">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="4e15e-200">In diesem Fall ist die tatsächliche Zeit die erforderliche Zeit, um eine Modellkonfiguration in einer einzigen Iteration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-200">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="4e15e-201">Die für Iterationen benötigte Zeit kann je nach Größe des Datasets variieren.</span><span class="sxs-lookup"><span data-stu-id="4e15e-201">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="4e15e-202">cache</span><span class="sxs-lookup"><span data-stu-id="4e15e-202">Cache</span></span>

<span data-ttu-id="4e15e-203">`--cache` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-203">`--cache` (string)</span></span>

<span data-ttu-id="4e15e-204">Wenn Sie Caching verwenden, wird das gesamte Trainingsdataset im Speicher geladen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-204">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="4e15e-205">Bei kleinen und mittleren Datasets kann Caching die Trainingsleistung erheblich verbessern, sodass die Trainingszeit im Vergleich zu einem Training ohne Cache kürzer sein kann.</span><span class="sxs-lookup"><span data-stu-id="4e15e-205">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="4e15e-206">Bei großen Datasets kann das Laden aller Daten im Speicher jedoch negative Auswirkungen haben, da Sie unter Umständen nicht mehr genügend Speicher zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="4e15e-206">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="4e15e-207">Wenn Sie für das Training mit großen Datasetdateien arbeiten und keinen Cache verwenden, streamt ML.NET Datenblöcke vom Laufwerk, wenn während des Trainings mehr Daten geladen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-207">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="4e15e-208">Sie können folgende Werte angeben:</span><span class="sxs-lookup"><span data-stu-id="4e15e-208">You can specify the following values:</span></span>

<span data-ttu-id="4e15e-209">`on`: Erzwingt, dass während des Trainings der Cache verwendet wird</span><span class="sxs-lookup"><span data-stu-id="4e15e-209">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="4e15e-210">`off`: Erzwingt, dass während des Trainings der Cache nicht verwendet wird</span><span class="sxs-lookup"><span data-stu-id="4e15e-210">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="4e15e-211">`auto`: Je nach AutoML-Heuristiken wird der Cache verwendet oder nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-211">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="4e15e-212">In der Regel verwenden kleine/mittlere Datasets den Cache, und große Datasets verwenden keinen Cache, wenn Sie die Option `auto` verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e15e-212">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="4e15e-213">Wenn Sie den `--cache`-Parameter nicht angeben, wird standardmäßig die Cachekonfiguration `auto` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-213">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="4e15e-214">name</span><span class="sxs-lookup"><span data-stu-id="4e15e-214">Name</span></span>

<span data-ttu-id="4e15e-215">`--name` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-215">`--name` (string)</span></span>

<span data-ttu-id="4e15e-216">Der Name für das erstellte Ausgabeprojekt oder die erstellte Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="4e15e-216">The name for the created output project or solution.</span></span> <span data-ttu-id="4e15e-217">Wenn kein Name angegeben ist, wird der Name `sample-{mltask}` verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e15e-217">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="4e15e-218">Die ML.NET-Modelldatei (ZIP-Datei) erhält ebenfalls denselben Namen.</span><span class="sxs-lookup"><span data-stu-id="4e15e-218">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="4e15e-219">Ausgabepfad</span><span class="sxs-lookup"><span data-stu-id="4e15e-219">Output path</span></span>

<span data-ttu-id="4e15e-220">`--output | -o` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-220">`--output | -o` (string)</span></span>

<span data-ttu-id="4e15e-221">Stammspeicherort/-ordner für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4e15e-221">Root location/folder to place the generated output.</span></span> <span data-ttu-id="4e15e-222">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4e15e-222">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="4e15e-223">Ausführlichkeit</span><span class="sxs-lookup"><span data-stu-id="4e15e-223">Verbosity</span></span>

<span data-ttu-id="4e15e-224">`--verbosity | -v` (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="4e15e-224">`--verbosity | -v` (string)</span></span>

<span data-ttu-id="4e15e-225">Legt den Ausführlichkeitsgrad für die Standardausgabe fest.</span><span class="sxs-lookup"><span data-stu-id="4e15e-225">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="4e15e-226">Zulässige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4e15e-226">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="4e15e-227">`m[inimal]` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="4e15e-227">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="4e15e-228">`diag[nostic]` (Protokollierung der Informationsebene)</span><span class="sxs-lookup"><span data-stu-id="4e15e-228">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="4e15e-229">Standardmäßig sollte das CLI-Tool, wenn es funktioniert, ein Mindestfeedback (`minimal`) anzeigen, z. B. dass es funktioniert und, wenn möglich, wie viel Zeit übrig ist oder wie viel Prozent der Zeit abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="4e15e-229">By default, the CLI tool should show some minimum feedback (`minimal`) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="4e15e-230">Hilfe</span><span class="sxs-lookup"><span data-stu-id="4e15e-230">Help</span></span>

`-h |--help`

<span data-ttu-id="4e15e-231">Druckt die Hilfe für den Befehl und eine Beschreibung der einzelnen Parameter für den Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="4e15e-231">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e15e-232">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e15e-232">See also</span></span>

- [<span data-ttu-id="4e15e-233">Vorgehensweise: Installieren des ML.NET-CLI-Tools</span><span class="sxs-lookup"><span data-stu-id="4e15e-233">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="4e15e-234">Übersicht über die ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="4e15e-234">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="4e15e-235">Tutorial: Stimmungsanalyse über die ML.NET-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e15e-235">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="4e15e-236">Telemetrie in der ML.NET-CLI</span><span class="sxs-lookup"><span data-stu-id="4e15e-236">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)
