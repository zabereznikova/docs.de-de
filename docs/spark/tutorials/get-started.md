---
title: Erste Schritte mit .NET für Apache Spark
description: Erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.
ms.date: 11/04/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1b736e078eea40e399882c0df020062b6aa758ad
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740527"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="b3a3c-103">Tutorial: Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="b3a3c-104">In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="b3a3c-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="b3a3c-106">Vorbereiten der Windows-Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="b3a3c-107">Schreiben einer ersten .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="b3a3c-108">Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-108">Build and run your simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="b3a3c-109">Vorbereiten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-109">Prepare your environment</span></span>

<span data-ttu-id="b3a3c-110">Bevor Sie mit dem Schreiben Ihrer App beginnen, müssen Sie einige grundlegende Abhängigkeiten einrichten.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-110">Before you begin writing your app, you need to setup some prerequisite dependencies.</span></span> <span data-ttu-id="b3a3c-111">Wenn Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeilenumgebung ausführen können, ist Ihre Umgebung bereits vorbereitet, und Sie können mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-111">If you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="b3a3c-112">Führen Sie die folgenden Schritte aus, wenn Sie keine oder nicht alle Befehle ausführen können.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="b3a3c-113">1. Installieren von .NET</span><span class="sxs-lookup"><span data-stu-id="b3a3c-113">1. Install .NET</span></span>

<span data-ttu-id="b3a3c-114">Sie müssen das .NET SDK (Software Development Kit) herunterladen und installieren, um mit der Entwicklung von .NET-Apps zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="b3a3c-115">Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span> <span data-ttu-id="b3a3c-116">Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> 

<span data-ttu-id="b3a3c-117">Nachdem Sie das .NET Core SDK installiert haben, öffnen Sie eine neue Eingabeaufforderung, und führen Sie `dotnet` aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-117">Once you've installed the .NET Core SDK, open a new command prompt and run `dotnet`.</span></span>

<span data-ttu-id="b3a3c-118">Wenn der Befehl ausgeführt wird und Informationen zur Verwendung von dotnet ausgibt, können Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="b3a3c-119">Wenn Sie einen `'dotnet' is not recognized as an internal or external command`-Fehler erhalten, stellen Sie sicher, dass Sie vor dem Ausführen des Befehls eine **neue** Eingabeaufforderung geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt before running the command.</span></span> 

### <a name="2-install-java"></a><span data-ttu-id="b3a3c-120">2. Installieren von Java</span><span class="sxs-lookup"><span data-stu-id="b3a3c-120">2. Install Java</span></span>

<span data-ttu-id="b3a3c-121">Installieren Sie [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

<span data-ttu-id="b3a3c-122">Wählen Sie die für Ihr Betriebssystem geeignete Version aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="b3a3c-123">Für einen Windows-Computer mit x64-Architektur wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span> <span data-ttu-id="b3a3c-124">Verwenden Sie dann den Befehl `java`, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-124">Then, use the command `java` to verify the installation.</span></span>
   
![Java-Download](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-7-zip"></a><span data-ttu-id="b3a3c-126">3. Installieren von 7-Zip</span><span class="sxs-lookup"><span data-stu-id="b3a3c-126">3. Install 7-zip</span></span>

<span data-ttu-id="b3a3c-127">Apache Spark wird als komprimierte TGZ-Datei heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="b3a3c-128">Verwenden Sie ein Extraktionsprogramm wie 7-Zip, um die Datei zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-128">Use an extraction program, like 7-zip, to extract the file.</span></span>

* <span data-ttu-id="b3a3c-129">Besuchen Sie [7-Zip-Downloads](https://www.7-zip.org/).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-129">Visit [7-Zip downloads](https://www.7-zip.org/).</span></span>
* <span data-ttu-id="b3a3c-130">Wählen Sie in der ersten Tabelle auf der Seite je nach Betriebssystem den 32-Bit-x86- oder 64-Bit-x64-Download aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-130">In the first table on the page, select the 32-bit x86 or 64-bit x64 download, depending on your operating system.</span></span>
* <span data-ttu-id="b3a3c-131">Führen Sie nach Abschluss des Downloads das Installationsprogramm aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-131">When the download completes, run the installer.</span></span>
   
![7-Zip-Download](https://dotnet.microsoft.com/static/images/7-zip-downloads.png?v=W6qWtFC1tTMKv3YGXz7lBa9F3M22uWyTvkMmunyroNk)

### <a name="4-install-apache-spark"></a><span data-ttu-id="b3a3c-133">4. Installieren von Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-133">4. Install Apache Spark</span></span>

<span data-ttu-id="b3a3c-134">[Laden Sie Apache Spark herunter, und installieren Sie es](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-134">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="b3a3c-135">Sie müssen aus den Versionen 2.3.\* oder 2.4.0, 2.4.1, 2.4.3 oder 2.4.4 auswählen (.NET für Apache Spark ist mit anderen Versionen von Apache Spark nicht kompatibel).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-135">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, or 2.4.4 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>  

<span data-ttu-id="b3a3c-136">Anhand der in den folgenden Schritten verwendeten Befehle wird davon ausgegangen, dass Sie [Apache Spark 2.4.1 heruntergeladen und installiert](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz) haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-136">The commands used in the following steps assume you have [downloaded and installed Apache Spark 2.4.1](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz).</span></span> <span data-ttu-id="b3a3c-137">Wenn Sie eine andere Version verwenden möchten, ersetzen Sie **2.4.1** durch die entsprechende Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-137">If you wish to use a different version, replace **2.4.1** with the appropriate version number.</span></span> <span data-ttu-id="b3a3c-138">Extrahieren Sie anschließend die **TAR**-Datei und die Apache Spark-Dateien.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-138">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="b3a3c-139">So extrahieren Sie die **TAR**-Datei:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-139">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="b3a3c-140">Suchen Sie die Datei **spark-2.4.1-bin-hadoop2.7.tgz**, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-140">Locate the **spark-2.4.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="b3a3c-141">Klicken Sie mit der rechten Maustaste auf die Datei, und wählen Sie **7-Zip -> Extract here** (7-Zip -> Hier extrahieren) aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-141">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="b3a3c-142">**spark-2.4.1-bin-hadoop2.7.tar** wird zusammen mit der **TGZ**-Datei erstellt, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-142">**spark-2.4.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="b3a3c-143">So extrahieren Sie die Apache Spark-Dateien:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-143">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="b3a3c-144">Klicken Sie mit der rechten Maustaste auf **spark-2.4.1-bin-hadoop2.7.tar**, und wählen Sie **7-Zip -> Extract files...** (7-Zip-> Dateien extrahieren...) aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-144">Right click on **spark-2.4.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="b3a3c-145">Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-145">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="b3a3c-146">Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-146">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="b3a3c-147">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-147">Select **OK**.</span></span>
* <span data-ttu-id="b3a3c-148">Die Apache Spark-Dateien werden nach C:\bin\spark-2.4.1-bin-hadoop2.7\ extrahiert.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-148">The Apache Spark files are extracted to C:\bin\spark-2.4.1-bin-hadoop2.7\</span></span>
      
![Spark-Installation](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)
    
<span data-ttu-id="b3a3c-150">Führen Sie die folgenden Befehle aus, um die Umgebungsvariablen für die Suche nach Apache Spark festzulegen:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-150">Run the following commands to set the environment variables used to locate Apache Spark:</span></span>

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

<span data-ttu-id="b3a3c-151">Nachdem Sie alles installiert und die Umgebungsvariablen festgelegt haben, öffnen Sie eine **neue** Eingabeaufforderung, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-151">Once you've installed everything and set your environment variables, open a **new** command prompt and run the following command:</span></span>

`%SPARK_HOME%\bin\spark-submit --version`

<span data-ttu-id="b3a3c-152">Wenn der Befehl ausgeführt wird und Versionsinformationen ausgibt, können Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-152">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="b3a3c-153">Wenn Sie einen `'spark-submit' is not recognized as an internal or external command`-Fehler erhalten, stellen Sie sicher, dass Sie eine **neue** Eingabeaufforderung geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-153">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="b3a3c-154">5. Installieren von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-154">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="b3a3c-155">Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von GitHub für .NET für Apache Spark herunter.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-155">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="b3a3c-156">Wenn Sie sich beispielsweise auf einem Windows-Computer befinden und die Verwendung von .NET Core planen, [laden Sie das Windows x64 netcoreapp2.1-Release herunter](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-156">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp2.1 release](https://github.com/dotnet/spark/releases/download/v0.5.0/Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip).</span></span>

<span data-ttu-id="b3a3c-157">So extrahieren Sie Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-157">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="b3a3c-158">Suchen Sie die Datei **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip**, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-158">Locate the **Microsoft.Spark.Worker.netcoreapp2.1.win-x64-0.6.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="b3a3c-159">Klicken Sie mit der rechten Maustaste, und wählen Sie **7-Zip -> Extract files...** (7-Zip-> Dateien extrahieren...) aus.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-159">Right click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="b3a3c-160">Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-160">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="b3a3c-161">Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-161">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="b3a3c-162">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-162">Select **OK**.</span></span>
  
![.NET Spark-Installation](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils"></a><span data-ttu-id="b3a3c-164">6. Installieren von WinUtils</span><span class="sxs-lookup"><span data-stu-id="b3a3c-164">6. Install WinUtils</span></span>

<span data-ttu-id="b3a3c-165">.NET für Apache Spark erfordert die Installation von WinUtils neben Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-165">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="b3a3c-166">[Laden Sie die winutils.exe-Datei herunter](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-166">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="b3a3c-167">Kopieren Sie dann WinUtils in **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-167">Then, copy WinUtils into **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="b3a3c-168">Wenn Sie eine andere Version von Hadoop verwenden (dies ist am Ende des Namens Ihres Spark-Installationsordner angemerkt), [wählen Sie die Version von WinUtils aus](https://github.com/steveloughran/winutils), die mit Ihrer Version von Hadoop kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-168">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span> 

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="b3a3c-169">7. Festlegen von DOTNET_WORKER_DIR und Überprüfen von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="b3a3c-169">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="b3a3c-170">Führen Sie den folgenden Befehl aus, um die Umgebungsvariable `DOTNET_WORKER_DIR` festzulegen, die von .NET-Apps für die Suche nach Apache Spark verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-170">Run the following command to set the `DOTNET_WORKER_DIR` Environment Variable, which is used by .NET apps to locate .NET for Apache Spark:</span></span>

`setx DOTNET_WORKER_DIR "C:\bin\Microsoft.Spark.Worker-0.6.0"`

<span data-ttu-id="b3a3c-171">Überprüfen Sie abschließend, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-171">Finally, double-check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="b3a3c-172">Programmieren einer .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="b3a3c-172">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="b3a3c-173">1. Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-173">1. Create a console app</span></span>

<span data-ttu-id="b3a3c-174">Führen Sie in der Eingabeaufforderung die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-174">In your command prompt, run the following commands to create a new console application:</span></span>

```console
dotnet new console -o mySparkApp
cd mySparkApp
```

<span data-ttu-id="b3a3c-175">Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-175">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="b3a3c-176">Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-176">The `-o` parameter creates a directory named *mySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="b3a3c-177">Mit dem Befehl `cd mySparkApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-177">The `cd mySparkApp` command changes the directory to the app directory you just created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="b3a3c-178">2. Installieren des NuGet-Pakets</span><span class="sxs-lookup"><span data-stu-id="b3a3c-178">2. Install NuGet package</span></span>

<span data-ttu-id="b3a3c-179">Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-179">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="b3a3c-180">Führen Sie an der Eingabeaufforderung folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-180">In your command prompt, run the following command:</span></span>

`dotnet add package Microsoft.Spark --version 0.6.0`

### <a name="3-code-your-app"></a><span data-ttu-id="b3a3c-181">3. Programmieren Ihrer App</span><span class="sxs-lookup"><span data-stu-id="b3a3c-181">3. Code your app</span></span>

<span data-ttu-id="b3a3c-182">Öffnen Sie *Program.cs* in Visual Studio Code oder in einem beliebigen Text-Editor, und ersetzen Sie den gesamten Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-182">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            var spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            var words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-add-data-file"></a><span data-ttu-id="b3a3c-183">4. Hinzufügen der Datendatei</span><span class="sxs-lookup"><span data-stu-id="b3a3c-183">4. Add data file</span></span>

<span data-ttu-id="b3a3c-184">Ihre App verarbeitet eine Datei mit Textzeilen.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-184">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="b3a3c-185">Erstellen Sie eine *input.txt*-Datei in Ihrem *mySparkApp*-Verzeichnis, die den folgenden Text enthält:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-185">Create an *input.txt* file in your *mySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="b3a3c-186">Ausführen der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="b3a3c-186">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="b3a3c-187">Führen Sie den folgenden Befehl aus, um die Anwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-187">Run the following command to build your application:</span></span>

   ```dotnetcli
   dotnet build
   ```

2. <span data-ttu-id="b3a3c-188">Führen Sie den folgenden Befehl aus, um Ihre Anwendung für die Ausführung auf Apache Spark zu übermitteln:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-188">Run the following command to submit your application to run on Apache Spark:</span></span>

   ```powershell
   %SPARK_HOME%\bin\spark-submit --class org.apache.spark.deploy.dotnet.DotnetRunner --master local bin\Debug\netcoreapp3.0\microsoft-spark-2.4.x-0.6.0.jar dotnet bin\Debug\netcoreapp3.0\mySparkApp.dll
   ```

3. <span data-ttu-id="b3a3c-189">Wenn Ihre App ausgeführt wird, werden die Wortzähldaten der Datei *Input.txt* in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-189">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

<span data-ttu-id="b3a3c-190">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="b3a3c-190">Congratulations!</span></span> <span data-ttu-id="b3a3c-191">Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-191">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b3a3c-192">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b3a3c-192">Next steps</span></span>

<span data-ttu-id="b3a3c-193">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b3a3c-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="b3a3c-194">Vorbereiten der Windows-Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-194">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="b3a3c-195">Schreiben einer ersten .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-195">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="b3a3c-196">Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a3c-196">Build and run your simple .NET for Apache Spark application</span></span>

<span data-ttu-id="b3a3c-197">Ein Video, in dem die obigen Schritte erläutert werden, finden Sie in der [Videoserie zu .NET für Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="b3a3c-197">To see a video explaining the steps above, checkout the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="b3a3c-198">Weitere Informationen finden Sie auf der Ressourcenseite.</span><span class="sxs-lookup"><span data-stu-id="b3a3c-198">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="b3a3c-199">Ressourcen für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b3a3c-199">.NET for Apache Spark Resources</span></span>](../resources/index.md)
