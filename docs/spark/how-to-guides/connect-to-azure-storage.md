---
title: Herstellen einer Verbindung mit Remotespeicher über Ihren lokalen Computer
description: Stellen Sie mithilfe von .NET für Apache Spark eine Verbindung mit Azure Storage-Konten über Ihren lokalen Computer her.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dc0c3b44279756596f3d456616821e690710ae04
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92224010"
---
# <a name="connect-to-azure-data-lake-storage-gen-2-or-wasb-account"></a><span data-ttu-id="7b237-103">Herstellen einer Verbindung mit einem Azure Data Lake Storage Gen2- oder WASB-Konto</span><span class="sxs-lookup"><span data-stu-id="7b237-103">Connect to Azure Data Lake Storage Gen 2 or WASB account</span></span>

<span data-ttu-id="7b237-104">In diesem Artikel erfahren Sie, wie Sie eine Verbindung mit einem ADLS Gen2- (Azure Data Lake Storage Gen2) oder WASB-Konto (Azure Storage Blob) über eine Instanz von [.NET für Apache Spark](https://github.com/dotnet/spark) herstellen, die lokal auf Ihrem Windows-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b237-104">In this article, you learn how to connect to an Azure Data Lake Storage (ADLS) Gen 2 or Windows Azure Storage Blob (WASB) account through an instance of [.NET for Apache Spark](https://github.com/dotnet/spark) running locally on your Windows machine.</span></span>

## <a name="set-up-the-environment"></a><span data-ttu-id="7b237-105">Einrichten der Umgebung</span><span class="sxs-lookup"><span data-stu-id="7b237-105">Set up the environment</span></span>

1. <span data-ttu-id="7b237-106">Laden Sie die Apache Spark-Distribution ohne Hadoop von der [offiziellen Website](https://archive.apache.org/dist/spark/) herunter (wählen Sie eine Version aus, die [von .NET für Apache Spark unterstützt wird](https://github.com/dotnet/spark#supported-apache-spark)), und extrahieren Sie sie in ein Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7b237-106">Download the Apache Spark distribution built without Hadoop from [official website](https://archive.apache.org/dist/spark/) (choose a version [supported by .NET for Apache Spark](https://github.com/dotnet/spark#supported-apache-spark)), and extract it to a directory.</span></span> <span data-ttu-id="7b237-107">Legen Sie die Umgebungsvariable `SPARK_HOME` auf dieses Verzeichnis fest.</span><span class="sxs-lookup"><span data-stu-id="7b237-107">Set the environment variable `SPARK_HOME` to this directory.</span></span>
2. <span data-ttu-id="7b237-108">Laden Sie die Apache Hadoop-Binärdatei [hier](http://hadoop.apache.org/releases.html) herunter, extrahieren Sie sie in einen Ordner, und legen Sie die Umgebungsvariable `HADOOP_HOME` auf diesen Ordner fest.</span><span class="sxs-lookup"><span data-stu-id="7b237-108">Download the Apache Hadoop binary from [here](http://hadoop.apache.org/releases.html) and extract to a folder, and set your `HADOOP_HOME` environment variable to this folder.</span></span>
3. <span data-ttu-id="7b237-109">Laden Sie die Dateien `winutils.exe` und `hadoop.dll` von [diesem Speicherort](https://github.com/cdarlint/winutils) herunter (abhängig von der Hadoop-Version, die Sie im vorherigen Schritt installiert haben), und fügen Sie diese in den bin-Ordner Ihrer Hadoop-Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="7b237-109">Download the `winutils.exe` and `hadoop.dll` files from [this location](https://github.com/cdarlint/winutils) (depending on the version of Hadoop installed in the previous step) and put them in the bin folder of your Hadoop.</span></span> <span data-ttu-id="7b237-110">Diese Binärdateien werden unter Windows benötigt, um alles ordnungsgemäß einzurichten (dies wird im [Apache-Wiki](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems) ausführlich erläutert).</span><span class="sxs-lookup"><span data-stu-id="7b237-110">These binaries are needed on Windows in order to get everything setup correctly (this is explained in detail in the [Apache wiki here](https://cwiki.apache.org/confluence/display/HADOOP2/WindowsProblems)).</span></span>
4. <span data-ttu-id="7b237-111">Konfigurieren Sie Ihre Hadoop-Installation, indem Sie die folgenden Änderungen an Ihrer `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd`-Datei vornehmen:</span><span class="sxs-lookup"><span data-stu-id="7b237-111">Configure your Hadoop installation by making the following changes to your `%HADOOP_HOME%\etc\hadoop\hadoop-env.cmd` file:</span></span>
    1. <span data-ttu-id="7b237-112">Legen Sie die `JAVA_HOME`-Eigenschaft mithilfe des DOS-Pfads fest (da Hadoop keine Leerzeichen in `JAVA_HOME` akzeptiert).</span><span class="sxs-lookup"><span data-stu-id="7b237-112">Set the `JAVA_HOME` property using the DOS path (since Hadoop doesn't like spaces in `JAVA_HOME`).</span></span> <span data-ttu-id="7b237-113">Dies sollte in etwa wie folgt aussehen: `C:\Progra~1\Java\jdk1.8.0_241` (Verweist auf die jeweilige auf Ihrem lokalen Computer installierte Version von Java).</span><span class="sxs-lookup"><span data-stu-id="7b237-113">This should look something like this: `C:\Progra~1\Java\jdk1.8.0_241` (Pointing to whatever version of Java you have installed on your local machine).</span></span>
    2. <span data-ttu-id="7b237-114">Fügen Sie `%HADOOP_HOME%\share\hadoop\tools\lib\*` an `HADOOP_CLASSPATH` an.</span><span class="sxs-lookup"><span data-stu-id="7b237-114">Append `%HADOOP_HOME%\share\hadoop\tools\lib\*` to `HADOOP_CLASSPATH`.</span></span>
    <span data-ttu-id="7b237-115">Ihre endgültige `hadoop-env.cmd`-Datei sollte in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7b237-115">Your final `hadoop-env.cmd` file should look something like this:</span></span>

    ![Finale Datei „hadoop-env.cmd“](./media/connect-external-sources/hadoop-env.png)

## <a name="configure-your-storage-account-in-hadoop"></a><span data-ttu-id="7b237-117">Konfigurieren Ihres Speicherkontos in Hadoop</span><span class="sxs-lookup"><span data-stu-id="7b237-117">Configure your storage account in Hadoop</span></span>

1. <span data-ttu-id="7b237-118">Öffnen Sie das ADLS Gen2- oder WASB-Speicherkonto, mit dem Sie eine Verbindung über das [Azure-Portal](https://portal.azure.com) herstellen möchten, öffnen Sie das Panel **Zugriffsschlüssel** auf dem Blatt **Einstellungen**, und kopieren Sie den Wert von **Key** (Schlüssel) unter key1.</span><span class="sxs-lookup"><span data-stu-id="7b237-118">Open the ADLS Gen 2 or WASB storage account you want to connect to through the [Azure portal](https://portal.azure.com) and open the **Access keys** panel under the **Settings** blade and copy the value of **Key** from under key1.</span></span>
2. <span data-ttu-id="7b237-119">Zum Konfigurieren des Zugriffs auf Ihr ADLS Gen2-Konto für Hadoop müssen Sie die unter `%HADOOP_HOME%\etc\hadoop\` gespeicherte Datei „`core-site.xml`“ bearbeiten, die eine clusterweite Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="7b237-119">Now in order to configure Hadoop to access your ADLS Gen2 account you would have to edit your `core-site.xml` (located in `%HADOOP_HOME%\etc\hadoop\` ) file which contains cluster-wide configuration.</span></span> <span data-ttu-id="7b237-120">Fügen Sie die folgenden Eigenschaften innerhalb der `<configuration>`-Tags in dieser Datei ein:</span><span class="sxs-lookup"><span data-stu-id="7b237-120">Add the following properties inside the `<configuration>` tags in this file:</span></span>

    ```xml
    <configuration>
      <property>
        <name>fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>SharedKey</value>
        <description></description>
      </property>
      <property>
        <name>fs.azure.account.key.YOUR_ACCOUNT_NAME.dfs.core.windows.net</name>
        <value>YOUR ACCESS KEY (copied from Step 1)</value>
        <description>The secret password. Never share these.</description>
      </property>
    </configuration>
    ```

    <span data-ttu-id="7b237-121">Wenn Sie versuchen, eine Verbindung mit einem WASB-Konto herzustellen, ersetzen Sie `dfs` in den Eigenschaftennamen durch `blob`.</span><span class="sxs-lookup"><span data-stu-id="7b237-121">If you are trying to connect to a WASB account, replace `dfs` with `blob` in the property names.</span></span> <span data-ttu-id="7b237-122">Beispiel: `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span><span class="sxs-lookup"><span data-stu-id="7b237-122">For example, `fs.azure.account.auth.type.YOUR_ACCOUNT_NAME.blob.core.windows.net`.</span></span>
3. <span data-ttu-id="7b237-123">Sie können die Konnektivität Ihres Speicherkontos über Hadoop testen, indem Sie den folgenden Befehl in Ihrem `%HADOOP_HOME%`-Verzeichnis ausführen:</span><span class="sxs-lookup"><span data-stu-id="7b237-123">You can test the connectivity to your Storage Account from Hadoop by running the following command from your `%HADOOP_HOME%` directory:</span></span>

    ```bash
    bin\hdfs dfs -ls <URI to your account>
    ```

<span data-ttu-id="7b237-124">Dadurch sollte eine Liste aller Dateien/Ordner im Pfad angezeigt werden, der von Ihrem URI bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7b237-124">This should display a list of all files/folders in the path provided by your URI.</span></span>

> [!NOTE]
> <span data-ttu-id="7b237-125">Das Format zum Ableiten des URI für Ihr Speicherkonto lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7b237-125">The format to derive the URI to your Storage account is as follows:</span></span>
>
> ```
> For ADLS: abfs[s]://<file_system>@<account_name>.dfs.core.windows.net/<path>/<file_name>
> For WASB: wasb[s]://<file_system>@<account_name>.blob.core.windows.net/<path>/<file_name>
> ```

## <a name="connect-to-your-storage-account"></a><span data-ttu-id="7b237-126">Herstellen einer Verbindung mit Ihrem Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="7b237-126">Connect to your storage account</span></span>

1. <span data-ttu-id="7b237-127">Wenn der obige Befehl funktioniert hat, können Sie nun über Spark auf das Speicherkonto zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7b237-127">If the above command worked, you can now move on to accessing this storage account through Spark.</span></span> <span data-ttu-id="7b237-128">Führen Sie zuerst den Befehl `hadoop classpath` über die Befehlszeile in `%HADOOP_HOME%` aus, und kopieren Sie die Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7b237-128">First run the command `hadoop classpath` from the commandline inside `%HADOOP_HOME%` and copy the output.</span></span>
2. <span data-ttu-id="7b237-129">Legen Sie die Ausgabe des in Schritt 1 ausgeführten Befehls auf den Wert der Umgebungsvariable `SPARK_DIST_CLASSPATH` fest.</span><span class="sxs-lookup"><span data-stu-id="7b237-129">Set the output of the command run in Step 1 to the value of environment variable `SPARK_DIST_CLASSPATH`.</span></span>
3. <span data-ttu-id="7b237-130">Sie sollten nun dazu in der Lage sein, wie im folgenden Beispiel gezeigt mithilfe des abfs-URIs über Spark .NET auf Ihr ADLS- oder WASB-Speicherkonto zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7b237-130">Now you should be able to access your ADLS or WASB storage account through Spark .NET using the abfs URI as shown in the simple example below.</span></span> <span data-ttu-id="7b237-131">(In diesem Beispiel wird die Standardbeispieldatei [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) verwendet, die in jeder Installation von Apache Spark enthalten ist.)</span><span class="sxs-lookup"><span data-stu-id="7b237-131">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.):</span></span>

    ```csharp
    SparkSession spark = SparkSession
       .Builder()
       .AppName("Connect to Azure Storage locally")
       .GetOrCreate();
    DataFrame df = spark.Read().Json("wasbs://file_system@account_name.blob.core.windows.net/path/people.json");
    //DataFrame df = spark.Read().Json("abfss://file_system@account_name.dfs.core.windows.net/path/file.json");
    df.Show();
    ```

    <span data-ttu-id="7b237-132">Das Ergebnis wird wie im folgenden DataFrame (`df`) angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7b237-132">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

    ```text
    +----+-------+
    | age|   name|
    +----+-------+
    |null|Michael|
    |  30|   Andy|
    |  19| Justin|
    +----+-------+
    ```
