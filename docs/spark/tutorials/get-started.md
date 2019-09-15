---
title: Erste Schritte mit .NET für Apache Spark
description: Erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 004256a2fe369b026b15151dfc72ae379da0be8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928485"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a><span data-ttu-id="17c06-103">Tutorial: Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="17c06-103">Tutorial: Get started with .NET for Apache Spark</span></span>

<span data-ttu-id="17c06-104">In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="17c06-104">This tutorial teaches you how to run a .NET for Apache Spark app using .NET Core on Windows.</span></span>

<span data-ttu-id="17c06-105">In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="17c06-105">In this tutorial, you learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="17c06-106">Vorbereiten der Windows-Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="17c06-106">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="17c06-107">Herunterladen von **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="17c06-107">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="17c06-108">Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="17c06-108">Build and run a simple .NET for Apache Spark application</span></span>

## <a name="prepare-your-environment"></a><span data-ttu-id="17c06-109">Vorbereiten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="17c06-109">Prepare your environment</span></span>

<span data-ttu-id="17c06-110">Überprüfen Sie zuerst, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="17c06-110">Before you begin, make sure you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line.</span></span> <span data-ttu-id="17c06-111">Wenn Sie Ihre Umgebung bereits vorbereitet haben, können Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="17c06-111">If your environment is already prepared, you can skip to the next section.</span></span> <span data-ttu-id="17c06-112">Wenn Sie keine oder nicht alle Befehle ausführen können, müssen Sie zuerst die folgenden Schritte abarbeiten.</span><span class="sxs-lookup"><span data-stu-id="17c06-112">If you cannot run any or all of the commands, follow the steps below.</span></span>

1. <span data-ttu-id="17c06-113">Laden Sie das [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="17c06-113">Download and install the [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span> <span data-ttu-id="17c06-114">Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="17c06-114">Installing the SDK adds the `dotnet` toolchain to your PATH.</span></span> <span data-ttu-id="17c06-115">Verwenden Sie den PowerShell-Befehl `dotnet --version`, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17c06-115">Use the PowerShell command `dotnet --version` to verify the installation.</span></span>

2. <span data-ttu-id="17c06-116">Installieren Sie [Visual Studio 2017](https://www.visualstudio.com/downloads/) oder [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) mit den neuesten Updates.</span><span class="sxs-lookup"><span data-stu-id="17c06-116">Install [Visual Studio 2017](https://www.visualstudio.com/downloads/) or [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) with the latest updates.</span></span> <span data-ttu-id="17c06-117">Sie können die Versionen Community, Professional oder Enterprise verwenden.</span><span class="sxs-lookup"><span data-stu-id="17c06-117">You can use Community, Professional, or Enterprise.</span></span> <span data-ttu-id="17c06-118">Die Community-Version ist kostenlos.</span><span class="sxs-lookup"><span data-stu-id="17c06-118">The Community version is free.</span></span>

   <span data-ttu-id="17c06-119">Wählen Sie während der Installation die folgenden Workloads aus:</span><span class="sxs-lookup"><span data-stu-id="17c06-119">Choose the following workloads during installation:</span></span>
      * <span data-ttu-id="17c06-120">.NET-Desktopentwicklung</span><span class="sxs-lookup"><span data-stu-id="17c06-120">.NET desktop development</span></span>
          * <span data-ttu-id="17c06-121">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="17c06-121">All required components</span></span>
          * <span data-ttu-id="17c06-122">.NET Framework 4.6.1-Entwicklungstools</span><span class="sxs-lookup"><span data-stu-id="17c06-122">.NET Framework 4.6.1 Development Tools</span></span>
      * <span data-ttu-id="17c06-123">Plattformübergreifende .NET Core-Entwicklung</span><span class="sxs-lookup"><span data-stu-id="17c06-123">.NET Core cross-platform development</span></span>
          * <span data-ttu-id="17c06-124">Alle erforderlichen Komponenten</span><span class="sxs-lookup"><span data-stu-id="17c06-124">All required components</span></span>

3. <span data-ttu-id="17c06-125">Installieren Sie [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span><span class="sxs-lookup"><span data-stu-id="17c06-125">Install [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).</span></span>

    * <span data-ttu-id="17c06-126">Wählen Sie die für Ihr Betriebssystem geeignete Version aus.</span><span class="sxs-lookup"><span data-stu-id="17c06-126">Select the appropriate version for your operating system.</span></span> <span data-ttu-id="17c06-127">Für einen Windows-Computer mit x64-Architektur wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** aus.</span><span class="sxs-lookup"><span data-stu-id="17c06-127">For example, select **jdk-8u201-windows-x64.exe** for a Windows x64 machine.</span></span>
    * <span data-ttu-id="17c06-128">Verwenden Sie den PowerShell-Befehl `java -version`, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17c06-128">Use the PowerShell command `java -version` to verify the installation.</span></span>

4. <span data-ttu-id="17c06-129">Installieren Sie [Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi).</span><span class="sxs-lookup"><span data-stu-id="17c06-129">Install [Apache Maven 3.6.0+](https://maven.apache.org/download.cgi).</span></span>
    * <span data-ttu-id="17c06-130">Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip) herunter.</span><span class="sxs-lookup"><span data-stu-id="17c06-130">Download [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip).</span></span>
    * <span data-ttu-id="17c06-131">Extrahieren Sie die Datei in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="17c06-131">Extract to a local directory.</span></span> <span data-ttu-id="17c06-132">Beispielsweise `c:\bin\apache-maven-3.6.0\`.</span><span class="sxs-lookup"><span data-stu-id="17c06-132">For example, `c:\bin\apache-maven-3.6.0\`.</span></span>
    * <span data-ttu-id="17c06-133">Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Maven hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-133">Add Apache Maven to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="17c06-134">Wenn Sie bei der Extraktion `c:\bin\apache-maven-3.6.0\` als Zielverzeichnis angegeben haben, fügen Sie PATH `c:\bin\apache-maven-3.6.0\bin` hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-134">If you extracted to `c:\bin\apache-maven-3.6.0\`, you would add `c:\bin\apache-maven-3.6.0\bin` to your PATH.</span></span>
    * <span data-ttu-id="17c06-135">Verwenden Sie den PowerShell-Befehl `mvn -version`, um die Installation zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17c06-135">Use the PowerShell command `mvn -version` to verify the installation.</span></span>

5. <span data-ttu-id="17c06-136">Installieren Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html).</span><span class="sxs-lookup"><span data-stu-id="17c06-136">Install [Apache Spark 2.3+](https://spark.apache.org/downloads.html).</span></span> <span data-ttu-id="17c06-137">Apache Spark 2.4 und höher wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="17c06-137">Apache Spark 2.4+ isn't supported.</span></span>
    * <span data-ttu-id="17c06-138">Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei mit einem Tool wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/) in einen lokalen Ordner.</span><span class="sxs-lookup"><span data-stu-id="17c06-138">Download [Apache Spark 2.3+](https://spark.apache.org/downloads.html) and extract it into a local folder using a tool like [7-zip](https://www.7-zip.org/) or [WinZip](https://www.winzip.com/).</span></span> <span data-ttu-id="17c06-139">Sie können beispielsweise `c:\bin\spark-2.3.2-bin-hadoop2.7\` als Extraktionsverzeichnis verwenden.</span><span class="sxs-lookup"><span data-stu-id="17c06-139">For example, you might extract it to `c:\bin\spark-2.3.2-bin-hadoop2.7\`.</span></span>
    * <span data-ttu-id="17c06-140">Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Spark hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-140">Add Apache Spark to your [PATH environment variable](https://www.java.com/en/download/help/path.xml).</span></span> <span data-ttu-id="17c06-141">Wenn Sie bei der Extraktion `c:\bin\spark-2.3.2-bin-hadoop2.7\` als Zielverzeichnis angegeben haben, fügen Sie PATH `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-141">If you extracted to `c:\bin\spark-2.3.2-bin-hadoop2.7\`, you would add `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` to your PATH.</span></span>
    * <span data-ttu-id="17c06-142">Fügen Sie [eine neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `SPARK_HOME` hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-142">Add a [new environment variable](https://www.java.com/en/download/help/path.xml) called `SPARK_HOME`.</span></span> <span data-ttu-id="17c06-143">Wenn Sie bei der Extraktion `C:\bin\spark-2.3.2-bin-hadoop2.7\` als Zielverzeichnis angegeben haben, legen Sie `C:\bin\spark-2.3.2-bin-hadoop2.7\` als **Variablenwert** fest.</span><span class="sxs-lookup"><span data-stu-id="17c06-143">If you extracted to `C:\bin\spark-2.3.2-bin-hadoop2.7\`, use  `C:\bin\spark-2.3.2-bin-hadoop2.7\` for the **Variable value**.</span></span>
    * <span data-ttu-id="17c06-144">Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.</span><span class="sxs-lookup"><span data-stu-id="17c06-144">Verify you are able to run `spark-shell` from your command line.</span></span>

6. <span data-ttu-id="17c06-145">Richten Sie [WinUtils](https://github.com/steveloughran/winutils) ein.</span><span class="sxs-lookup"><span data-stu-id="17c06-145">Set up [WinUtils](https://github.com/steveloughran/winutils).</span></span>
    * <span data-ttu-id="17c06-146">Laden Sie die Binärdatei **winutils.exe** aus dem [WinUtils-Repository](https://github.com/steveloughran/winutils) herunter.</span><span class="sxs-lookup"><span data-stu-id="17c06-146">Download the **winutils.exe** binary from [WinUtils repository](https://github.com/steveloughran/winutils).</span></span> <span data-ttu-id="17c06-147">Wählen Sie die Hadoop-Version aus, mit der die Spark-Distribution kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="17c06-147">Select the version of Hadoop the Spark distribution was compiled with.</span></span> <span data-ttu-id="17c06-148">Für **Spark 2.3.2** verwenden Sie beispielsweise **hadoop-2.7.1**.</span><span class="sxs-lookup"><span data-stu-id="17c06-148">For example, you use **hadoop-2.7.1** for **Spark 2.3.2**.</span></span> <span data-ttu-id="17c06-149">Die Hadoop-Version ist abschließend in der Bezeichnung des Spark-Installationsordners enthalten.</span><span class="sxs-lookup"><span data-stu-id="17c06-149">The Hadoop version is annotated at the end of your Spark install folder name.</span></span>
    * <span data-ttu-id="17c06-150">Speichern Sie die Binärdatei **winutils.exe** in einem beliebigen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="17c06-150">Save the **winutils.exe** binary to a directory of your choice.</span></span> <span data-ttu-id="17c06-151">Beispielsweise `c:\hadoop\bin`.</span><span class="sxs-lookup"><span data-stu-id="17c06-151">For example, `c:\hadoop\bin`.</span></span>
    * <span data-ttu-id="17c06-152">Legen Sie für `HADOOP_HOME` das Verzeichnis fest, in dem sich **winutils.exe** befindet, und lassen Sie dabei `bin` weg.</span><span class="sxs-lookup"><span data-stu-id="17c06-152">Set `HADOOP_HOME` to reflect the directory with **winutils.exe** without `bin`.</span></span> <span data-ttu-id="17c06-153">Beispielsweise `c:\hadoop`.</span><span class="sxs-lookup"><span data-stu-id="17c06-153">For example, `c:\hadoop`.</span></span>
    * <span data-ttu-id="17c06-154">Fügen Sie der PATH-Umgebungsvariable `%HADOOP_HOME%\bin` hinzu.</span><span class="sxs-lookup"><span data-stu-id="17c06-154">Set the PATH environment variable to include `%HADOOP_HOME%\bin`.</span></span>

<span data-ttu-id="17c06-155">Überprüfen Sie, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="17c06-155">Double check that you can run `dotnet`, `java`, `mvn`, `spark-shell` from your command line before you move to the next section.</span></span>

## <a name="download-the-microsoftsparkworker-release"></a><span data-ttu-id="17c06-156">Herunterladen des Microsoft.Spark.Worker-Release</span><span class="sxs-lookup"><span data-stu-id="17c06-156">Download the Microsoft.Spark.Worker release</span></span>

1. <span data-ttu-id="17c06-157">Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von der GitHub-Releaseseite für .NET für Apache Spark auf Ihren lokalen Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="17c06-157">Download the [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) release from the .NET for Apache Spark GitHub Releases page to your local machine.</span></span> <span data-ttu-id="17c06-158">Beispielsweise können Sie für den Download der Datei den Pfad `c:\bin\Microsoft.Spark.Worker\` verwenden.</span><span class="sxs-lookup"><span data-stu-id="17c06-158">For example, you might download it to the path, `c:\bin\Microsoft.Spark.Worker\`.</span></span>

2. <span data-ttu-id="17c06-159">Erstellen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `DotnetWorkerPath`, und legen Sie diese auf das Verzeichnis fest, in dem sich die heruntergeladene und extrahierte **Microsoft.Spark.Worker**-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="17c06-159">Create a [new environment variable](https://www.java.com/en/download/help/path.xml) called `DotnetWorkerPath` and set it to the directory where you downloaded and extracted the **Microsoft.Spark.Worker**.</span></span> <span data-ttu-id="17c06-160">Beispielsweise `c:\bin\Microsoft.Spark.Worker`.</span><span class="sxs-lookup"><span data-stu-id="17c06-160">For example, `c:\bin\Microsoft.Spark.Worker`.</span></span>

## <a name="clone-the-net-for-apache-spark-github-repo"></a><span data-ttu-id="17c06-161">Klonen des GitHub-Repositorys von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="17c06-161">Clone the .NET for Apache Spark GitHub repo</span></span>

<span data-ttu-id="17c06-162">Verwenden Sie den folgenden [GitBash](https://gitforwindows.org/)-Befehl, um das .NET für Apache Spark-Repository auf Ihrem Computer zu klonen.</span><span class="sxs-lookup"><span data-stu-id="17c06-162">Use the following [GitBash](https://gitforwindows.org/) command to clone the .NET for Apache Spark repo to your machine.</span></span>

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a><span data-ttu-id="17c06-163">Programmieren einer .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="17c06-163">Write a .NET for Apache Spark app</span></span>

1. <span data-ttu-id="17c06-164">Öffnen Sie **Visual Studio**, und navigieren Sie zu **Datei > Neues Projekt erstellen > Konsolen-App (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="17c06-164">Open **Visual Studio** and navigate to **File > Create New Project > Console App (.NET Core)**.</span></span> <span data-ttu-id="17c06-165">Nennen Sie die Anwendung **HelloSpark**.</span><span class="sxs-lookup"><span data-stu-id="17c06-165">Name the application **HelloSpark**.</span></span>

2. <span data-ttu-id="17c06-166">Installieren Sie das [NuGet-Paket Microsoft.Spark](https://www.nuget.org/profiles/spark).</span><span class="sxs-lookup"><span data-stu-id="17c06-166">Install the [Microsoft.Spark NuGet package](https://www.nuget.org/profiles/spark).</span></span> <span data-ttu-id="17c06-167">Weitere Informationen zum Installieren von NuGet-Paketen finden Sie unter [Installationsmöglichkeiten für NuGet-Pakete](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span><span class="sxs-lookup"><span data-stu-id="17c06-167">For more information on installing NuGet packages, see [Different ways to install a NuGet Package](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).</span></span>

3. <span data-ttu-id="17c06-168">Öffnen Sie im **Projektmappen-Explorer** die Datei **Program.cs**, und fügen Sie den folgenden C#-Code ein:</span><span class="sxs-lookup"><span data-stu-id="17c06-168">In **Solution Explorer**, open **Program.cs** and write the following C# code:</span></span>

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. <span data-ttu-id="17c06-169">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="17c06-169">Build the solution.</span></span>

## <a name="run-your-net-for-apache-spark-app"></a><span data-ttu-id="17c06-170">Ausführen der .NET für Apache Spark-App</span><span class="sxs-lookup"><span data-stu-id="17c06-170">Run your .NET for Apache Spark app</span></span>

1. <span data-ttu-id="17c06-171">Öffnen Sie **PowerShell**, und legen Sie für das Verzeichnis den Ordner fest, in dem Ihre App gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="17c06-171">Open **PowerShell** and change the directory to the folder where your app is stored.</span></span>

   ```powershell
   cd <your-app-output-directory>
   ```

2. <span data-ttu-id="17c06-172">Erstellen Sie eine Datei mit dem Namen **project.json** und dem folgendem Inhalt:</span><span class="sxs-lookup"><span data-stu-id="17c06-172">Create a file called **people.json** with the following content:</span></span>

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. <span data-ttu-id="17c06-173">Verwenden Sie den folgenden PowerShell-Befehl, um die App auszuführen:</span><span class="sxs-lookup"><span data-stu-id="17c06-173">Use the following PowerShell command to run your app:</span></span>

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

<span data-ttu-id="17c06-174">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="17c06-174">Congratulations!</span></span> <span data-ttu-id="17c06-175">Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="17c06-175">You successfully authored and ran a .NET for Apache Spark app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="17c06-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="17c06-176">Next steps</span></span>

<span data-ttu-id="17c06-177">In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="17c06-177">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> * <span data-ttu-id="17c06-178">Vorbereiten der Windows-Umgebung für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="17c06-178">Prepare your Windows environment for .NET for Apache Spark</span></span>
> * <span data-ttu-id="17c06-179">Herunterladen von **Microsoft.Spark.Worker**</span><span class="sxs-lookup"><span data-stu-id="17c06-179">Download the **Microsoft.Spark.Worker**</span></span>
> * <span data-ttu-id="17c06-180">Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="17c06-180">Build and run a simple .NET for Apache Spark application</span></span>

<span data-ttu-id="17c06-181">Weitere Informationen finden Sie auf der Ressourcenseite.</span><span class="sxs-lookup"><span data-stu-id="17c06-181">Check out the resources page to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="17c06-182">Ressourcen für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="17c06-182">.NET for Apache Spark Resources</span></span>](../resources/index.md)
