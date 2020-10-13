---
title: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung in HDInsight bereitstellen.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8ef1429d265c87347bb8771dc01b319fcb9e84d0
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955369"
---
# <a name="tutorial-deploy-a-net-for-apache-spark-application-to-azure-hdinsight"></a>Tutorial: Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight

In diesem Tutorial erfahren Sie, wie Sie Ihre .NET-App für Apache Spark über einen Azure HDInsight-Cluster in der Cloud bereitstellen. HDInsight erleichtert das Erstellen und Konfigurieren eines Spark-Clusters in Azure, da Spark-Cluster in HDInsight mit Azure Storage und Azure Data Lake Storage kompatibel sind.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Zugreifen über Azure Storage-Explorer auf Ihre Speicherkonten.
> * Erstellen eines Azure HDInsight-Clusters.
> * Veröffentlichen der .NET-App für Apache Spark.
> * Erstellen und Ausführen einer HDInsight-Skriptaktion.
> * Ausführen einer .NET-App für Apache Spark in einem HDInsight-Cluster.

## <a name="prerequisites"></a>Voraussetzungen

Führen Sie die folgenden Schritte aus, bevor Sie beginnen:

* Wenn Sie kein Azure-Abonnement besitzen, können Sie ein [kostenloses Konto](https://azure.microsoft.com/free/dotnet/) erstellen.
* Melden Sie sich beim [Azure-Portal](https://portal.azure.com/) an.
* Installieren Sie Azure Storage-Explorer auf Ihrem [Windows](https://go.microsoft.com/fwlink/?LinkId=708343&clcid=0x409)-, [Linux](https://go.microsoft.com/fwlink/?LinkId=722418&clcid=0x409)- oder [MacOS](https://go.microsoft.com/fwlink/?LinkId=708342&clcid=0x409)-Computer.
* Vervollständigen Sie das Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro).

## <a name="access-your-storage-accounts"></a>Zugreifen auf Ihre Speicherkonten

1. Öffnen Sie den Azure Storage-Explorer.

2. Wählen Sie im linken Menü **Konto hinzufügen** aus, und melden Sie sich bei Ihrem Azure-Konto an.

    ![Anmelden bei einem Azure-Konto über Storage-Explorer](./media/hdinsight-deployment/signin-azure-storage-explorer.png)

   Nachdem Sie sich angemeldet haben, sollten alle Speicherkonten in Ihrem Besitz und alle Ressourcen angezeigt werden, die Sie in Ihre Speicherkonten hochgeladen haben.

## <a name="create-an-hdinsight-cluster"></a>Erstellen eines HDInsight-Clusters

> [!IMPORTANT]
> Die Abrechnung für die HDInsight-Cluster erfolgt anteilsmäßig auf Minutenbasis und ist unabhängig von ihrer Verwendung. Daher sollten Sie Ihren Cluster nach der Verwendung unbedingt wieder löschen. Weitere Informationen finden Sie im Abschnitt [Bereinigen von Ressourcen](#clean-up-resources) in diesem Tutorial.

1. Besuchen Sie das [Azure-Portal](https://portal.azure.com).

2. Wählen Sie **+ Ressource erstellen**. Wählen Sie dann **HDInsight** aus der Kategorie **Analyse** aus.

    ![Erstellen einer HDInsight-Ressource über das Azure-Portal](./media/hdinsight-deployment/create-hdinsight-resource.png)

3. Geben Sie unter **Grundlagen** die folgenden Werte an:

    |Eigenschaft  |Beschreibung  |
    |---------|---------|
    |Abonnement  | Wählen Sie in der Dropdownliste eines Ihrer aktiven Azure-Abonnements aus. |
    |Resource group | Geben Sie an, ob Sie eine neue Ressourcengruppe erstellen oder eine vorhandene Ressourcengruppe verwenden möchten. Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung enthält. |
    |Clustername | Geben Sie einen Namen für den HDInsight Spark-Cluster an.|
    |Speicherort   | Wählen Sie einen Speicherort für die Ressourcengruppe aus. Die Vorlage verwendet diesen Standort sowohl für die Erstellung des Clusters als auch für den Standardclusterspeicher. |
    |Clustertyp| Wählen Sie als Clustertyp **Spark** aus.|
    |Clusterversion|Nach der Auswahl des Clustertyps wird dieses Feld automatisch mit der Standardversion aufgefüllt. Wählen Sie eine Version 2.3 oder 2.4 von Spark aus.|
    |Benutzername für Clusteranmeldung| Geben Sie den Anmeldebenutzernamen für den Cluster ein.  Der Standardname lautet *admin*. |
    |Kennwort für Clusteranmeldung| Geben Sie das Kennwort für die Anmeldung ein. |
    |SSH-Benutzername (Secure Shell)| Geben Sie den SSH-Benutzernamen ein. Standardmäßig gilt für dieses Konto dasselbe Kennwort wie für das Konto mit dem *Benutzernamen für die Clusteranmeldung*. |

4. Klicken Sie auf **Weiter: Speicher >>** , um zur Seite **Speicher** zu wechseln. Geben Sie unter **Speicher** die folgenden Werte an:

    |Eigenschaft  |Beschreibung  |
    |---------|---------|
    |Primärer Speichertyp|Übernehmen Sie den Standardwert **Azure Storage**.|
    |Auswahlmethode|Übernehmen Sie den Standardwert **Aus Liste auswählen**.|
    |Primäres Speicherkonto|Wählen Sie Ihr Abonnement und eines Ihrer aktiven Speicherkonten in diesem Abonnement aus.|
    |Container|Dieser Container ist der spezifische Blobcontainer in Ihrem Speicherkonto, in dem Ihr Cluster nach Dateien sucht, um Ihre App in der Cloud auszuführen. Sie können ihm einen beliebigen verfügbaren Namen zuweisen.|

5. Wählen Sie unter **Überprüfen + erstellen** die Option **Erstellen** aus. Das Erstellen des Clusters dauert ca. 20 Minuten. Der Cluster muss erstellt werden, bevor Sie mit dem nächsten Schritt fortfahren können.

## <a name="publish-your-app"></a>Veröffentlichen der App

Anschließend veröffentlichen Sie die *mySparkApp*, die im Tutorial [.NET für Apache Spark: Erste Schritte in 10 Minuten](https://dotnet.microsoft.com/learn/data/spark-tutorial/intro) erstellt wurde, die Ihrem Spark-Cluster Zugriff auf alle Dateien ermöglicht, die er zum Ausführen Ihrer App benötigt.

1. Führen Sie zum Veröffentlichen der *mySparkApp* die folgenden Befehle aus:

   **Unter Windows:**

   ```dotnetcli
   cd mySparkApp
   dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

   **Unter Linux:**

   ```bash
   cd mySparkApp
   foo@bar:~/path/to/app$ dotnet publish -c Release -f netcoreapp3.0 -r ubuntu.16.04-x64
   ```

2. Führen Sie die folgenden Aufgaben aus, um die veröffentlichten App-Dateien zu komprimieren, damit Sie sie problemlos in ihren HDInsight-Cluster hochladen können.

   **Unter Windows:**

   Navigieren Sie zu *MySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64*. Klicken Sie dann mit der rechten Maustaste auf den Ordner **Veröffentlichen**, und wählen Sie **Senden an > Komprimierter Ordner (ZIP-Ordner)** aus. Nennen Sie den neuen Ordner **publish.zip**.

   **Führen Sie unter Linux den folgenden Befehl aus:**

   ```bash
   zip -r publish.zip
   ```

## <a name="upload-files-to-azure"></a>Hochladen von Dateien in Azure

Im nächsten Schritt verwenden Sie Azure Storage-Explorer, um die folgenden fünf Dateien in den Blobcontainer hochzuladen, den Sie als Speicher für Ihren Cluster ausgewählt haben:

* Microsoft.Spark.Worker
* install-worker.sh
* publish.zip
* microsoft-spark-2.3.x-0.3.0.jar
* input.txt.

1. Öffnen Sie Azure Storage-Explorer, und navigieren Sie im Menü auf der linken Seite zu Ihrem Speicherkonto. Führen Sie einen Drilldown zum Blobcontainer für Ihren Cluster unter **Blobcontainer** in Ihrem Speicherkonto aus.

2. *Microsoft.Spark.Worker* unterstützt Apache Spark bei der Ausführung Ihrer App, z.B. für benutzerdefinierte Funktionen (User-Defined Functions, UDFs), die Sie ggf. geschrieben haben. Laden Sie [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases/download/v0.3.0/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.3.0.tar.gz) herunter. Wählen Sie dann in Azure Storage-Explorer **Hochladen** aus, um den Worker hochzuladen.

   ![Hochladen von Dateien in Azure Storage-Explorer](./media/hdinsight-deployment/upload-files-to-storage.png)

3. *install-worker.sh* ist ein Skript, mit dem Sie von .NET für Apache Spark abhängige Dateien in die Knoten Ihres Clusters kopieren können.

   Erstellen Sie eine neue Datei mit dem Namen **install-worker.sh** auf Ihrem lokalen Computer, und fügen Sie den [Inhalt von install-worker.sh](https://raw.githubusercontent.com/dotnet/spark/master/deployment/install-worker.sh) auf GitHub ein. Laden Sie dann *install-worker.sh* in Ihren Blobcontainer hoch.

4. Ihr Cluster benötigt die Datei „publish.zip“, die die veröffentlichten Dateien Ihrer App enthält. Navigieren Sie zu Ihrem veröffentlichten Ordner **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, und suchen Sie nach **publish.zip**. Laden Sie dann *publish.zip* in Ihren Blobcontainer hoch.

5. Ihr Cluster benötigt den Anwendungscode, der in einer JAR-Datei gepackt wurde. Navigieren Sie zu Ihrem veröffentlichten Ordner **mySparkApp/bin/Release/netcoreapp3.0/ubuntu.16.04-x64**, und suchen Sie nach **microsoft-spark-2.3.x-0.3.0.jar**. Laden Sie die JAR-Datei dann in Ihren Blobcontainer hoch.

   Möglicherweise gibt es mehrere JAR-Dateien (für die Versionen 2.3.x und 2.4.x von Spark). Sie müssen die JAR-Datei auswählen, die mit der Version von Spark übereinstimmt, die Sie während der Clustererstellung ausgewählt haben. Wählen Sie beispielsweise *microsoft-spark-2.3.x-0.3.0.jar* aus, wenn Sie Spark 2.3.2 während der Clustererstellung ausgewählt haben.

6. Ihr Cluster benötigt die Eingabe in Ihre App. Navigieren Sie zu Ihrem Verzeichnis **mySparkApp**, und suchen Sie nach **input.txt**. Laden Sie die Eingabedatei in das Verzeichnis **user/sshuser** in Ihren Blobcontainer hoch. Sie stellen über SSH eine Verbindung mit Ihrem Cluster her, und in diesem Ordner sucht der Cluster nach der Eingabe. Die Datei *input.txt* ist die einzige Datei, die in ein bestimmtes Verzeichnis hochgeladen wurde.

## <a name="run-the-hdinsight-script-action"></a>Ausführen der HDInsight-Skriptaktion

Sobald der Cluster ausgeführt wird und Sie Ihre Dateien in Azure hochgeladen haben, führen Sie das Skript **install-worker.sh** auf dem Cluster aus.

1. Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **Skriptaktionen**aus.

2. Wählen Sie **+ Neue übermitteln** aus, und geben Sie die folgenden Werte an:

   |Eigenschaft  |Beschreibung  |
   |---------|---------|
   | Skripttyp |Benutzerdefiniert|
   | name | Installieren des Workers|
   | Bash-Skript-URI |`https://mystorageaccount.blob.core.windows.net/mycontainer/install-worker.sh` </br> Klicken Sie zum Bestätigen dieses URIs in Azure Storage-Explorer mit der rechten Maustaste auf „install-Worker.sh“, und wählen Sie „Eigenschaften“ aus. |
   | Knotentyp(en)| Worker|
   | Parameter | azure </br> wasbs://mycontainer@myStorageAccount.blob.core.windows.net/Microsoft.Spark.Worker.netcoreapp2.1.linux-x64-0.6.0.tar.gz </br> /usr/local/bin

3. Wählen Sie **Erstellen** aus, um das Skript zu übermitteln.

## <a name="run-your-app"></a>Ausführen der App

1. Navigieren Sie im Azure-Portal zu Ihrem HDInsight Spark-Cluster, und wählen Sie dann **SSH und Clusteranmeldung**aus.

2. Kopieren Sie die SSH-Anmeldeinformationen, und fügen Sie diese in ein Terminal ein. Melden Sie sich mit dem Kennwort, das Sie während der Clustererstellung festgelegt haben, bei Ihrem Cluster an. Es sollten Meldungen angezeigt werden, die Sie bei Ubuntu und Spark Willkommen heißen.

3. Verwenden Sie den Befehl **spark-submit**, um Ihre App auf dem HDInsight-Cluster auszuführen. Denken Sie daran, **mycontainer** und **mystorageaccount** im Beispielskript durch die tatsächlichen Namen Ihres Blobcontainers und Speicherkontos zu ersetzen.

   ```bash
   $SPARK_HOME/bin/spark-submit \
   --master yarn \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/microsoft-spark-2.3.x-0.6.0.jar \
   wasbs://mycontainer@mystorageaccount.blob.core.windows.net/publish.zip mySparkApp
   ```

   Wenn Ihre App ausgeführt wird, wird die gleiche Wortzahltabelle aus der lokalen Ausführung von „Erste Schritte“ in der Konsole angezeigt. Herzlichen Glückwunsch, Sie haben Ihre erste .NET-Anwendung für Apache Spark in der Cloud ausgeführt!

## <a name="clean-up-resources"></a>Bereinigen von Ressourcen

HDInsight speichert Ihre Daten in Azure Storage, sodass Sie einen Cluster problemlos löschen können, wenn er nicht verwendet wird. Für einen HDInsight-Cluster fallen auch dann Gebühren an, wenn er nicht verwendet wird. Da die Gebühren für den Cluster erheblich höher sind als die Kosten für den Speicher, ist es sinnvoll, nicht verwendete Cluster zu löschen.

Sie können auch den Namen der Ressourcengruppe auswählen, um die Seite für die Ressourcengruppe zu öffnen, und dann **Ressourcengruppe löschen** auswählen. Indem Sie die Ressourcengruppe löschen, löschen Sie sowohl den HDInsight Spark-Cluster als auch das Standardspeicherkonto.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie eine .NET für Apache Spark-Anwendung in Azure HDInsight bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu Azure HDInsight.

> [!div class="nextstepaction"]
> [Azure HDInsight-Dokumentation](/azure/hdinsight/)
