---
title: Senden eines .NET für Apache Spark-Auftrags an Databricks
description: Erfahren Sie, wie Sie mit spark-submit und Set JAR einen .NET für Apache Spark-Auftrag an Databricks übermitteln.
ms.date: 12/05/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9cd3d40871d4600660957ec268f192ef3e045845
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838362"
---
# <a name="submit-a-net-for-apache-spark-job-to-databricks"></a>Übermitteln eines .NET für Apache Spark-Auftrags an Databricks

Es gibt zwei Möglichkeiten, einen .NET für Apache Spark-Auftrag für Databricks bereitzustellen: `spark-submit` und Set JAR. 

## <a name="deploy-using-spark-submit"></a>Bereitstellen mit spark-submit

Mit dem Befehl [spark-submit](https://spark.apache.org/docs/latest/submitting-applications.html) können Sie .NET für Apache Spark-Aufträge an Databricks übermitteln. `spark-submit` ermöglicht die Übermittlung nur an einen Cluster, der bedarfsgesteuert erstellt wird.

1. Wechseln Sie zu Ihrem Databricks-Arbeitsbereich, und erstellen Sie einen Auftrag. Wählen Sie einen Titel für Ihren Auftrag aus, und wählen Sie dann **spark-submit konfigurieren** aus. Fügen Sie die folgenden Parameter in die Auftragskonfiguration ein, und wählen Sie dann **Bestätigen** aus.

    ```
    ["--files","/dbfs/<path-to>/<app assembly/file to deploy to worker>","--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/<path-to>/microsoft-spark-<spark_majorversion.spark_minorversion.x>-<spark_dotnet_version>.jar","/dbfs/<path-to>/<app name>.zip","<app bin name>","app arg1","app arg2"]
    ```

    > [!NOTE]
    > Aktualisieren Sie den Inhalt des obigen Parameters basierend auf Ihren spezifischen Dateien und Ihrer Konfiguration. Verweisen Sie beispielsweise auf die Version der JAR-Datei „Microsoft.Spark“, die Sie in Databricks File System (DBFS) hochgeladen haben, und verwenden Sie den entsprechenden Namen Ihrer App und der ZIP-Datei der veröffentlichten App.

2. Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Bearbeiten** aus, um den Cluster Ihres Auftrags zu konfigurieren. Legen Sie die Databricks Runtime-Version basierend auf der Version von Apache Spark fest, die Sie in Ihrer Bereitstellung verwenden möchten. Wählen Sie dann **Advanced Options > Init Scripts** (Erweiterte Optionen > Initialisierungsskripts) aus, und legen Sie den Pfad des Initialisierungsskripts auf `dbfs:/spark-dotnet/db-init.sh` fest. Wählen Sie **Bestätigen** aus, um die Clustereinstellungen zu bestätigen.

3. Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Jetzt ausführen** aus, um den Auftrag auf dem neu konfigurierten Spark-Cluster auszuführen. Es dauert einige Minuten, bis der Cluster des Auftrags erstellt wird. Nach seiner Erstellung wird Ihr Auftrag übermittelt. Sie können die Ausgabe anzeigen, indem Sie im linken Menü Ihres Databricks-Arbeitsbereichs **Clusters** (Cluster) und dann **Driver Logs** (Treiberprotokolle) auswählen.

## <a name="deploy-using-set-jar"></a>Bereitstellen mithilfe von Set JAR

Alternativ können Sie in Ihrem Databricks-Arbeitsbereich [Set JAR](https://docs.microsoft.com/azure/databricks/jobs#--create-a-job) verwenden, um .NET für Apache Spark-Aufträge an Databricks zu übermitteln. *Set JAR* ermöglicht das Übermitteln eines Auftrags an einen vorhandenen aktiven Cluster.

### <a name="one-time-setup"></a>Einmalige Konfiguration

1. Wechseln Sie zu Ihrem Databricks-Cluster, und klicken Sie im Menü auf der linken Seite erst auf **Jobs** (Aufträge) und dann auf **Set JAR**.

2. Laden Sie die entsprechende Datei `microsoft-spark-<spark-version>-<spark-dotnet-version>.jar` hoch.

3. Ändern Sie die folgenden Parameter so, dass sie den richtigen Namen für die ausführbare Datei enthalten, die Sie anstelle von `<your-app-name>` veröffentlicht haben:

    ```
    Main Class: org.apache.spark.deploy.dotnet.DotnetRunner
    Arguments /dbfs/apps/<your-app-name>.zip <your-app-name>
    ```

4. Konfigurieren Sie den Cluster so, dass er auf einen bestehenden Cluster zeigt, für den Sie das Initialisierungsskript bereits festgelegt haben.

### <a name="publish-and-run-your-app"></a>Veröffentlichen und Ausführen der App

1. Vergewissern Sie sich, dass Sie Ihre App veröffentlicht haben und Ihr Anwendungscode nicht `SparkSession.Stop()` verwendet.

2. Verwenden Sie die [Databricks CLI](https://docs.microsoft.com/azure/databricks/dev-tools/databricks-cli), um Ihre Anwendung in Ihren Databricks-Cluster hochzuladen. Mit dem folgenden Befehl können Sie beispielsweise Ihre veröffentlichte Anwendung in Ihren Cluster hochladen:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <your-app-name>.zip dbfs:/apps/<your-app-name>.zip
    ```

3. Wenn es in Ihrer App benutzerdefinierte Funktionen gibt, müssen die App-Assemblys, wie z.B. DLLs, die benutzerdefinierte Funktionen und deren Abhängigkeiten enthalten, in das Arbeitsverzeichnis der einzelnen *Microsoft.Spark.Worker*-Elemente verschoben werden.

    Laden Sie Ihre Anwendungsassemblys in Ihren Databricks-Cluster hoch:

    ```console
    cd <path-to-your-app-publish-directory>
    databricks fs cp <assembly>.dll dbfs:/apps/dependencies
    ```

    Heben Sie die Auskommentierung auf, und ändern Sie den Abschnitt mit den App-Abhängigkeiten in [db-init.sh](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh), um auf den Pfad Ihrer App-Abhängigkeiten zu verweisen. Laden Sie dann die aktualisierte Datei *db-init.sh* in Ihren Cluster hoch:

    ```console
    cd <path-to-db-init-and-install-worker>
    databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
    ```

4. Navigieren Sie zu **Databricks cluster > Jobs > [Job-name] > Run Now** (Databricks-Cluster > Aufträge > [Name des Auftrags]), um Ihren Auftrag auszuführen.

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks](../tutorials/databricks-deployment.md)
* [Dokumentation zu Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
