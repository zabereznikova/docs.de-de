---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in Databricks bereitstellen.
ms.date: 01/23/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: a117d85ab911b380598c93417f6ff95661ab864c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868030"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-databricks"></a>Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks

In diesem Tutorial erfahren Sie, wie Sie Ihre App über Azure Databricks (eine auf Apache Spark basierende Analyseplattform, die Sie mit einem Mausklick einrichten können, die optimierte Workflows und einen interaktiven Arbeitsbereich bietet, der die Zusammenarbeit ermöglicht) in der Cloud bereitstellen können.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> - Erstellen eines Azure Databricks-Arbeitsbereichs
> - Veröffentlichen der .NET-App für Apache Spark.
> - Erstellen eines Spark-Auftrags und eines Spark-Clusters.
> - Ausführen Ihrer App auf dem Spark-Cluster.

## <a name="prerequisites"></a>Voraussetzungen

Führen Sie die folgenden Schritte aus, bevor Sie beginnen:

* Falls Sie noch kein Azure-Konto besitzen, erstellen Sie ein [kostenloses Konto](https://azure.microsoft.com/free/).
* Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.
* Vervollständigen Sie das Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).

## <a name="create-an-azure-databricks-workspace"></a>Erstellen eines Azure Databricks-Arbeitsbereichs

> [!Note]
> Dieses Tutorial kann nicht mit dem **kostenlosen Azure-Testabonnement** absolviert werden.
> Wenn Sie ein kostenloses Konto haben, rufen Sie Ihr Profil auf, und ändern Sie Ihr Abonnement auf **Nutzungsbasierte Bezahlung**. Weitere Informationen finden Sie unter [Kostenloses Azure-Konto](https://azure.microsoft.com/free/). [Entfernen Sie das dann Ausgabenlimit](https://docs.microsoft.com/azure/billing/billing-spending-limit#why-you-might-want-to-remove-the-spending-limit), und [fordern Sie die Erhöhung des Kontingents](https://docs.microsoft.com/azure/azure-supportability/resource-manager-core-quotas-request) für vCPUs in Ihrer Region an. Wenn Sie Ihren Azure Databricks-Arbeitsbereich erstellen, können Sie den Tarif **Testversion (Premium – 14 Tage kostenlosen DBUs)** auswählen, damit Sie über den Arbeitsbereich 14 Tage lang auf kostenlose Premium Azure Databricks-DBUs zugreifen können.

In diesem Abschnitt erstellen Sie einen Azure Databricks-Arbeitsbereich über das Azure-Portal.

1. Klicken Sie im Azure-Portal auf **Ressource erstellen** > **Analysen** > **Azure Databricks**.

   ![Erstellen einer Azure Databricks-Ressource im Azure-Portal](./media/databricks-deployment/create-databricks-resource.png)

2. Geben Sie unter **Azure Databricks-Dienst** die Werte für die Erstellung eines Databricks-Arbeitsbereichs an.

    |Eigenschaft  |Beschreibung  |
    |---------|---------|
    |**Arbeitsbereichsname**     | Geben Sie einen Namen für Ihren Databricks-Arbeitsbereich an.        |
    |**Abonnement**     | Wählen Sie in der Dropdownliste Ihr Azure-Abonnement aus.        |
    |**Ressourcengruppe**     | Geben Sie an, ob Sie eine neue Ressourcengruppe erstellen oder eine vorhandene Ressourcengruppe verwenden möchten. Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält. Weitere Informationen finden Sie in der [Übersicht über den Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview). |
    |**Position**     | Wählen Sie Ihre bevorzugte Region aus. Informationen zu allen verfügbaren Regionen finden Sie unter [Verfügbare Azure-Dienste nach Region](https://azure.microsoft.com/regions/services/).        |
    |**Tarif**     |  Wählen Sie zwischen **Standard**, **Premium** oder **Testversion**. Weitere Informationen zu diesen Tarifen, finden Sie unter [Azure Databricks – Preise](https://azure.microsoft.com/pricing/details/databricks/).       |
    |**Virtual Network**     |   Nein       |

3. Wählen Sie **Erstellen** aus. Die Erstellung des Arbeitsbereichs dauert einige Minuten. Während der Erstellung des Arbeitsbereichs können Sie den Bereitstellungsstatus in **Benachrichtigungen** anzeigen.

## <a name="install-azure-databricks-tools"></a>Installieren von Azure Databricks-Tools

Mit der **Databricks CLI** können Sie eine Verbindung mit Azure Databricks-Clustern herstellen und Dateien in diese von Ihrem lokalen Computer hochladen. Databricks-Cluster greifen über DBFS (Databricks File System) auf Dateien zu.

1. Die Databricks CLI erfordert Python 3.6 oder höher. Wenn Sie Python bereits installiert haben, können Sie diesen Schritt überspringen.

   **Für Windows:**

   [Laden Sie Python für Windows herunter](https://www.python.org/ftp/python/3.7.4/python-3.7.4.exe).

   **Für Linux:** Python ist in den meisten Linux-Distributionen bereits vorinstalliert. Führen Sie den folgenden Befehl aus, um festzustellen, welche Version Sie installiert haben:

   ```bash
   python3 --version
   ```

2. Verwenden Sie pip zum Installieren der Databricks CLI. Python 3.4 oder höher enthält pip standardmäßig. Verwenden Sie pip3 für Python 3. Führen Sie den folgenden Befehl aus:

   ```bash
   pip3 install databricks-cli
   ```

3. Nachdem Sie die Databricks CLI installiert haben, öffnen Sie eine neue Eingabeaufforderung, und führen Sie den Befehl `databricks` aus. Wenn Sie eine Fehlermeldung **'databricks' is not recognized as an internal or external command error** („Databricks“ wird nicht als interner oder externer Befehl erkannt: Fehler) erhalten, stellen Sie sicher, dass Sie eine neue Eingabeaufforderung geöffnet haben.

## <a name="set-up-azure-databricks"></a>Einrichten von Azure Databricks

Nachdem Sie die Databricks CLI installiert haben, müssen Sie Authentifizierungsdetails einrichten.

1. Führen Sie den Befehl `databricks configure --token` der Databricks CLI aus.

2. Nachdem Sie den Konfigurstionsbefehl ausgeführt haben, werden Sie zur Eingabe eines Hosts aufgefordert. Die Host-URL verwendet das folgende Format: **https://<\Speicherort >.azuredatabricks.net**. Wenn Sie beispielsweise während der Azure Databricks-Diensterstellung **eastus2** (USA, Osten 2) ausgewählt haben, wäre der Host **https://eastus2.azuredatabricks.net** .

3. Nachdem Sie den Host eingegeben haben, werden Sie zur Eingabe eines Tokens aufgefordert. Wählen Sie im Azure-Portal **Arbeitsbereich starten** aus, um den Azure Databricks-Arbeitsbereich zu starten.

   ![Starten des Azure Databricks-Arbeitsbereichs](./media/databricks-deployment/launch-databricks-workspace.png)

4. Wählen Sie auf der Startseite Ihres Arbeitsbereichs **Benutzereinstellungen** aus.

   ![Benutzereinstellungen in einem Azure Databricks-Arbeitsbereich](./media/databricks-deployment/databricks-user-settings.png)

5. Auf der Seite „Benutzereinstellungen“ können Sie ein neues Token generieren. Kopieren Sie das generierte Token, und fügen Sie es dann in die Eingabeaufforderung ein.

   ![Generieren eines neuen Zugriffstokens im Azure Databricks-Arbeitsbereich](./media/databricks-deployment/generate-token.png)

Sie sollten jetzt in der Lage sein, auf alle Azure Databricks-Cluster zuzugreifen, die Sie erstellen, und Dateien in DBFS hochzuladen.

## <a name="download-worker-dependencies"></a>Herunterladen von Workerabhängigkeiten

1. Microsoft.Spark.Worker unterstützt Apache Spark bei der Ausführung Ihrer App, z.B. für benutzerdefinierte Funktionen (User-Defined Functions, UDFs), die Sie ggf. geschrieben haben. Laden Sie [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz) herunter.

2. *install-worker.sh* ist ein Skript, mit dem Sie von .NET für Apache Spark abhängige Dateien in die Knoten Ihres Clusters kopieren können.

   Erstellen Sie eine neue Datei mit dem Namen **install-worker.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) auf GitHub ein.

3. *db-init.sh* ist ein Skript, mit dem Abhängigkeiten auf Ihrem Databricks Spark-Cluster installiert werden.

   Erstellen Sie eine neue Datei mit dem Namen **db-init.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von „db-init.sh“](https://github.com/dotnet/spark/blob/master/deployment/db-init.sh) auf GitHub ein.

   Legen Sie in der soeben erstellten Datei die `DOTNET_SPARK_RELEASE`-Variable auf `https://github.com/dotnet/spark/releases/download/v0.6.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz` fest. Lassen Sie den Rest der Datei *db-init.sh* unverändert.

> [!Note]
> Wenn Sie Windows verwenden, stellen Sie sicher, dass die Zeilenenden in Ihren *install-worker.sh*- und *db-init.sh*-Skripts den Unix-Stil (LF) verwenden. Sie können die Zeilenenden mit Text-Editoren wie Notepad++ oder Atom ändern.

## <a name="publish-your-app"></a>Veröffentlichen der App

Anschließend veröffentlichen Sie die *mySparkApp*, die im Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) erstellt wurde, um sicherzustellen, dass Ihr Spark-Cluster Zugriff auf alle Dateien besitzt, die er zum Ausführen Ihrer App benötigt.

1. Führen Sie zum Veröffentlichen der *mySparkApp* die folgenden Befehle aus:

   **Unter Windows:**

   ```console
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   **Unter Linux:**

   ```bash
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Führen Sie die folgenden Aufgaben aus, um die veröffentlichten App-Dateien zu komprimieren, damit Sie sie problemlos in ihren Databricks Spark-Cluster hochladen können.

   **Unter Windows:**

   Navigieren Sie zu „MySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64“. Klicken Sie dann mit der rechten Maustaste auf den Ordner **Veröffentlichen**, und wählen Sie **Senden an > Komprimierter Ordner (ZIP-Ordner)** aus. Nennen Sie den neuen Ordner **publish.zip**.

   **Führen Sie unter Linux den folgenden Befehl aus:**

   ```bash
   zip -r publish.zip .
   ```

## <a name="upload-files"></a>Hochladen von Dateien

In diesem Abschnitt laden Sie mehrere Dateien in DBFS hoch, sodass Ihr Cluster über alles verfügt, was er benötigt, um Ihre App in der Cloud auszuführen. Stellen Sie bei jedem Hochladen einer Datei in DBFS sicher, dass Sie sich in dem Verzeichnis befinden, in dem diese Datei auf Ihrem Computer gespeichert ist.

1. Führen Sie die folgenden Befehle aus, um die Dateien *db-init.sh*, *install-worker.sh* und *Microsoft.Spark.Worker* in DBFS hochzuladen:

   ```console
   databricks fs cp db-init.sh dbfs:/spark-dotnet/db-init.sh
   databricks fs cp install-worker.sh dbfs:/spark-dotnet/install-worker.sh
   databricks fs cp Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz dbfs:/spark-dotnet/   Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz
   ```

2. Führen Sie die folgenden Befehle aus, um die verbleibenden Dateien hochzuladen, die Ihr Cluster zum Ausführen der App benötigt: den gezippten Veröffentlichungsordner, *input.txt* und *microsoft-spark-2.4.x-0.3.0.jar*.

   ```console
   cd mySparkApp
   databricks fs cp input.txt dbfs:/input.txt

   cd mySparkApp\bin\Release\netcoreapp3.0\ubuntu.16.04-x64 directory
   databricks fs cp mySparkApp.zip dbfs:/spark-dotnet/publish.zip
   databricks fs cp microsoft-spark-2.4.x-0.6.0.jar dbfs:/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar
   ```

## <a name="create-a-job"></a>Erstellen eines Auftrags

Ihre App wird in Azure Databricks durch einen Auftrag ausgeführt, der **spark-submit** ausführt. Dies ist der Befehl, mit dem Sie .NET-Aufträge für Apache Spark ausführen.

1. Wählen Sie im Azure Databricks-Arbeitsbereich das Symbol **Aufträge** aus, und klicken Sie dann auf **+ Auftrag erstellen**.

   ![Erstellen eines Azure Databricks-Auftrags](./media/databricks-deployment/create-job.png)

2. Wählen Sie einen Titel für Ihren Auftrag aus, und wählen Sie dann **spark-submit konfigurieren** aus.

   ![Konfigurieren von spark-submit für den Databricks-Auftrag](./media/databricks-deployment/configure-spark-submit.png)

3. Fügen Sie die folgenden Parameter in die Auftragskonfiguration ein. Wählen Sie dann **Bestätigen** aus.

   ```
   ["--class","org.apache.spark.deploy.dotnet.DotnetRunner","/dbfs/spark-dotnet/microsoft-spark-2.4.x-0.6.0.jar","/dbfs/spark-dotnet/publish.zip","mySparkApp"]
   ```

## <a name="create-a-cluster"></a>Erstellen eines Clusters

1. Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Bearbeiten** aus, um den Cluster Ihres Auftrags zu konfigurieren.

2. Legen Sie den Cluster auf **Spark 2.4.1** fest. Wählen Sie dann **Erweiterte Optionen** > **Init-Skripts** aus. Legen Sie den init-Skriptpfad auf `dbfs:/spark-dotnet/db-init.sh` fest.

   ![Konfigurieren eines Spark-Clusters in Azure Databricks](./media/databricks-deployment/cluster-config.png)

3. Wählen Sie **Bestätigen** aus, um die Clustereinstellungen zu bestätigen.

## <a name="run-your-app"></a>Ausführen der App

1. Navigieren Sie zu Ihrem Auftrag, und wählen Sie **Jetzt ausführen** aus, um den Auftrag auf dem neu konfigurierten Spark-Cluster auszuführen.

2. Es dauert einige Minuten, bis der Cluster des Auftrags erstellt wurde. Nachdem der Auftrag erstellt wurde, wird er übermittelt, und Sie können die Ausgabe anzeigen.

3. Wählen Sie im Menü auf der linken Seite **Cluster** und dann den Namen aus, und führen Sie den Auftrag aus.

4. Wählen Sie **Treiberprotokolle** aus, um die Ausgabe des Auftrags anzuzeigen. Nachdem die Ausführung Ihrer App abgeschlossen wurde, wird die gleiche Wortzahltabelle aus der lokalen Ausführung von „Erste Schritte“ in der Standardausgabekonsole angezeigt.

   ![Tabelle der Azure Databricks-Auftragsausgabe](./media/databricks-deployment/table-output.png)

   Herzlichen Glückwunsch, Sie haben Ihre erste .NET-Anwendung für Apache Spark in der Cloud ausgeführt!

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

Wenn Sie den Databricks-Arbeitsbereich nicht mehr benötigen, können Sie die Azure Databricks-Ressource im Azure-Portal löschen. Sie können auch den Namen der Ressourcengruppe auswählen, um die Seite für die Ressourcengruppe zu öffnen, und dann **Ressourcengruppe löschen** auswählen.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Databricks bereitgestellt. Weitere Informationen zu Databricks finden Sie in der Dokumentation zu Azure Databricks.

> [!div class="nextstepaction"]
> [Dokumentation zu Azure Databricks](https://docs.microsoft.com/azure/azure-databricks/)
