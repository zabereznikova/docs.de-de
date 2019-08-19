---
title: Beginnen Sie mit .net für Apache Spark
description: Erfahren Sie, wie Sie mit .net Core unter Windows eine .net für Apache Spark-app ausführen.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577007"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="24c41-103">Tutorial: Beginnen Sie mit .net für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="24c41-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="24c41-104">In diesem Tutorial erfahren Sie, wie Sie mit .net Core unter Windows eine .net für Apache Spark-app ausführen.</span><span class="sxs-lookup"><span data-stu-id="24c41-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="24c41-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="24c41-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="24c41-106">Vorbereiten der Windows-Umgebung für .net für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="24c41-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="24c41-107">Herunterladen von " **Microsoft. Spark. Worker** "</span><span class="sxs-lookup"><span data-stu-id="24c41-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="24c41-108">Erstellen und Ausführen einer einfachen .net für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="24c41-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="24c41-109">Vorbereiten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="24c41-109">Prepare your environment</span></span>

<span data-ttu-id="24c41-110">Bevor Sie beginnen, stellen Sie sicher, dass `dotnet`Sie `java`, `mvn`, `spark-shell` , über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="24c41-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="24c41-111">Wenn Ihre Umgebung bereits vorbereitet ist, können Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="24c41-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="24c41-112">Wenn Sie keine oder alle Befehle ausführen können, führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="24c41-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="24c41-113">Laden Sie das [.net Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="24c41-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="24c41-114">Wenn Sie das SDK installieren `dotnet` , wird die Toolkette dem Pfad hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="24c41-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="24c41-115">Verwenden Sie den PowerShell `dotnet --version` -Befehl, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="24c41-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="24c41-116">Installieren Sie [Visual Studio 2017](https://www.visualstudio.com/downloads/) oder [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) mit den neuesten Updates.</span><span class="sxs-lookup"><span data-stu-id="24c41-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="24c41-117">Sie können Community, Professional oder Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="24c41-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="24c41-118">Die Community-Version ist kostenlos.</span><span class="sxs-lookup"><span data-stu-id="24c41-118">The Community version is free.</span></span>

   <span data-ttu-id="24c41-119">Wählen Sie während der Installation die folgenden Workloads aus:</span><span class="sxs-lookup"><span data-stu-id="24c41-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="24c41-120">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="24c41-120">.NET desktop development</span></span>
          * <span data-ttu-id="24c41-121">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="24c41-121">All required components</span></span>
          * <span data-ttu-id="24c41-122">.NET Framework 4.6.1-Entwicklungs Tools</span><span class="sxs-lookup"><span data-stu-id="24c41-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="24c41-123">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="24c41-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="24c41-124">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="24c41-124">All required components</span></span>

3. <span data-ttu-id="24c41-125">Installieren Sie [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="24c41-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="24c41-126">Wählen Sie die für Ihr Betriebssystem geeignete Version aus.</span><span class="sxs-lookup"><span data-stu-id="24c41-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="24c41-127">Wählen Sie z. b. **JDK-8u201-Windows-x64. exe** für einen Windows x64-Computer aus.</span><span class="sxs-lookup"><span data-stu-id="24c41-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="24c41-128">Verwenden Sie den PowerShell `java -version` -Befehl, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="24c41-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="24c41-129">Installieren Sie [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="24c41-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="24c41-130">Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)herunter.</span><span class="sxs-lookup"><span data-stu-id="24c41-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="24c41-131">In ein lokales Verzeichnis extrahieren.</span><span class="sxs-lookup"><span data-stu-id="24c41-131">Extract to a local directory.</span></span> <span data-ttu-id="24c41-132">Beispielsweise `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="24c41-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="24c41-133">Fügen Sie Apache Maven Ihrer [PATH-Umgebungsvariablen](https://www.java.com/en/download/help/path.xml)hinzu.</span><span class="sxs-lookup"><span data-stu-id="24c41-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="24c41-134">Wenn Sie in `c:\bin\apache-maven-3.6.0\`extrahiert haben, würden Sie `c:\bin\apache-maven-3.6.0\bin` zu Ihrem Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="24c41-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="24c41-135">Verwenden Sie den PowerShell `mvn -version` -Befehl, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="24c41-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="24c41-136">Installieren Sie [Apache Spark 2.3 +](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="24c41-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="24c41-137">Apache Spark 2.4 und höher wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="24c41-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="24c41-138">Laden Sie [Apache Spark 2.3](https://spark.apache.org/downloads.html) und höher herunter, und extrahieren Sie Sie mithilfe eines Tools wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/)in einen lokalen Ordner.</span><span class="sxs-lookup"><span data-stu-id="24c41-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="24c41-139">Beispielsweise können Sie Sie in `c:\bin\spark-2.3.2-bin-hadoop2.7\`extrahieren.</span><span class="sxs-lookup"><span data-stu-id="24c41-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="24c41-140">Fügen Sie Apache Spark Ihrer [PATH-Umgebungsvariablen](https://www.java.com/en/download/help/path.xml)hinzu.</span><span class="sxs-lookup"><span data-stu-id="24c41-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="24c41-141">Wenn Sie in `c:\bin\spark-2.3.2-bin-hadoop2.7\`extrahiert haben, würden Sie `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` zu Ihrem Pfad hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="24c41-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="24c41-142">Fügen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `SPARK_HOME`hinzu.</span><span class="sxs-lookup"><span data-stu-id="24c41-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="24c41-143">Wenn Sie in `C:\bin\spark-2.3.2-bin-hadoop2.7\`extrahiert haben, `C:\bin\spark-2.3.2-bin-hadoop2.7\` verwenden Sie für den **Variablen Wert**.</span><span class="sxs-lookup"><span data-stu-id="24c41-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="24c41-144">Vergewissern Sie sich, dass Sie `spark-shell` in der Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="24c41-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="24c41-145">Einrichten von [winutils](https://github.com/steveloughran/winutils).</span><span class="sxs-lookup"><span data-stu-id="24c41-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="24c41-146">Laden Sie die Binärdatei **winutils. exe** aus dem [winutils-Repository](https://github.com/steveloughran/winutils)herunter.</span><span class="sxs-lookup"><span data-stu-id="24c41-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="24c41-147">Wählen Sie die Version von Hadoop aus, mit der die Spark-Distribution kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="24c41-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="24c41-148">Beispielsweise verwenden Sie **Hadoop-2.7.1** für **Spark 2.3.2**.</span><span class="sxs-lookup"><span data-stu-id="24c41-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="24c41-149">Die Hadoop-Version wird am Ende Ihres Spark-Installationsordner namens mit Anmerkungen versehen.</span><span class="sxs-lookup"><span data-stu-id="24c41-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="24c41-150">Speichern Sie die Binärdatei " **winutils. exe** " in einem Verzeichnis Ihrer Wahl.</span><span class="sxs-lookup"><span data-stu-id="24c41-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="24c41-151">Beispielsweise `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="24c41-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="24c41-152">Legen `HADOOP_HOME` Sie fest, um das Verzeichnis mit **winutils. exe** ohne `bin`zu reflektieren.</span><span class="sxs-lookup"><span data-stu-id="24c41-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="24c41-153">Beispielsweise `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="24c41-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="24c41-154">Legen Sie die Umgebungsvariable PATH auf `%HADOOP_HOME%\bin`include fest.</span><span class="sxs-lookup"><span data-stu-id="24c41-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="24c41-155">Überprüfen Sie, ob Sie `dotnet` `mvn`, `java`,, `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="24c41-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="24c41-156">Herunterladen der Microsoft. Spark. Worker-Version</span><span class="sxs-lookup"><span data-stu-id="24c41-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="24c41-157">Laden Sie die [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) -Version von der .net for Apache Spark GitHub Releases-Seite auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="24c41-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="24c41-158">Beispielsweise können Sie die Datei in den Pfad `c:\bin\Microsoft.Spark.Worker\`herunterladen.</span><span class="sxs-lookup"><span data-stu-id="24c41-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="24c41-159">Erstellen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `DotnetWorkerPath` , und legen Sie Sie auf das Verzeichnis fest, in das Sie **Microsoft. Spark. Worker**heruntergeladen und extrahiert haben.</span><span class="sxs-lookup"><span data-stu-id="24c41-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="24c41-160">Beispielsweise `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="24c41-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="24c41-161">Klonen von .net für Apache Spark GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="24c41-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="24c41-162">Verwenden Sie den folgenden [gitbash](https://gitforwindows.org/) -Befehl, um .net für Apache Spark Repository auf Ihrem Computer zu klonen.</span><span class="sxs-lookup"><span data-stu-id="24c41-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="24c41-163">.Net für Apache Spark-app schreiben</span><span class="sxs-lookup"><span data-stu-id="24c41-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="24c41-164">Öffnen Sie **Visual Studio** , und navigieren Sie zu **Datei > Erstellen Sie ein neues Projekt > Konsolen-app (.net Core)** .</span><span class="sxs-lookup"><span data-stu-id="24c41-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="24c41-165">Nennen Sie die Anwendung **hellospark**.</span><span class="sxs-lookup"><span data-stu-id="24c41-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="24c41-166">Installieren Sie das [nuget-Paket Microsoft. Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="24c41-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="24c41-167">Weitere Informationen zum Installieren von nuget-Paketen finden [Sie unter verschiedene Möglichkeiten zum Installieren eines nuget-Pakets](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="24c41-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="24c41-168">ÖffnenSie in Projektmappen-Explorer **Program.cs** , und schreiben Sie C# den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="24c41-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="24c41-169">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="24c41-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="24c41-170">Ausführen der .net für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="24c41-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="24c41-171">Öffnen Sie **PowerShell** , und ändern Sie das Verzeichnis in den Ordner, in dem Ihre APP gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="24c41-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="24c41-172">Erstellen Sie eine Datei namens **People. JSON** mit folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="24c41-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="24c41-173">Verwenden Sie den folgenden PowerShell-Befehl, um die APP auszuführen:</span><span class="sxs-lookup"><span data-stu-id="24c41-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="24c41-174">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="24c41-174">Congratulations!</span></span> <span data-ttu-id="24c41-175">Sie haben .net für Apache Spark-App erfolgreich erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="24c41-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24c41-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="24c41-176">Next steps</span></span>

<span data-ttu-id="24c41-177">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="24c41-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="24c41-178">Vorbereiten der Windows-Umgebung für .net für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="24c41-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="24c41-179">Herunterladen von " **Microsoft. Spark. Worker** "</span><span class="sxs-lookup"><span data-stu-id="24c41-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="24c41-180">Erstellen und Ausführen einer einfachen .net für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="24c41-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="24c41-181">Weitere Informationen finden Sie auf der Ressourcenseite.</span><span class="sxs-lookup"><span data-stu-id="24c41-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="24c41-182">.Net für Apache Spark-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="24c41-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
