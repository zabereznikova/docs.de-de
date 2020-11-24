---
title: Verwenden von Jupyter-Notebooks
titleSuffix: .NET for Apache Spark
description: Verwenden von .NET für Apache Spark in interaktiven Umgebungen wie Jupyter Notebook, Jupyter Lab oder Visual Studio Code (VS Code)
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: efebaf0a66863eae0f71fbf1158b80260d7469cf
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688175"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a><span data-ttu-id="49f10-103">Verwenden von .NET für Apache Spark in Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="49f10-103">Use .NET for Apache Spark in Jupyter notebooks</span></span>

<span data-ttu-id="49f10-104">In diesem Artikel erfahren Sie, wie Sie .NET für Apache Spark-Aufträge interaktiv in Jupyter Notebook und Visual Studio Code (VS Code) mit .NET Interactive ausführen.</span><span class="sxs-lookup"><span data-stu-id="49f10-104">In this article, you learn how to run .NET for Apache Spark jobs interactively in Jupyter Notebook and Visual Studio Code (VS Code) with .NET Interactive.</span></span>

## <a name="about-jupyter"></a><span data-ttu-id="49f10-105">Informationen zu Jupyter</span><span class="sxs-lookup"><span data-stu-id="49f10-105">About Jupyter</span></span>

<span data-ttu-id="49f10-106">[Jupyter](https://jupyter.org/) ist eine plattformübergreifende Open-Source-Computingumgebung, die Benutzern die Möglichkeit bietet, Prototypen und Anwendungen interaktiv zu entwickeln.</span><span class="sxs-lookup"><span data-stu-id="49f10-106">[Jupyter](https://jupyter.org/) is an open-source, cross-platform computing environment that provides a way for users to prototype and develop applications interactively.</span></span> <span data-ttu-id="49f10-107">Sie können über eine Vielzahl von Schnittstellen mit Jupyter interagieren, z. B. Jupyter Notebook, Jupyter Lab und VS Code.</span><span class="sxs-lookup"><span data-stu-id="49f10-107">You can interact with Jupyter through a wide variety of interfaces such as Jupyter Notebook, Jupyter Lab, and VS Code.</span></span>

<span data-ttu-id="49f10-108">Im Kontext von .NET bietet [.NET Interactive](https://github.com/dotnet/interactive) (ein globales .NET Core-Tool) einen Kernel zum Schreiben von .NET-Code (C#/F#) in interaktiven Computingumgebungen wie Jupyter Notebook.</span><span class="sxs-lookup"><span data-stu-id="49f10-108">In the context of .NET, [.NET Interactive](https://github.com/dotnet/interactive), a .NET Core global tool, provides a kernel for writing .NET code (C#/F#) in interactive computing environments such as Jupyter Notebook.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="49f10-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="49f10-109">Prerequisites</span></span>

- [<span data-ttu-id="49f10-110">.NET Core 3.1 SDK</span><span class="sxs-lookup"><span data-stu-id="49f10-110">.NET Core 3.1 SDK</span></span>](../../core/install/index.yml)
- [<span data-ttu-id="49f10-111">Apache Spark</span><span class="sxs-lookup"><span data-stu-id="49f10-111">Apache Spark</span></span>](https://spark.apache.org/downloads.html)
- [<span data-ttu-id="49f10-112">Apache Spark .NET-Worker</span><span class="sxs-lookup"><span data-stu-id="49f10-112">Apache Spark .NET Worker</span></span>](https://github.com/dotnet/spark/releases)

<span data-ttu-id="49f10-113">Weitere Informationen zum Einrichten Ihrer .NET für Apache Spark-Umgebung finden Sie im [Tutorial für die ersten Schritte](../tutorials/get-started.md).</span><span class="sxs-lookup"><span data-stu-id="49f10-113">See the [getting started tutorial](../tutorials/get-started.md) for more information on setting up your .NET for Apache Spark environment.</span></span>

## <a name="prepare-environment"></a><span data-ttu-id="49f10-114">Vorbereiten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="49f10-114">Prepare environment</span></span>

<span data-ttu-id="49f10-115">Für die Arbeit mit Jupyter Notebook benötigen Sie zwei Dinge.</span><span class="sxs-lookup"><span data-stu-id="49f10-115">To work with Jupyter Notebooks, you'll need two things.</span></span>

1. <span data-ttu-id="49f10-116">Installieren Sie das [globale .NET-Tool von .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md).</span><span class="sxs-lookup"><span data-stu-id="49f10-116">Install the [.NET Interactive global .NET tool](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)</span></span>
1. <span data-ttu-id="49f10-117">Laden Sie das NuGet-Paket `Microsoft.Spark` herunter.</span><span class="sxs-lookup"><span data-stu-id="49f10-117">Download the `Microsoft.Spark` NuGet package.</span></span>
    1. <span data-ttu-id="49f10-118">Rufen Sie die NuGet-Paketseite [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) auf.</span><span class="sxs-lookup"><span data-stu-id="49f10-118">Navigate to the [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) NuGet package page.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="49f10-119">Standardmäßig wird die neueste Version des Pakets heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="49f10-119">By default, the latest version of the package is downloaded.</span></span> <span data-ttu-id="49f10-120">**Stellen Sie sicher, dass die heruntergeladene Version Ihrem Apache Spark .NET-Worker entspricht.**</span><span class="sxs-lookup"><span data-stu-id="49f10-120">**Make sure that the version you download is the same as your Apache Spark .NET Worker.**</span></span>

    1. <span data-ttu-id="49f10-121">Klicken Sie im Bereich **Info** auf **Paket herunterladen**, um die neueste Version des Pakets herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="49f10-121">In the **Info** pane, select **Download package** to download the latest version of the package.</span></span> <span data-ttu-id="49f10-122">Der Name des Pakets ähnelt *microsoft.spark.[PAKETVERSION].nupkg*.</span><span class="sxs-lookup"><span data-stu-id="49f10-122">The name of the package is similar to  *microsoft.spark.[PACKAGE-VERSION].nupkg*.</span></span>
    1. <span data-ttu-id="49f10-123">Entpacken Sie das heruntergeladene Paket.</span><span class="sxs-lookup"><span data-stu-id="49f10-123">Unzip the downloaded package.</span></span> <span data-ttu-id="49f10-124">Das entpackte Verzeichnis sollte ein Unterverzeichnis namens *jars* enthalten.</span><span class="sxs-lookup"><span data-stu-id="49f10-124">The unzipped directory should contain a subdirectory called *jars*.</span></span> <span data-ttu-id="49f10-125">Notieren Sie sich den Pfad, da Sie ihn später benötigen.</span><span class="sxs-lookup"><span data-stu-id="49f10-125">Take note of the path since it's used at a later time.</span></span>

## <a name="start-net-for-apache-spark"></a><span data-ttu-id="49f10-126">Starten von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="49f10-126">Start .NET for Apache Spark</span></span>

<span data-ttu-id="49f10-127">Führen Sie den folgenden Befehl aus, um .NET für Apache Spark im Debugmodus zu starten.</span><span class="sxs-lookup"><span data-stu-id="49f10-127">Run the following command to start .NET for Apache Spark in debug mode.</span></span> <span data-ttu-id="49f10-128">Dieser `spark-submit`-Befehl startet einen Prozess und wartet auf eine Verbindung von [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span><span class="sxs-lookup"><span data-stu-id="49f10-128">This `spark-submit` command starts a process and waits for connections from a [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span> <span data-ttu-id="49f10-129">Stellen Sie sicher, dass Sie den entsprechenden Pfad zu `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` für die Version von .NET für Apache Spark angeben, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="49f10-129">Make sure to provide the path to the `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` for the respective version of .NET for Apache Spark you're using.</span></span>

<span data-ttu-id="49f10-130">**Ubuntu**</span><span class="sxs-lookup"><span data-stu-id="49f10-130">**Ubuntu**</span></span>

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

<span data-ttu-id="49f10-131">**Windows**</span><span class="sxs-lookup"><span data-stu-id="49f10-131">**Windows**</span></span>

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a><span data-ttu-id="49f10-132">Erstellen eines Notebooks</span><span class="sxs-lookup"><span data-stu-id="49f10-132">Create a notebook</span></span>

<span data-ttu-id="49f10-133">Sie können verschiedene Schnittstellen verwenden, um mit Jupyter zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="49f10-133">You can use different interfaces to interact with Jupyter.</span></span> <span data-ttu-id="49f10-134">Wenn Sie eine browserbasierte Schnittstelle verwenden möchten, können Sie Jupyter Notebook oder Jupyter Lab verwenden.</span><span class="sxs-lookup"><span data-stu-id="49f10-134">For a browser-based interface, use Jupyter Notebooks or Jupyter Lab.</span></span> <span data-ttu-id="49f10-135">Wenn Sie einen lokalen Editor verwenden möchten, können Sie VS Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="49f10-135">For a local editor experience, use VS Code.</span></span>

### <a name="jupyter-notebooks--jupyter-lab"></a><span data-ttu-id="49f10-136">Jupyter Notebook & Jupyter Lab</span><span class="sxs-lookup"><span data-stu-id="49f10-136">Jupyter Notebooks & Jupyter Lab</span></span>

1. <span data-ttu-id="49f10-137">Starten Sie Jupyter Notebook oder Jupyter Lab mit einem der folgenden Befehle in einer anderen Eingabeaufforderung:</span><span class="sxs-lookup"><span data-stu-id="49f10-137">In another command prompt, start Jupyter Notebook or Jupyter Lab using one of the commands below:</span></span>

    <span data-ttu-id="49f10-138">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="49f10-138">**Jupyter Notebook**</span></span>

    ```bash
    jupyter notebook
    ```

    <span data-ttu-id="49f10-139">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="49f10-139">**Jupyter Lab**</span></span>

    ```bash
    jupyter lab
    ```

    <span data-ttu-id="49f10-140">Mit diesen Befehlen wird ein Browserfenster mit der Jupyter Notebook- oder Jupyter Lab-Schnittstelle gestartet.</span><span class="sxs-lookup"><span data-stu-id="49f10-140">These commands launch a browser window with the Jupyter Notebook or Jupyter Lab interface.</span></span>

1. <span data-ttu-id="49f10-141">Erstellen Sie ein neues Notebook im Browser.</span><span class="sxs-lookup"><span data-stu-id="49f10-141">In the browser, create a new notebook.</span></span>

    <span data-ttu-id="49f10-142">**Jupyter Notebook**</span><span class="sxs-lookup"><span data-stu-id="49f10-142">**Jupyter Notebook**</span></span>

    <span data-ttu-id="49f10-143">Klicken Sie auf **Neu > .NET (C#)** oder **Neu > .NET (F#)**</span><span class="sxs-lookup"><span data-stu-id="49f10-143">Select **New > .NET (C#)** or **New > .NET (F#)**</span></span>

    <span data-ttu-id="49f10-144">**Jupyter Lab**</span><span class="sxs-lookup"><span data-stu-id="49f10-144">**Jupyter Lab**</span></span>

    <span data-ttu-id="49f10-145">Klicken Sie im Fenster des Launchers auf **.NET (C#)** oder **.NET (F#)** .</span><span class="sxs-lookup"><span data-stu-id="49f10-145">In the Launcher window, select **.NET (C#)** or **.NET (F#)**</span></span>

### <a name="visual-studio-code-preview"></a><span data-ttu-id="49f10-146">Visual Studio Code (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="49f10-146">Visual Studio Code (preview)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49f10-147">Zum Verwenden von Jupyter Notebook in VS Code müssen Sie Folgendes installieren:</span><span class="sxs-lookup"><span data-stu-id="49f10-147">To use Jupyter Notebooks in VS Code, you have to install:</span></span>
>
>- [<span data-ttu-id="49f10-148">VS Code Insiders</span><span class="sxs-lookup"><span data-stu-id="49f10-148">VS Code Insiders</span></span>](https://code.visualstudio.com/insiders/)
>- [<span data-ttu-id="49f10-149">.NET Interactive-Notebookerweiterung</span><span class="sxs-lookup"><span data-stu-id="49f10-149">.NET Interactive Notebooks extension</span></span>](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. <span data-ttu-id="49f10-150">Öffnen Sie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="49f10-150">Open VS Code.</span></span>
1. <span data-ttu-id="49f10-151">Öffnen Sie die Befehlspalette **Ansicht > Befehlspalette**.</span><span class="sxs-lookup"><span data-stu-id="49f10-151">Open the command palette **View > Command Palette**.</span></span>

    <span data-ttu-id="49f10-152">Geben Sie den folgenden Befehl ein, wenn die Befehlspalette angezeigt wird, um ein neues .NET Interactive-Notebook zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49f10-152">When the command palette appears, enter the following command to create a new .NET Interactive notebook:</span></span>

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    <span data-ttu-id="49f10-153">Alternativ können Sie den folgenden Befehl verwenden, wenn Sie ein vorhandenes .NET Interactive Notebook mit der Erweiterung *.ipynb* öffnen möchten.</span><span class="sxs-lookup"><span data-stu-id="49f10-153">Alternatively, if you want to open an existing .NET Interactive notebook with the *.ipynb* extension, use the following command:</span></span>

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a><span data-ttu-id="49f10-154">Initialisieren einer Spark-Sitzung</span><span class="sxs-lookup"><span data-stu-id="49f10-154">Initialize a Spark Session</span></span>

1. <span data-ttu-id="49f10-155">Wenn das Notebook geöffnet wird, installieren Sie das NuGet-Paket `Microsoft.Spark`.</span><span class="sxs-lookup"><span data-stu-id="49f10-155">When the notebook opens, install the `Microsoft.Spark` NuGet package.</span></span> <span data-ttu-id="49f10-156">Stellen Sie sicher, dass die Version, die Sie installieren, mit der Version des .NET-Workers übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="49f10-156">Make sure the version you install is the same as the .NET Worker.</span></span>

    ```text
    #r "nuget:Microsoft.Spark, 0.12.1"
    ```

1. <span data-ttu-id="49f10-157">Fügen Sie die folgende using-Anweisung zum Notebook hinzu.</span><span class="sxs-lookup"><span data-stu-id="49f10-157">Add the following using statement to the notebook.</span></span>

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. <span data-ttu-id="49f10-158">Initialisieren Sie das Objekt [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span><span class="sxs-lookup"><span data-stu-id="49f10-158">Initialize your [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).</span></span>

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

<span data-ttu-id="49f10-159">Das Notebook sollte dann dem Notebook auf der folgenden Abbildung ähneln.</span><span class="sxs-lookup"><span data-stu-id="49f10-159">The notebook should look similar to the one in the following image.</span></span> <span data-ttu-id="49f10-160">In diesem Beispiel wird VS Code verwendet, jedoch sollten Jupyter Notebook und Jupyter Lab nahezu identisch aussehen.</span><span class="sxs-lookup"><span data-stu-id="49f10-160">This example uses VS Code, but Jupyter Notebook and Jupyter Lab should look about the same.</span></span>

> [!div class="mx-imgBorder"]
<span data-ttu-id="49f10-161">![.NET für Apache Spark mit Jupyter Notebook in VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span><span class="sxs-lookup"><span data-stu-id="49f10-161">![.NET for Apache Spark Jupyter Notebook VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="49f10-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="49f10-162">Next Steps</span></span>

- [<span data-ttu-id="49f10-163">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="49f10-163">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
- [<span data-ttu-id="49f10-164">Vorhersagen der Stimmung mit .NET für Apache Spark und ML.NET</span><span class="sxs-lookup"><span data-stu-id="49f10-164">Predict sentiment using .NET for Apache Spark and ML.NET</span></span>](../tutorials/ml-sentiment-analysis.md)
- <span data-ttu-id="49f10-165">Weitere Informationen über .NET Interactive finden Sie in der [Dokumentation zu .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md).</span><span class="sxs-lookup"><span data-stu-id="49f10-165">For more information on .NET Interactive, see the [.NET Interactive documentation](https://github.com/dotnet/interactive/blob/main/docs/README.md).</span></span>
