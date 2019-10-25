---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.
ms.date: 05/17/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 55fa9b42e04a540deb245887d601e6cce0e6e623
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583520"
---
# <a name="deploy-a-net-for-apache-spark-application-to-databricks"></a>Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks

In diesem Tutorial erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten von Microsoft.Spark.Worker
> * Veröffentlichen einer .NET für Apache Spark-Anwendung
> * Bereitstellen der App in Databricks
> * Ausführen der App

## <a name="prerequisites"></a>Erforderliche Komponenten

Führen Sie zunächst folgende Schritte aus:

* Laden Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html) herunter.
* Laden Sie [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf Ihren lokalen Computer herunter. Hierbei handelt es sich um ein Hilfsskript, mit dem Sie später von .NET für Apache Spark abhängige Dateien auf die Workerknoten Ihres Spark-Clusters kopieren.

## <a name="prepare-worker-dependencies"></a>Vorbereiten von Workerabhängigkeiten

**Microsoft.Spark.Worker** ist eine Back-End-Komponente, die sich auf den einzelnen Workerknoten Ihres Spark-Clusters befindet. Wenn Sie eine benutzerdefinierte C#-Funktion ausführen möchten, muss Spark dafür wissen, wie die .NET CLR gestartet wird. **Microsoft.Spark.Worker** stellt eine Sammlung von Klassen für Spark bereit, die diese Funktionalität ermöglichen.

1. Wählen Sie für [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) das Linux-netcoreapp-Release aus, das auf Ihrem Cluster bereitgestellt werden soll.

   Wenn z. B. `netcoreapp2.1` für `.NET for Apache Spark v0.1.0` verwendet werden soll, laden Sie [Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz](https://github.com/dotnet/spark/releases/download/v0.1.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.1.0.tar.gz) herunter.

2. Laden Sie `Microsoft.Spark.Worker.<release>.tar.gz` und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh) auf ein verteiltes Dateisystem (beispielsweise dBFS) hoch, auf das Ihr Cluster zugreifen kann.

## <a name="prepare-your-net-for-apache-spark-app"></a>Vorbereiten der .NET für Apache Spark-App

1. Führen Sie die Schritte im Tutorial [Erste Schritte](get-started.md) aus, um Ihre App zu erstellen.

2. Veröffentlichen Sie Ihre .NET für Apache Spark-App als eigenständige Anwendung.

   Sie können unter Linux den folgenden Befehl ausführen:

   ```dotnetcli
   dotnet publish -c Release -f netcoreapp2.1 -r ubuntu.16.04-x64
   ```

3. Erstellen Sie für die veröffentlichten Dateien die Datei `<your app>.zip`.

   Sie können unter Linux den folgenden `zip`-Befehl ausführen:

   ```bash
   zip -r <your app>.zip .
   ```

4. Laden Sie Folgendes auf ein verteiltes Dateisystem (beispielsweise dBFS) hoch, auf das Ihr Cluster zugreifen kann:

   * `microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar`: Diese JAR-Datei ist im NuGet-Paket [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) enthalten und befindet sich im Buildausgabeverzeichnis Ihrer App.
   * `<your app>.zip`
   * Dateien (z. B. Abhängigkeitsdateien oder Daten, die für jeden Worker zugänglich sind) oder Assemblys (beispielsweise DLLs mit benutzerdefinierten Funktionen oder Bibliotheken, von denen Ihre App abhängig ist), die im Arbeitsverzeichnis jedes Executors abgelegt werden sollen.

## <a name="deploy-to-databricks"></a>Bereitstellen in Databricks

[Databricks](https://databricks.com) ist eine Plattform, die cloudbasierte Big Data-Verarbeitung mithilfe von Apache Spark ermöglicht.

> [!NOTE]
> [Azure Databricks](https://azure.microsoft.com/services/databricks/) und [AWS Databricks](https://databricks.com/aws) sind Linux-basiert. Wenn Sie Ihre App in Databricks bereitstellen möchten, müssen Sie darauf achten, dass diese mit .NET Standard kompatibel ist und dass Sie den [.NET Core-Compiler](https://dotnet.microsoft.com/download) zum Kompilieren Ihrer App verwenden.

Mit Databricks können Sie .NET für Apache Spark-Apps an einen vorhandenen aktiven Cluster übermitteln oder jedes Mal, wenn Sie einen Auftrag starten, einen neuen Cluster erstellen. Hierfür muss **Microsoft.Spark.Worker** installiert sein, bevor Sie eine .NET für Apache Spark-App übermitteln.

### <a name="deploy-microsoftsparkworker"></a>Bereitstellen von Microsoft.Spark.Worker

Der folgende Schritt ist nur einmal für einen Cluster erforderlich.

1. Laden Sie [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) und [install-worker.sh](https://github.com/dotnet/spark/blob/master/deployment/install-worker.sh
) auf Ihren lokalen Computer herunter.

2. Ändern Sie **db-init.sh**, um auf das **Microsoft.Spark.Worker**-Release zu verweisen, das Sie herunterladen und auf Ihrem Cluster installieren möchten.

3. Installieren Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html).

4. [Richten Sie Authentifizierungsdetails](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html#set-up-authentication) für die Databricks-Befehlszeilenschnittstelle ein.

5. Laden Sie die Dateien mithilfe des folgenden Befehls in Ihren Databricks-Cluster hoch:

   ```bash
   cd <path-to-db-init-and-install-worker>
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   ```

6. Greifen Sie auf Ihren Databricks-Arbeitsbereich zu. Klicken Sie im Menü links auf **Cluster** und anschließend auf **Cluster erstellen**.

7. Nachdem Sie den Cluster entsprechend konfiguriert haben, legen Sie das **Init-Skript** fest, und erstellen Sie den Cluster.

   ![Screenshot mit Skriptaktion](./media/databricks-deployment/deployment-databricks-init-script.png)

## <a name="run-your-app"></a>Ausführen der App

Sie können `set JAR` oder `spark-submit` verwenden, um Ihren Auftrag an Databricks zu übermitteln.

### <a name="use-set-jar"></a>Verwenden von Set JAR

[Set JAR](https://docs.databricks.com/user-guide/jobs.html#create-a-job) ermöglicht das Übermitteln eines Auftrags an einen vorhandenen aktiven Cluster.

#### <a name="one-time-setup"></a>Einmalige Konfiguration

1. Wechseln Sie zu Ihrem Databricks-Cluster, und klicken Sie im Menü auf der linken Seite auf **Aufträge**. Klicken Sie dann auf **Set JAR** (JAR festlegen).

2. Laden Sie die entsprechende Datei `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` hoch.

3. Legen Sie die entsprechenden Parameter fest.

   | Parameter   | Wert                                                |
   |-------------|------------------------------------------------------|
   | Hauptklasse  | org.apache.spark.deploy.dotnet.DotnetRunner          |
   | Argumente   | /dbfs/apps/\<Name-Ihrer-App>.zip \<Hauptklasse-Ihrer-App> |

4. Konfigurieren Sie den **Cluster**, um auf den vorhandenen Cluster zu verweisen, für den Sie im vorherigen Abschnitt das **Init-Skript** erstellt haben.

#### <a name="publish-and-run-your-app"></a>Veröffentlichen und Ausführen der App

1. Verwenden Sie die [Databricks-Befehlszeilenschnittstelle](https://docs.databricks.com/user-guide/dev-tools/databricks-cli.html), um Ihre Anwendung in Ihren Databricks-Cluster hochzuladen.

    ```bash
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

2. Dieser Schritt ist nur erforderlich, wenn Ihre App-Assemblys (z. B. DLLs, die benutzerdefinierte Funktionen zusammen mit ihren Abhängigkeiten enthalten) im Arbeitsverzeichnis jeder **Microsoft.Spark.Worker**-Komponente abgelegt werden müssen.

   * Laden Sie Ihre Anwendungsassemblys in Ihren Databricks-Cluster hoch.

      ```bash
      cd <path-to-your-app-publish-directory>
      databricks fs cp <assembly>.dll dbfs:/apps/dependencies
      ```

   * Heben Sie die Auskommentierung auf, und ändern Sie den Abschnitt „App-Abhängigkeiten“ zu [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), um auf den Pfad Ihrer App-Abhängigkeiten zu verweisen und in Ihren Databricks-Cluster hochzuladen.

      ```bash
      cd <path-to-db-init-and-install-worker>
      databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
      ```

   * Starten Sie Ihren Cluster neu.

3. Navigieren Sie zu Ihrem Databricks-Cluster in Ihrem Databricks-Arbeitsbereich. Klicken Sie unter **Aufträge** auf Ihren Auftrag und anschließend auf **Jetzt ausführen**, um Ihren Auftrag auszuführen.

### <a name="use-spark-submit"></a>Verwenden von „spark-submit“

Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie einen Auftrag an einen neuen Cluster übermitteln.

1. [Erstellen Sie einen Auftrag](https://docs.databricks.com/user-guide/jobs.html), und klicken Sie auf **Configure spark-submit** (spark-submit konfigurieren).

2. Konfigurieren Sie `spark-submit` mit den folgenden Parametern:

    ```bash
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

3. Navigieren Sie zu Ihrem Databricks-Cluster in Ihrem Databricks-Arbeitsbereich. Klicken Sie unter **Aufträge** auf Ihren Auftrag und anschließend auf **Jetzt ausführen**, um Ihren Auftrag auszuführen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Databricks bereitgestellt. Weitere Informationen zu Databricks finden Sie in der Dokumentation zu Azure Databricks.

> [!div class="nextstepaction"]
> [Dokumentation zu Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
