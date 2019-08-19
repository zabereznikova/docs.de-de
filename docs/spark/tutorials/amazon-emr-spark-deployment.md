---
title: Bereitstellen einer .net for Apache Spark-Anwendung in Amazon EMR Spark
description: Erfahren Sie, wie Sie eine .net for Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 5414bc20de3bb90a5d2144bd006d1b859e184a39
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "69576927"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Bereitstellen einer .net for Apache Spark-Anwendung in Amazon EMR Spark

In diesem Tutorial erfahren Sie, wie Sie eine .NET-Anwendung für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Vorbereiten von Microsoft. Spark. Worker
> * Veröffentlichen Ihrer Spark .net-App
> * Bereitstellen Ihrer APP in Amazon EMR Spark
> * Ausführen der App

## <a name="prerequisites"></a>Vorraussetzungen

Bevor Sie beginnen, gehen Sie folgendermaßen vor:

* Laden Sie die [AWS-CLI](https://aws.amazon.com/cli/)herunter.
* Laden Sie [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter. Hierbei handelt es sich um ein Hilfsskript, das Sie später verwenden, um .net für Apache Spark abhängige Dateien in die workerknoten Ihres Spark-Clusters zu kopieren.

## <a name="prepare-worker-dependencies"></a>Vorbereiten von workerabhängigkeiten

**Microsoft. Spark. Worker** ist eine Back-End-Komponente, die sich auf den einzelnen workerknoten Ihres Spark-Clusters befindet. Wenn Sie eine C# benutzerdefinierte Funktion (User-Defined Function, UDF) ausführen möchten, muss Spark wissen, wie die .NET CLR gestartet werden muss, um die UDF auszuführen. **Microsoft. Spark. Worker** stellt eine Auflistung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.

1. Wählen Sie eine Version von [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) Linux netcoreapp aus, die auf Ihrem Cluster bereitgestellt werden soll.

   Wenn Sie beispielsweise verwenden `.NET for Apache Spark v0.1.0` `netcoreapp2.1`möchten, laden Sie [Microsoft. Spark. Worker. netcoreapp 2.1. Linux-x64-0.1.0. tar. gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz)herunter.

2. Hochladen `Microsoft.Spark.Worker.<release>.tar.gz` und [install-Worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) in ein verteiltes Dateisystem (z. b. S3), auf das Ihr Cluster Zugriff hat.

## <a name="prepare-your-net-for-apache-spark-app"></a>Vorbereiten von .net für Apache Spark-App

1. Befolgen Sie das Tutorial " [Get Started](get-started.md) ", um Ihre APP zu erstellen.

2. Veröffentlichen Sie Ihre Spark .net-App als eigenständig.

   Führen Sie unter Linux den folgenden Befehl aus.

   ```bash
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Erzeugt `<your app>.zip` für die veröffentlichten Dateien.

   Führen Sie den folgenden Befehl unter Linux `zip`mit aus.

   ```bash
   zip -r <your app>.zip .
   ```

4. Laden Sie die folgenden Elemente in ein verteiltes Dateisystem (z. b. S3) hoch, auf das Ihr Cluster Zugriff hat:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist als Teil des [Microsoft. Spark](https://www.nuget.org/packages/Microsoft.Spark/) -nuget-Pakets enthalten und wird im Buildausgabeverzeichnis Ihrer APP zusammengestellt.
   * `<your app>.zip`
   * Dateien (z. b. Abhängigkeits Dateien oder gemeinsame Daten, die für jeden Worker zugänglich sind) oder Assemblys (z. b. DLLs, die die benutzerdefinierten Funktionen oder Bibliotheken enthalten, von denen Ihre APP abhängt), die im Arbeitsverzeichnis jedes Executor abgelegt werden sollen

## <a name="deploy-to-amazon-emr-spark"></a>Bereitstellen in Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Cluster Plattform, die die Ausführung Big Data Frameworks auf AWS vereinfacht.

> [!NOTE] 
> Amazon EMR Spark ist Linux-basiert. Wenn Sie Ihre APP in Amazon EMR Spark bereitstellen möchten, müssen Sie daher sicherstellen, dass Ihre APP .NET Standard kompatibel ist und Sie den [.net Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer APP verwenden.

### <a name="deploy-microsoftsparkworker"></a>Bereitstellen von Microsoft. Spark. Worker

Dieser Schritt ist nur bei der Cluster Erstellung erforderlich.

Wird `install-worker.sh` während der Cluster Erstellung mithilfe von [Bootstrap-Aktionen](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)ausgeführt.

Führen Sie den folgenden Befehl unter Linux mithilfe der AWS CLI aus.

```bash
aws emr create-cluster \
--name "Test cluster" \
--release-label emr-5.23.0 \
--use-default-roles \
--ec2-attributes KeyName=myKey \
--applications Name=Spark \
--instance-count 3 \
--instance-type m1.medium \
--bootstrap-actions Path=s3://mybucket/<some dir>/install-worker.sh,Name="Install Microsoft.Spark.Worker",Args=["aws","s3://mybucket/<some dir>/Microsoft.Spark.Worker.<release>.tar.gz","/usr/local/bin"]
```

## <a name="run-your-app"></a>Ausführen der App

Es gibt zwei Möglichkeiten, Ihre APP in Amazon EMR Spark auszuführen: Spark-Submit und Amazon EMR Steps.

### <a name="use-spark-submit"></a>Verwenden von Spark-Submit

Mit dem Befehl " [Spark-Submit](https://spark.apache.org/docs/latest/submitting-applications.html) " können Sie .net für Apache Spark Aufträge an Amazon EMR Spark übermitteln.

1. `ssh`in einen der Knoten im Cluster.

2. Führen Sie aus `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Verwenden von Amazon EMR-Schritten

Mithilfe von [Amazon EMR Steps](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) können Aufträge an das Spark-Framework übermittelt werden, das auf dem EMR-Cluster installiert ist.

Führen Sie den folgenden Befehl unter Linux mithilfe der AWS CLI aus.

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Ihre .net for Apache Spark-Anwendung in Amazon EMR Spark bereitgestellt. Weitere Informationen zu Apache Spark Beispielprojekten für .net finden Sie unter GitHub.

> [!div class="nextstepaction"]
> [.Net für Apache Spark-Beispiele](https://github.com/dotnet/spark/tree/master/examples)
