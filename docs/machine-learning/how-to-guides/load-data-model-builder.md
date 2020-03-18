---
title: Laden von Trainingsdaten für den Modell-Generator
description: Informieren Sie sich, wie Sie Trainingsdaten aus einer SQL Server-Datenbank oder einer Datei zur Verwendung in eines der Modell-Generator-Szenarios für ML.NET laden.
ms.date: 10/29/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: 23de2d06090f4c1eaa2c79178ba4c346698d45e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849158"
---
# <a name="load-training-data-into-model-builder"></a><span data-ttu-id="2d847-103">Laden von Trainingsdaten in den Modell-Generator</span><span class="sxs-lookup"><span data-stu-id="2d847-103">Load training data into Model Builder</span></span>

<span data-ttu-id="2d847-104">Informieren Sie sich, wie Sie Ihre Trainingsdatasets aus einer Datei oder einer SQL Server-Datenbank zur Verwendung in eines der Modell-Generator-Szenarios für ML.NET laden.</span><span class="sxs-lookup"><span data-stu-id="2d847-104">Learn how to load your training datasets from a file or a SQL Server database for use in one of the Model Builder scenarios for ML.NET.</span></span> <span data-ttu-id="2d847-105">Modell-Generator-Szenarios können SQL Server-Datenbanken, Imagedateien und CSV- oder TSV-Dateiformate als Trainingsdaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d847-105">Model Builder scenarios can use SQL Server databases, image files, and CSV or TSV file formats as training data.</span></span>

## <a name="training-dataset-limitations-in-model-builder"></a><span data-ttu-id="2d847-106">Trainingsdataseteinschränkungen im Modell-Generator</span><span class="sxs-lookup"><span data-stu-id="2d847-106">Training dataset limitations in Model Builder</span></span>

<span data-ttu-id="2d847-107">Der Modell-Generator schränkt die Menge und den Typ der Daten ein, die Sie für Trainingsmodelle verwenden können:</span><span class="sxs-lookup"><span data-stu-id="2d847-107">Model Builder limits the amount and type of data you can use for training models:</span></span>

- <span data-ttu-id="2d847-108">SQL Server-Daten: 100.000 Zeilen</span><span class="sxs-lookup"><span data-stu-id="2d847-108">SQL Server data: 100,000 rows</span></span>
- <span data-ttu-id="2d847-109">CSV- und TSV-Dateien: kein Größenlimit</span><span class="sxs-lookup"><span data-stu-id="2d847-109">CSV and TSV files: No size limit</span></span>
- <span data-ttu-id="2d847-110">Images: nur PNG und JPG</span><span class="sxs-lookup"><span data-stu-id="2d847-110">Images: PNG and JPG only.</span></span>

## <a name="model-builder-scenarios"></a><span data-ttu-id="2d847-111">Modell-Generator-Szenarios</span><span class="sxs-lookup"><span data-stu-id="2d847-111">Model Builder scenarios</span></span>

<span data-ttu-id="2d847-112">Der Modell-Generator unterstützt Sie beim Erstellen von Modellen für die folgenden Machine Learning-Szenarios:</span><span class="sxs-lookup"><span data-stu-id="2d847-112">Model Builder helps you create models for the following machine learning scenarios:</span></span>

- <span data-ttu-id="2d847-113">Standpunktanalyse (binäre Klassifizierung): Klassifizieren von Textdaten in zwei Kategorien</span><span class="sxs-lookup"><span data-stu-id="2d847-113">Sentiment analysis (binary classification): Classify textual data into two categories.</span></span>
- <span data-ttu-id="2d847-114">Klassifizierung von Issues (Multiklassenklassifizierung): Klassifizieren von Textdaten in drei oder mehr Kategorien</span><span class="sxs-lookup"><span data-stu-id="2d847-114">Issue classification (multiclass classification): Classify textual data into 3 or more categories.</span></span>
- <span data-ttu-id="2d847-115">Preisvorhersage (Regression): Vorhersagen eines numerischen Werts</span><span class="sxs-lookup"><span data-stu-id="2d847-115">Price prediction (regression): Predict a numeric value.</span></span>
- <span data-ttu-id="2d847-116">Bildklassifizierung (Deep Learning): Kategorisieren von Bildern basierend auf Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2d847-116">Image classification (deep learning): Categorize images based on characteristics.</span></span>
- <span data-ttu-id="2d847-117">Benutzerdefiniertes Szenario: Erstellen benutzerdefinierter Szenarios aus Ihren Daten mithilfe von Regression, Klassifizierung und anderen Aufgaben</span><span class="sxs-lookup"><span data-stu-id="2d847-117">Custom scenario: Build custom scenarios from your data using regression, classification, and other tasks.</span></span>

<span data-ttu-id="2d847-118">In diesem Artikel werden Klassifizierungs- und Regressionsszenarios mit Text- oder numerischen Daten sowie Bildklassifizierungsszenarios behandelt.</span><span class="sxs-lookup"><span data-stu-id="2d847-118">This article covers classification and regression scenarios with textual or numerical data, and image classification scenarios.</span></span>

## <a name="load-text-or-numeric-data-from-a-file"></a><span data-ttu-id="2d847-119">Laden von Text- oder numerischen Daten aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="2d847-119">Load text or numeric data from a file</span></span>

<span data-ttu-id="2d847-120">Sie können Text- oder numerische Daten aus einer Datei in den Modell-Generator laden.</span><span class="sxs-lookup"><span data-stu-id="2d847-120">You can load text or numeric data from a file into Model Builder.</span></span> <span data-ttu-id="2d847-121">Dieser akzeptiert durch Trennzeichen getrennte (CSV) und durch Tabstopps getrennte (TSV) Dateiformate.</span><span class="sxs-lookup"><span data-stu-id="2d847-121">It accepts comma-delimited (CSV) or tab-delimited (TSV) file formats.</span></span>

1. <span data-ttu-id="2d847-122">Wählen Sie im Schritt „Daten“ des Modell-Generators die Option **Datei** aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="2d847-122">In the data step of Model Builder, select **File** from the data source dropdown.</span></span>
2. <span data-ttu-id="2d847-123">Klicken Sie auf die Schaltfläche neben dem Textfeld **Datei auswählen**, und verwenden Sie den Datei-Explorer, um die Datendatei zu suchen und auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2d847-123">Select the button next to the **Select a file** text box, and use File Explorer to browse and select the data file.</span></span>
3. <span data-ttu-id="2d847-124">Wählen Sie in der Dropdownliste **Column to Predict (Label)** (Vorherzusagende Spalte (Bezeichnung)) eine Kategorie aus.</span><span class="sxs-lookup"><span data-stu-id="2d847-124">Choose a category in the **Column to Predict (Label)** dropdown.</span></span>
4. <span data-ttu-id="2d847-125">Vergewissern Sie sich, dass in der Dropdownliste **Input Columns (Features)** (Eingabespalten (Features)) die Datenspalten, die Sie einschließen möchten, überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2d847-125">From the **Input Columns (Features)** dropdown, confirm the data columns you want to include are checked.</span></span>

<span data-ttu-id="2d847-126">Sie haben die Einrichtung der Datenquellendatei für den Modell-Generator abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2d847-126">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="2d847-127">Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="2d847-127">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="load-data-from-a-sql-server-database"></a><span data-ttu-id="2d847-128">Laden von Daten aus einer SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="2d847-128">Load data from a SQL Server database</span></span>

<span data-ttu-id="2d847-129">Der Modell-Generator unterstützt das Laden von Daten aus lokalen und SQL Server-Remotedatenbanken.</span><span class="sxs-lookup"><span data-stu-id="2d847-129">Model Builder supports loading data from local and remote SQL Server databases.</span></span>

<span data-ttu-id="2d847-130">So laden Sie Daten aus einer SQL Server-Datenbank in den Modell-Generator:</span><span class="sxs-lookup"><span data-stu-id="2d847-130">To load data from a SQL Server database into Module Builder:</span></span>

1. <span data-ttu-id="2d847-131">Wählen Sie im Schritt „Daten“ des Modell-Generators die Option **SQL Server** aus der Dropdownliste „Datenquelle“ aus.</span><span class="sxs-lookup"><span data-stu-id="2d847-131">In the data step of Model Builder, select **SQL Server** from the data source dropdown.</span></span>
1. <span data-ttu-id="2d847-132">Klicken Sie auf die Schaltfläche neben dem Textfeld **Connect to SQL Server database** (Verbindung mit SQL Server-Datenbank herstellen).</span><span class="sxs-lookup"><span data-stu-id="2d847-132">Select the button next to the **Connect to SQL Server database** text box.</span></span>
    1. <span data-ttu-id="2d847-133">Klicken Sie im Dialogfeld **Choose Data** (Daten auswählen) auf **Microsoft SQL Server-Datenbankdatei**.</span><span class="sxs-lookup"><span data-stu-id="2d847-133">In the **Choose Data** dialog, select **Microsoft SQL Server Database File**.</span></span>
    1. <span data-ttu-id="2d847-134">Deaktivieren Sie das Kontrollkästchen **Immer diese Auswahl verwenden**, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2d847-134">Uncheck the **Always use this selection** checkbox and select **Continue**</span></span>
    1. <span data-ttu-id="2d847-135">Klicken Sie im Dialogfeld **Verbindungseigenschaften** auf **Durchsuchen**, und klicken Sie auf die heruntergeladene MDF-Datei.</span><span class="sxs-lookup"><span data-stu-id="2d847-135">In the **Connection Properties** dialog, select **Browse** and select the downloaded .MDF file.</span></span>
    1. <span data-ttu-id="2d847-136">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2d847-136">Select **OK**</span></span>
1. <span data-ttu-id="2d847-137">Wählen Sie in der Dropdownliste **Tabellenname** den Datasetnamen aus.</span><span class="sxs-lookup"><span data-stu-id="2d847-137">Choose the dataset name from the **Table Name** dropdown.</span></span>
1. <span data-ttu-id="2d847-138">Wählen Sie in der Dropdownliste **Column to Predict (Label)** (Vorherzusagende Spalte (Bezeichnung)) die Datenkategorie aus, für die Sie eine Vorhersage erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d847-138">From the **Column to Predict (Label)** dropdown, choose the data category on which you want to make a prediction.</span></span>
1. <span data-ttu-id="2d847-139">Vergewissern Sie sich, dass in der Dropdownliste **Input Columns (Features)** (Eingabespalten (Features)) die Spalten, die Sie einschließen möchten, überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2d847-139">From the **Input Columns (Features)** dropdown, confirm the columns you want to include are checked.</span></span>

<span data-ttu-id="2d847-140">Sie haben die Einrichtung der Datenquellendatei für den Modell-Generator abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2d847-140">You're done setting up your data source file for Model Builder.</span></span> <span data-ttu-id="2d847-141">Wählen Sie den Link **Trainieren** aus, um zum nächsten Schritt im Modell-Generator zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="2d847-141">Select the **Train** link to move to the next step in Model Builder.</span></span>

## <a name="set-up-image-data-files"></a><span data-ttu-id="2d847-142">Einrichten von Bilddatendateien</span><span class="sxs-lookup"><span data-stu-id="2d847-142">Set up image data files</span></span>

<span data-ttu-id="2d847-143">Der Modell-Generator erwartet, dass Bilddaten JPG- oder PNG-Dateien sind, die in Ordnern organisiert sind, die den Kategorien der Klassifizierung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2d847-143">Model Builder expects image data to be JPG or PNG files organized in folders that correspond to the categories of the classification.</span></span>

<span data-ttu-id="2d847-144">Geben Sie den Pfad zu einem einzelnen Verzeichnis der obersten Ebene an, um Bilder in den Modell-Generator zu laden:</span><span class="sxs-lookup"><span data-stu-id="2d847-144">To load images into Model Builder, provide the path to a single top-level directory:</span></span>

- <span data-ttu-id="2d847-145">Dieses Verzeichnis der obersten Ebene enthält einen Unterordner für jede der vorherzusagenden Kategorien.</span><span class="sxs-lookup"><span data-stu-id="2d847-145">This top-level directory contains one subfolder for each of the categories to predict.</span></span>
- <span data-ttu-id="2d847-146">Jeder Unterordner enthält die Bilddateien, die zur Kategorie gehören.</span><span class="sxs-lookup"><span data-stu-id="2d847-146">Each subfolder contains the image files belonging to its category.</span></span>

<span data-ttu-id="2d847-147">In der unten dargestellten Ordnerstruktur ist *flower_photos* das Verzeichnis der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="2d847-147">In the folder structure illustrated below, the top-level directory is *flower_photos*.</span></span> <span data-ttu-id="2d847-148">Es gibt fünf Unterverzeichnisse, die den Kategorien entsprechen, die Sie vorhersagen möchten: daisy, dandelion, roses, sunflowers und tulips.</span><span class="sxs-lookup"><span data-stu-id="2d847-148">There are five subdirectories corresponding to the categories you want to predict: daisy, dandelion, roses, sunflowers, and tulips.</span></span> <span data-ttu-id="2d847-149">Jedes dieser Unterverzeichnisse enthält Bilder, die der jeweiligen Kategorie angehören.</span><span class="sxs-lookup"><span data-stu-id="2d847-149">Each of these subdirectories contains images belonging to its respective category.</span></span>

```text
\---flower_photos
    +---daisy
    |       100080576_f52e8ee070_n.jpg
    |       102841525_bd6628ae3c.jpg
    |       105806915_a9c13e2106_n.jpg
    |
    +---dandelion
    |       10443973_aeb97513fc_m.jpg
    |       10683189_bd6e371b97.jpg
    |       10919961_0af657c4e8.jpg
    |
    +---roses
    |       102501987_3cdb8e5394_n.jpg
    |       110472418_87b6a3aa98_m.jpg
    |       118974357_0faa23cce9_n.jpg
    |
    +---sunflowers
    |       127192624_afa3d9cb84.jpg
    |       145303599_2627e23815_n.jpg
    |       147804446_ef9244c8ce_m.jpg
    |
    \---tulips
            100930342_92e8746431_n.jpg
            107693873_86021ac4ea_n.jpg
            10791227_7168491604.jpg
```

## <a name="next-steps"></a><span data-ttu-id="2d847-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2d847-150">Next steps</span></span>

<span data-ttu-id="2d847-151">Führen Sie die Schritte dieses Tutorials aus, um mit dem Modell-Generator Machine Learning-Apps zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="2d847-151">Follow these tutorials to build machine learning apps with Model Builder:</span></span>

- [<span data-ttu-id="2d847-152">Vorhersagen von Preisen per Regression</span><span class="sxs-lookup"><span data-stu-id="2d847-152">Predict prices using regression</span></span>](../tutorials/predict-prices-with-model-builder.md)
- [<span data-ttu-id="2d847-153">Analysieren des Standpunkts in einer Webanwendung mithilfe der binären Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="2d847-153">Analyze sentiment in a web application using binary classification</span></span>](../tutorials/sentiment-analysis-model-builder.md )

<span data-ttu-id="2d847-154">Wenn Sie ein Modell mithilfe von Code trainieren, können Sie sich [hier informieren, wie Sie Daten mithilfe der ML.NET-API laden](load-data-ml-net.md).</span><span class="sxs-lookup"><span data-stu-id="2d847-154">If you're training a model using code, [learn how to load data using the ML.NET API](load-data-ml-net.md).</span></span>
