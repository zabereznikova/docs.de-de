---
title: Erste Schritte mit .NET für Apache Spark
description: Informieren Sie sich, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET for Apache Spark-App ausführen.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687822"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="6a257-103">Tutorial: Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="6a257-104">In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET for Apache Spark-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a257-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows, macOS, and Ubuntu.</span></span>

<span data-ttu-id="6a257-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="6a257-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="6a257-106">Vorbereiten der Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-106">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="6a257-107">Schreiben einer ersten .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a257-107">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="6a257-108">Erstellen und Ausführen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a257-108">Build and run your .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="6a257-109">Vorbereiten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="6a257-109">Prepare your environment</span></span>

<span data-ttu-id="6a257-110">Bevor Sie mit dem Schreiben Ihrer App beginnen, müssen Sie einige grundlegende Abhängigkeiten einrichten.</span><span class="sxs-lookup"><span data-stu-id="6a257-110">Before you begin writing your app, you need to set up some prerequisite dependencies.</span></span> <span data-ttu-id="6a257-111">Wenn Sie `dotnet`, `java` und `spark-shell` über die Befehlszeilenumgebung ausführen können, ist Ihre Umgebung bereits vorbereitet, und Sie können mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6a257-111">If you can run `dotnet`, `java`, `spark-shell` from your command line environment, then your environment is already prepared and you can skip to the next section.</span></span> <span data-ttu-id="6a257-112">Führen Sie die folgenden Schritte aus, wenn Sie keine oder nicht alle Befehle ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6a257-112">If you cannot run any or all of the commands, do the following steps.</span></span>

### <a name="1-install-net"></a><span data-ttu-id="6a257-113">1. Installieren von .NET</span><span class="sxs-lookup"><span data-stu-id="6a257-113">1. Install .NET</span></span>

<span data-ttu-id="6a257-114">Sie müssen das .NET SDK (Software Development Kit) herunterladen und installieren, um mit der Entwicklung von .NET-Apps zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="6a257-114">To start building .NET apps, you need to download and install the .NET SDK (Software Development Kit).</span></span>

<span data-ttu-id="6a257-115">Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="6a257-115">Download and install the [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span> <span data-ttu-id="6a257-116">Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a257-116">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span>

<span data-ttu-id="6a257-117">Nachdem Sie das .NET Core SDK installiert haben, öffnen Sie eine neue Eingabeaufforderung oder ein Terminal, und führen Sie `dotnet` aus.</span><span class="sxs-lookup"><span data-stu-id="6a257-117">Once you've installed the .NET Core SDK, open a new command prompt or terminal and run `dotnet`.</span></span>

<span data-ttu-id="6a257-118">Wenn der Befehl ausgeführt wird und Informationen zur Verwendung von dotnet ausgibt, können Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6a257-118">If the command runs and prints out information about how to use dotnet, can move to the next step.</span></span> <span data-ttu-id="6a257-119">Stellen Sie sicher, dass Sie vor dem Ausführen des Befehls eine **neue** Eingabeaufforderung oder ein Terminal geöffnet haben, wenn Sie einen `'dotnet' is not recognized as an internal or external command`-Fehler erhalten.</span><span class="sxs-lookup"><span data-stu-id="6a257-119">If you receive a `'dotnet' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt or terminal before running the command.</span></span>

### <a name="2-install-java"></a><span data-ttu-id="6a257-120">2. Installieren von Java</span><span class="sxs-lookup"><span data-stu-id="6a257-120">2. Install Java</span></span>

<span data-ttu-id="6a257-121">Installieren Sie [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) für Windows und macOS oder [OpenJDK 8](https://openjdk.java.net/install/) für Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="6a257-121">Install [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) for Windows and macOS, or [OpenJDK 8](https://openjdk.java.net/install/) for Ubuntu.</span></span>

<span data-ttu-id="6a257-122">Wählen Sie die für Ihr Betriebssystem geeignete Version aus.</span><span class="sxs-lookup"><span data-stu-id="6a257-122">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="6a257-123">Wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** für einen Windows-x64-Computer (wie unten gezeigt) oder **jdk-8u231-macosx-x64.dmg** für macOS aus.</span><span class="sxs-lookup"><span data-stu-id="6a257-123">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine (as shown below) or **jdk-8u231-macosx-x64.dmg** for macOS.</span></span> <span data-ttu-id="6a257-124">Verwenden Sie dann den Befehl `java`, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6a257-124">Then, use the command `java` to verify the installation.</span></span>

![Java-Download](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a><span data-ttu-id="6a257-126">3. Installieren von Komprimierungssoftware</span><span class="sxs-lookup"><span data-stu-id="6a257-126">3. Install compression software</span></span>

<span data-ttu-id="6a257-127">Apache Spark wird als komprimierte TGZ-Datei heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="6a257-127">Apache Spark is downloaded as a compressed .tgz file.</span></span> <span data-ttu-id="6a257-128">Verwenden Sie ein Extraktionsprogramm wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/), um die Datei zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="6a257-128">Use an extraction program, like [7-Zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/), to extract the file.</span></span>

### <a name="4-install-apache-spark"></a><span data-ttu-id="6a257-129">4. Installieren von Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-129">4. Install Apache Spark</span></span>

<span data-ttu-id="6a257-130">[Laden Sie Apache Spark herunter, und installieren Sie es](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="6a257-130">[Download and install Apache Spark](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="6a257-131">Sie müssen aus den Versionen 2.3.\* oder 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 oder 3.0.1. auswählen (.NET für Apache Spark ist mit anderen Versionen von Apache Spark nicht kompatibel).</span><span class="sxs-lookup"><span data-stu-id="6a257-131">You'll need to select from version 2.3.\* or 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0, or 3.0.1 (.NET for Apache Spark is not compatible with other versions of Apache Spark).</span></span>

<span data-ttu-id="6a257-132">Anhand der in den folgenden Schritten verwendeten Befehle wird davon ausgegangen, dass Sie [Apache Spark 3.0.1 heruntergeladen und installiert](https://spark.apache.org/downloads.html) haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-132">The commands used in the following steps assume you have [downloaded and installed Apache Spark 3.0.1](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="6a257-133">Wenn Sie eine andere Version verwenden möchten, ersetzen Sie **3.0.1** durch die entsprechende Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="6a257-133">If you wish to use a different version, replace **3.0.1** with the appropriate version number.</span></span> <span data-ttu-id="6a257-134">Extrahieren Sie anschließend die **TAR**-Datei und die Apache Spark-Dateien.</span><span class="sxs-lookup"><span data-stu-id="6a257-134">Then, extract the **.tar** file and the Apache Spark files.</span></span>

<span data-ttu-id="6a257-135">So extrahieren Sie die **TAR**-Datei:</span><span class="sxs-lookup"><span data-stu-id="6a257-135">To extract the nested **.tar** file:</span></span>

* <span data-ttu-id="6a257-136">Suchen Sie die Datei **spark-3.0.1-bin-hadoop2.7.tgz**, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-136">Locate the **spark-3.0.1-bin-hadoop2.7.tgz** file that you downloaded.</span></span>
* <span data-ttu-id="6a257-137">Klicken Sie mit der rechten Maustaste auf die Datei, und wählen Sie **7-Zip -> Extract here** (7-Zip -> Hier extrahieren) aus.</span><span class="sxs-lookup"><span data-stu-id="6a257-137">Right click on the file and select **7-Zip -> Extract here**.</span></span>
* <span data-ttu-id="6a257-138">**spark-3.0.1-bin-hadoop2.7.tar** wird zusammen mit der **TGZ**-Datei erstellt, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-138">**spark-3.0.1-bin-hadoop2.7.tar** is created alongside the **.tgz** file you downloaded.</span></span>

<span data-ttu-id="6a257-139">So extrahieren Sie die Apache Spark-Dateien:</span><span class="sxs-lookup"><span data-stu-id="6a257-139">To extract the Apache Spark files:</span></span>

* <span data-ttu-id="6a257-140">Klicken Sie mit der rechten Maustaste auf **spark-3.0.1-bin-hadoop2.7.tar**, und klicken Sie auf **7-Zip > Extract files** (7-Zip > Dateien extrahieren).</span><span class="sxs-lookup"><span data-stu-id="6a257-140">Right-click on **spark-3.0.1-bin-hadoop2.7.tar** and select **7-Zip -> Extract files...**</span></span>
* <span data-ttu-id="6a257-141">Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.</span><span class="sxs-lookup"><span data-stu-id="6a257-141">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="6a257-142">Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.</span><span class="sxs-lookup"><span data-stu-id="6a257-142">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="6a257-143">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a257-143">Select **OK**.</span></span>
* <span data-ttu-id="6a257-144">Die Apache Spark-Dateien werden nach C:\bin\spark-3.0.1-bin-hadoop2.7\ extrahiert.</span><span class="sxs-lookup"><span data-stu-id="6a257-144">The Apache Spark files are extracted to C:\bin\spark-3.0.1-bin-hadoop2.7\</span></span>

![Spark-Installation](./media/spark-extract-with-7-zip.png)

<span data-ttu-id="6a257-146">Führen Sie die folgenden Befehle aus, um die Umgebungsvariablen für die Suche nach Apache Spark festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6a257-146">Run the following commands to set the environment variables used to locate Apache Spark.</span></span> <span data-ttu-id="6a257-147">Stellen Sie unter Windows sicher, dass Sie die Eingabeaufforderung im Administratormodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a257-147">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="6a257-148">Windows</span><span class="sxs-lookup"><span data-stu-id="6a257-148">Windows</span></span>](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[<span data-ttu-id="6a257-149">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="6a257-149">Mac/Linux</span></span>](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

<span data-ttu-id="6a257-150">Nachdem Sie alles installiert und die Umgebungsvariablen festgelegt haben, öffnen Sie eine **neue** Eingabeaufforderung oder ein Terminal, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6a257-150">Once you've installed everything and set your environment variables, open a **new** command prompt or terminal and run the following command:</span></span>

```text
spark-submit --version
```

<span data-ttu-id="6a257-151">Wenn der Befehl ausgeführt wird und Versionsinformationen ausgibt, können Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6a257-151">If the command runs and prints version information, you can move to the next step.</span></span>

<span data-ttu-id="6a257-152">Wenn Sie einen `'spark-submit' is not recognized as an internal or external command`-Fehler erhalten, stellen Sie sicher, dass Sie eine **neue** Eingabeaufforderung geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-152">If you receive a `'spark-submit' is not recognized as an internal or external command` error, make sure you opened a **new** command prompt.</span></span>

### <a name="5-install-net-for-apache-spark"></a><span data-ttu-id="6a257-153">5. Installieren von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-153">5. Install .NET for Apache Spark</span></span>

<span data-ttu-id="6a257-154">Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von GitHub für .NET für Apache Spark herunter.</span><span class="sxs-lookup"><span data-stu-id="6a257-154">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub.</span></span> <span data-ttu-id="6a257-155">Wenn Sie beispielsweise einen Windows-Computer nutzen und die Verwendung von .NET Core planen, [laden Sie das Windows x64 netcoreapp3.1-Release herunter](https://github.com/dotnet/spark/releases).</span><span class="sxs-lookup"><span data-stu-id="6a257-155">For example if you're on a Windows machine and plan to use .NET Core, [download the Windows x64 netcoreapp3.1 release](https://github.com/dotnet/spark/releases).</span></span>

<span data-ttu-id="6a257-156">So extrahieren Sie Microsoft.Spark.Worker:</span><span class="sxs-lookup"><span data-stu-id="6a257-156">To extract the Microsoft.Spark.Worker:</span></span>

* <span data-ttu-id="6a257-157">Suchen Sie die Datei **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip**, die Sie heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-157">Locate the **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip** file that you downloaded.</span></span>
* <span data-ttu-id="6a257-158">Klicken Sie mit der rechten Maustaste, und wählen Sie **7-Zip > Extract files** (7-Zip > Dateien extrahieren) aus.</span><span class="sxs-lookup"><span data-stu-id="6a257-158">Right-click and select **7-Zip -> Extract files...**.</span></span>
* <span data-ttu-id="6a257-159">Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.</span><span class="sxs-lookup"><span data-stu-id="6a257-159">Enter **C:\bin** in the **Extract to** field.</span></span>
* <span data-ttu-id="6a257-160">Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.</span><span class="sxs-lookup"><span data-stu-id="6a257-160">Uncheck the checkbox below the **Extract to** field.</span></span>
* <span data-ttu-id="6a257-161">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a257-161">Select **OK**.</span></span>

### <a name="6-install-winutils-windows-only"></a><span data-ttu-id="6a257-162">6. Installieren von WinUtils (nur Windows)</span><span class="sxs-lookup"><span data-stu-id="6a257-162">6. Install WinUtils (Windows only)</span></span>

<span data-ttu-id="6a257-163">.NET für Apache Spark erfordert die Installation von WinUtils neben Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="6a257-163">.NET for Apache Spark requires WinUtils to be installed alongside Apache Spark.</span></span> <span data-ttu-id="6a257-164">[Laden Sie die winutils.exe-Datei herunter](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span><span class="sxs-lookup"><span data-stu-id="6a257-164">[Download winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe).</span></span> <span data-ttu-id="6a257-165">Kopieren Sie dann WinUtils in **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span><span class="sxs-lookup"><span data-stu-id="6a257-165">Then, copy WinUtils into **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.</span></span>

> [!NOTE]
> <span data-ttu-id="6a257-166">Wenn Sie eine andere Version von Hadoop verwenden (dies ist am Ende des Namens Ihres Spark-Installationsordner angemerkt), [wählen Sie die Version von WinUtils aus](https://github.com/steveloughran/winutils), die mit Ihrer Version von Hadoop kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="6a257-166">If you are using a different version of Hadoop, which is annotated at the end of your Spark install folder name, [select the version of WinUtils](https://github.com/steveloughran/winutils) that's compatible with your version of Hadoop.</span></span>

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a><span data-ttu-id="6a257-167">7. Festlegen von DOTNET_WORKER_DIR und Überprüfen von Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="6a257-167">7. Set DOTNET_WORKER_DIR and check dependencies</span></span>

<span data-ttu-id="6a257-168">Führen Sie einen der folgenden Befehle aus, um die Umgebungsvariable `DOTNET_WORKER_DIR` festzulegen, die von .NET-Apps für die Suche nach Workerbinärdateien für .NET für Apache Spark verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a257-168">Run one of the following commands to set the `DOTNET_WORKER_DIR` environment variable, which is used by .NET apps to locate .NET for Apache Spark worker binaries.</span></span> <span data-ttu-id="6a257-169">Stellen Sie sicher, dass Sie `<PATH-DOTNET_WORKER_DIR>` durch das Verzeichnis ersetzen, in das Sie `Microsoft.Spark.Worker` heruntergeladen und extrahiert haben.</span><span class="sxs-lookup"><span data-stu-id="6a257-169">Make sure to replace `<PATH-DOTNET_WORKER_DIR>` with the directory where you downloaded and extracted the `Microsoft.Spark.Worker`.</span></span> <span data-ttu-id="6a257-170">Stellen Sie unter Windows sicher, dass Sie die Eingabeaufforderung im Administratormodus ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a257-170">On Windows, make sure to run the command prompt in administrator mode.</span></span>

#### <a name="windows"></a>[<span data-ttu-id="6a257-171">Windows</span><span class="sxs-lookup"><span data-stu-id="6a257-171">Windows</span></span>](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[<span data-ttu-id="6a257-172">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="6a257-172">Mac/Linux</span></span>](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

<span data-ttu-id="6a257-173">Überprüfen Sie abschließend, ob Sie `dotnet`, `java` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6a257-173">Finally, double-check that you can run `dotnet`, `java`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="6a257-174">Programmieren einer .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="6a257-174">Write a .NET for Apache Spark app</span></span>

### <a name="1-create-a-console-app"></a><span data-ttu-id="6a257-175">1. Erstellen einer Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="6a257-175">1. Create a console app</span></span>

<span data-ttu-id="6a257-176">Führen Sie in der Eingabeaufforderung oder im Terminal die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6a257-176">In your command prompt or terminal, run the following commands to create a new console application:</span></span>

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

<span data-ttu-id="6a257-177">Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`.</span><span class="sxs-lookup"><span data-stu-id="6a257-177">The `dotnet` command creates a `new` application of type `console` for you.</span></span> <span data-ttu-id="6a257-178">Der `-o`-Parameter erstellt ein Verzeichnis namens *MySparkApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf.</span><span class="sxs-lookup"><span data-stu-id="6a257-178">The `-o` parameter creates a directory named *MySparkApp* where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="6a257-179">Mit dem Befehl `cd MySparkApp` wird das Verzeichnis in das erstellte App-Verzeichnis geändert.</span><span class="sxs-lookup"><span data-stu-id="6a257-179">The `cd MySparkApp` command changes the directory to the app directory you created.</span></span>

### <a name="2-install-nuget-package"></a><span data-ttu-id="6a257-180">2. Installieren des NuGet-Pakets</span><span class="sxs-lookup"><span data-stu-id="6a257-180">2. Install NuGet package</span></span>

<span data-ttu-id="6a257-181">Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket.</span><span class="sxs-lookup"><span data-stu-id="6a257-181">To use .NET for Apache Spark in an app, install the Microsoft.Spark package.</span></span> <span data-ttu-id="6a257-182">Führen Sie in der Eingabeaufforderung oder im Terminal den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="6a257-182">In your command prompt or terminal, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> <span data-ttu-id="6a257-183">In diesem Tutorial wird die neueste Version des NuGet-Pakets `Microsoft.Spark` verwendet, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="6a257-183">This tutorial uses the latest version of the `Microsoft.Spark` NuGet package unless otherwise specified.</span></span>

### <a name="3-write-your-app"></a><span data-ttu-id="6a257-184">3. Schreiben der App</span><span class="sxs-lookup"><span data-stu-id="6a257-184">3. Write your app</span></span>

<span data-ttu-id="6a257-185">Öffnen Sie *Program.cs* in Visual Studio Code oder in einem beliebigen Text-Editor, und ersetzen Sie den gesamten Code durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6a257-185">Open *Program.cs* in Visual Studio Code, or any text editor, and replace all of the code with the following:</span></span>

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

<span data-ttu-id="6a257-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) ist der Einstiegspunkt von Apache Spark-Anwendungen, der den Kontext und Informationen zu Ihrer Anwendung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6a257-186">[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) is the entrypoint of Apache Spark applications, which manages the context and information of your application.</span></span> <span data-ttu-id="6a257-187">Mithilfe der [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A)-Methode werden die Textdaten aus der Datei, die durch `filePath` angegeben wird, in einen [DataFrame](xref:Microsoft.Spark.Sql.DataFrame) gelesen.</span><span class="sxs-lookup"><span data-stu-id="6a257-187">Using the [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) method, the text data from the file specified by the `filePath` is read into a [DataFrame](xref:Microsoft.Spark.Sql.DataFrame).</span></span> <span data-ttu-id="6a257-188">Ein DataFrame ist eine Möglichkeit zum Organisieren von Daten in eine Gruppe von benannten Spalten.</span><span class="sxs-lookup"><span data-stu-id="6a257-188">A DataFrame is a way of organizing data into a set of named columns.</span></span> <span data-ttu-id="6a257-189">Anschließend wird eine Reihe von Transformationen angewendet, um die Sätze in der Datei aufzuteilen, die einzelnen Wörter zu gruppieren, sie zu zählen und in absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="6a257-189">Then, a series of transformations is applied to split the sentences in the file, group each of the words, count them and order them in descending order.</span></span> <span data-ttu-id="6a257-190">Das Ergebnis dieser Vorgänge wird in einem anderen DataFrame gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6a257-190">The result of these operations is stored in another DataFrame.</span></span> <span data-ttu-id="6a257-191">Beachten Sie, dass zu diesem Zeitpunkt keine Vorgänge stattgefunden haben, da .NET für Apache Spark die Daten verzögert auswertet.</span><span class="sxs-lookup"><span data-stu-id="6a257-191">Note that at this point, no operations have taken place because .NET for Apache Spark lazily evaluates the data.</span></span> <span data-ttu-id="6a257-192">Erst wenn die [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A)-Methode aufgerufen wird, um den Inhalt des transformierten `words`-DataFrame in der Konsole anzuzeigen, werden die Vorgänge, die in den Zeilen oben definiert wurden, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a257-192">It's not until the [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) method is called to display the contents of the `words` transformed DataFrame to the console that the operations defined in the lines above execute.</span></span> <span data-ttu-id="6a257-193">Wenn Sie die Spark-Sitzung nicht mehr benötigen, verwenden Sie die [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A)-Methode zum Beenden der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6a257-193">Once you no longer need the Spark session, use the [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A) method to stop your session.</span></span>

### <a name="4-create-data-file"></a><span data-ttu-id="6a257-194">4. Erstellen der Datendatei</span><span class="sxs-lookup"><span data-stu-id="6a257-194">4. Create data file</span></span>

<span data-ttu-id="6a257-195">Ihre App verarbeitet eine Datei mit Textzeilen.</span><span class="sxs-lookup"><span data-stu-id="6a257-195">Your app processes a file containing lines of text.</span></span> <span data-ttu-id="6a257-196">Erstellen Sie eine Datei *input.txt* in Ihrem Verzeichnis *MySparkApp*, die den folgenden Text enthält:</span><span class="sxs-lookup"><span data-stu-id="6a257-196">Create a file called *input.txt* file in your *MySparkApp* directory, containing the following text:</span></span>

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

<span data-ttu-id="6a257-197">Speichern Sie die Änderungen, und schließen Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="6a257-197">Save the changes and close the file.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="6a257-198">Ausführen der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="6a257-198">Run your .NET for Apache Spark app</span></span>

<span data-ttu-id="6a257-199">Führen Sie den folgenden Befehl aus, um die Anwendung zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="6a257-199">Run the following command to build your application:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="6a257-200">Navigieren Sie zum Buildausgabeverzeichnis, und verwenden Sie den `spark-submit`-Befehl, um Ihre Anwendung für die Ausführung unter Apache Spark zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="6a257-200">Navigate to your build output directory and use the `spark-submit` command to submit your application to run on Apache Spark.</span></span> <span data-ttu-id="6a257-201">Stellen Sie sicher, dass Sie `<version>` durch die Version des .NET-Workers und `<path-of-input.txt>` durch den Pfad der Datei *input.txt* ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6a257-201">Make sure to replace  `<version>` with the version of your .NET worker and `<path-of-input.txt>` with the path of your *input.txt* file is stored.</span></span>

### <a name="windows"></a>[<span data-ttu-id="6a257-202">Windows</span><span class="sxs-lookup"><span data-stu-id="6a257-202">Windows</span></span>](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[<span data-ttu-id="6a257-203">Mac/Linux</span><span class="sxs-lookup"><span data-stu-id="6a257-203">Mac/Linux</span></span>](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> <span data-ttu-id="6a257-204">Bei diesem Befehl wird davon ausgegangen, dass Sie Apache Spark heruntergeladen und der Umgebungsvariablen „PATH“ hinzugefügt haben, damit `spark-submit` verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6a257-204">This command assumes you have downloaded Apache Spark and added it to your PATH environment variable to be able to use `spark-submit`.</span></span> <span data-ttu-id="6a257-205">Andernfalls müssten Sie den vollständigen Pfad (z. B. *C:\bin\apache-spark\bin\spark-submit* oder *~/spark/bin/spark-submit*) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a257-205">Otherwise, you'd have to use the full path (for example, *C:\bin\apache-spark\bin\spark-submit* or *~/spark/bin/spark-submit*).</span></span>

<span data-ttu-id="6a257-206">Wenn Ihre App ausgeführt wird, werden die Wortzähldaten der Datei *Input.txt* in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6a257-206">When your app runs, the word count data of the *input.txt* file is written to the console.</span></span>

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

<span data-ttu-id="6a257-207">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="6a257-207">Congratulations!</span></span> <span data-ttu-id="6a257-208">Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6a257-208">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6a257-209">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6a257-209">Next steps</span></span>

<span data-ttu-id="6a257-210">In diesem Tutorial haben Sie Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="6a257-210">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="6a257-211">Vorbereiten der Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-211">Prepare your environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="6a257-212">Schreiben einer ersten .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a257-212">Write your first .NET for Apache Spark application</span></span>
> * <span data-ttu-id="6a257-213">Erstellen und Ausführen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="6a257-213">Build and run your .NET for Apache Spark application</span></span>

<span data-ttu-id="6a257-214">Ein Video, in dem die oben aufgeführten Schritte erläutert werden, finden Sie in der [Videoserie zu .NET für Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span><span class="sxs-lookup"><span data-stu-id="6a257-214">To see a video explaining the steps above, check out the [.NET for Apache Spark 101 video series](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).</span></span>

<span data-ttu-id="6a257-215">Weitere Informationen finden Sie auf der Ressourcenseite.</span><span class="sxs-lookup"><span data-stu-id="6a257-215">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6a257-216">Ressourcen für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="6a257-216">.NET for Apache Spark Resources</span></span>](../resources/index.md)
