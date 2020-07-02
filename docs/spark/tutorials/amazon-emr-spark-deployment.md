---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.
ms.date: 06/25/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6cf26044693c5d923d11e1bbc72232e7009fe73
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618258"
---
# <a name="deploy-a-net-for-apache-spark-application-to-amazon-emr-spark"></a>Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark

In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitstellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten von Microsoft.Spark.Worker
> * Veröffentlichen einer .NET für Apache Spark-Anwendung
> * Bereitstellen einer App in Amazon EMR Spark
> * Ausführen der App

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>Voraussetzungen

Führen Sie zunächst folgende Schritte aus:

* Laden Sie die [AWS CLI](https://aws.amazon.com/cli/) herunter.
* Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter. Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.

## <a name="prepare-worker-dependencies"></a>Vorbereiten von Workerabhängigkeiten

**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet. Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird. **Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.

1. Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.

   Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.

2. Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann.

## <a name="prepare-your-net-for-apache-spark-app"></a>Vorbereiten der .NET für Apache Spark-App

1. Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.

2. Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.

   Führen Sie unter Linux den folgenden Befehl aus:

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.

   Führen Sie unter Linux den folgenden `zip`-Befehl aus:

   ```bash
   zip -r <your app>.zip .
   ```

4. Laden Sie die folgenden Dateien auf ein verteiltes Dateisystem (beispielsweise S3) hoch, auf das Ihr Cluster zugreifen kann:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.
   * `<your app>.zip`
   * Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit benutzerdefinierten Funktionen oder Bibliotheken, von denen Ihre App abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.

## <a name="deploy-to-amazon-emr-spark"></a>Bereitstellen einer App in Amazon EMR Spark

[Amazon EMR](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-what-is-emr.html) ist eine verwaltete Clusterplattform, die die Ausführung von Big-Data-Frameworks in AWS vereinfacht.

> [!NOTE]
> Amazon EMR Spark basiert auf Linux. Wenn Sie Ihre App in Amazon EMR Spark bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.

### <a name="deploy-microsoftsparkworker"></a>Bereitstellen von Microsoft.Spark.Worker

Dieser Schritt ist nur bei der Erstellung des Clusters erforderlich.

Führen Sie mithilfe der [Bootstrapaktionen](https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html)`install-worker.sh` bei der Erstellung des Clusters aus.

Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:

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

Sie können Ihre App in Amazon EMR Spark entweder mit „spark-submit“ oder mit Amazon EMR-Schritten ausführen.

### <a name="use-spark-submit"></a>Verwenden von „spark-submit“

Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Amazon EMR Spark übermitteln.

1. Stellen Sie mit `ssh` eine Verbindung mit einem Knoten Ihres Clusters her.

2. Führen Sie aus `spark-submit`.

   ```bash
   spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --files <comma-separated list of assemblies that contain UDF definitions, if any> \
   s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar \
   s3://mybucket/<some dir>/<your app>.zip <your app> <app args>
   ```

### <a name="use-amazon-emr-steps"></a>Verwenden von Amazon EMR-Schritten

Mithilfe von [Amazon EMR-Schritten](https://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-spark-submit-step.html) können Sie Aufträge an das Spark-Framework übermitteln, das auf dem EMR-Cluster installiert ist.

Führen Sie unter Linux den folgenden Befehl mit der AWS CLI aus:

```bash
aws emr add-steps \
--cluster-id j-xxxxxxxxxxxxx \
--steps Type=spark,Name="Spark Program",Args=[--master,yarn,--files,s3://mybucket/<some dir>/<udf assembly>,--class,org.apache.spark.deploy.dotnet.DotnetRunner,s3://mybucket/<some dir>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar,s3://mybucket/<some dir>/<your app>.zip,<your app>,<app arg 1>,<app arg 2>,...,<app arg n>],ActionOnFailure=CONTINUE
```

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Amazon EMR Spark bereitgestellt. Beispielprojekte für .NET für Apache Spark finden Sie auf GitHub.

> [!div class="nextstepaction"]
> [Beispiele für .NET für Apache Spark](https://github.com/dotnet/spark/tree/master/examples)
