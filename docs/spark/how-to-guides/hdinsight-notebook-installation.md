---
title: Installieren von .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern
description: Erfahren Sie, wie Sie .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight installieren.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 14babf7a551192b286f309393e3bbff25d4745d5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617742"
---
# <a name="install-net-for-apache-spark-on-jupyter-notebooks-on-azure-hdinsight-spark-clusters"></a>Installieren von .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern

In diesem Artikel erfahren Sie, wie Sie .NET für Apache Spark für Jupyter Notebooks in Azure HDInsight Spark-Clustern installieren. Sie können .NET für Apache Spark über eine Kombination aus der Befehlszeile und dem Azure-Portal in Azure HDInsight-Clustern bereitstellen (weitere Informationen finden Sie unter [Bereitstellen einer .NET für Apache Spark-Anwendung für Azure HDInsight](../tutorials/hdinsight-deployment.md)), aber Notebooks ermöglichen iterative Funktionen mit mehr Interaktion.

Jupyter Notebooks ist bereits in Azure HDInsight-Clustern integriert, deshalb müssen Sie es lediglich für die Ausführung von .NET für Apache Spark konfigurieren. Um .NET für Apache Spark in Ihren Jupyter Notebooks zu verwenden, wird eine C#-REPL benötigt, um Ihren C#-Code Zeile für Zeile auszuführen und bei Bedarf den Ausführungsstatus beizubehalten. [Try .NET](https://github.com/dotnet/try) wurde als offizielle .NET-REPL integriert.

Um .NET für Apache Spark über die Jupyter Notebooks-Benutzeroberfläche zu aktivieren, müssen Sie einige manuelle Schritte über [Ambari](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-manage-ambari) ausführen und [Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux) im HDInsight Spark-Cluster ausführen.

> [!NOTE]
> Dieses Feature ist *experimentell* und wird nicht vom HDInsight Spark-Team unterstützt.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="prerequisites"></a>Voraussetzungen

Sofern noch nicht vorhanden, erstellen Sie einen [Azure HDInsight Spark](https://docs.microsoft.com/azure/hdinsight/spark/apache-spark-jupyter-spark-sql-use-portal#create-an-apache-spark-cluster-in-hdinsight)-Cluster.

1. Wechseln Sie zum [Azure-Portal](https://portal.azure.com), und klicken Sie auf **+ Ressource erstellen**.

1. Erstellen Sie eine neue Azure HDInsight-Clusterressource. Wählen Sie während der Clustererstellung **Spark 2.4** und **HDI 4.0** aus.

## <a name="install-net-for-apache-spark"></a>Installieren von .NET für Apache Spark

Wählen Sie im Azure-Portal den im vorherigen Schritt erstellten **HDInsight Spark-Cluster** aus.

### <a name="stop-the-livy-server"></a>Beenden des Livy-Servers

1. Klicken Sie im Portal auf **Übersicht** und dann auf **Ambari-Homepage**. Geben Sie bei Aufforderung die Anmeldeinformationen für den Cluster ein.

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-ambari.png)

2. Wählen Sie im links angezeigten Navigationsmenü **Spark2** aus, und klicken Sie auf **LIVY FOR SPARK2 SERVER**.

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-livyserver.png)

3. Wählen Sie **hn0... host** aus.

   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/select-host.png)

4. Klicken Sie auf die Auslassungspunkte neben **Livy for Spark2 Server**, und klicken Sie auf **Stop** (Beenden). Klicken Sie in der Aufforderung auf **OK**, um den Vorgang fortzusetzen.

   Beenden Sie den Server „Livy for Spark2“.
   ![Beenden des Livy-Servers](./media/hdinsight-notebook-installation/stop-server.png)

5. Wiederholen Sie die vorherigen Schritte für **hn1... host**.

### <a name="submit-an-hdinsight-script-action"></a>Übermitteln einer HDInsight-Skriptaktion

1. `install-interactive-notebook.sh` ist ein Skript, mit dem .NET for Apache Spark installiert wird und Änderungen an Apache Livy und sparkmagic durchgeführt werden. Bevor Sie eine Skriptaktion an HDInsight übermitteln, müssen Sie `install-interactive-notebook.sh` erstellen und hochladen.

   Erstellen Sie eine neue Datei namens **install-interactive-notebook.sh** auf Ihrem lokalen Computer, und fügen Sie die Inhalte von [install-interactive-notebook.sh contents](https://raw.githubusercontent.com/dotnet/spark/master/deployment/HDI-Spark/Notebooks/install-interactive-notebook.sh) darin ein.

   Laden Sie das Skript an einen [URI](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux#understand-script-actions) hoch, der für den HDInsight-Cluster zugänglich ist. Beispielsweise `https://<my storage account>.blob.core.windows.net/<my container>/<some dir>/install-interactive-notebook.sh`.

2. Führen Sie mithilfe der [HDInsight-Skriptaktionen](https://docs.microsoft.com/azure/hdinsight/hdinsight-hadoop-customize-cluster-linux)`install-interactive-notebook.sh` auf dem Cluster aus.

   Wechseln Sie zurück zum HDI-Cluster im Azure-Portal, und wählen Sie aus den links angezeigten Optionen **Skriptaktionen** aus. Sie übermitteln eine Skriptaktion zum Bereitstellen der .NET für Apache Spark-REPL für Ihren HDInsight Spark-Cluster. Verwenden Sie folgende Einstellungen:

   |Eigenschaft  |Beschreibung  |
   |---------|---------|
   | Skripttyp | Benutzerdefiniert |
   | Name | *Installation der interaktiven Notebook-Benutzeroberfläche für .NET for Apache Spark* |
   | Bash-Skript-URI | Der URI für die hochgeladene Datei `install-interactive-notebook.sh`. |
   | Knotentyp(en)| Hauptknoten und Worker |
   | Parameter | Version von .NET für Apache Spark. Überprüfen Sie ggf. die [.NET für Apache Spark-Releases](https://github.com/dotnet/spark/releases). Wenn Sie beispielsweise Sparkdotnet 0.6.0 installieren möchten, wäre dies `0.6.0`.

   Wechseln Sie zum nächsten Schritt, wenn ein grünes Häkchen neben dem Status der Skriptaktion angezeigt wird.

### <a name="start-the-livy-server"></a>Starten des Livy-Servers

Folgen Sie den Anweisungen im Abschnitt [Beenden des Livy-Servers](#stop-the-livy-server), um den Livy for Spark2-Server für die Hosts **hn0** und **hn1** zu **Starten** (statt sie wie vorher zu **Beenden**).

### <a name="set-up-spark-default-configurations"></a>Einrichten der Spark-Standardkonfigurationen

1. Klicken Sie im Portal auf **Übersicht** und dann auf **Ambari-Homepage**. Geben Sie die Anmeldeinformationen für den Cluster ein, wenn Sie dazu aufgefordert werden.

2. Wählen Sie **Spark2** und **CONFIGS** aus. Klicken Sie dann auf **Custom spark2-defaults**.

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/spark-configs.png)

3. Wählen Sie **Add Property** (Eigenschaft hinzufügen) aus, um Spark-Standardeinstellungen hinzuzufügen.

   ![Hinzufügen einer Eigenschaft](./media/hdinsight-notebook-installation/add-property.png)

   Es sind drei Eigenschaften vorhanden. Fügen Sie diese nacheinander mit dem Eigenschaftstyp **TEXT** im Modus zum Hinzufügen einzelner Eigenschaften hinzu. Vergewissern Sie sich, dass vor und nach den Schlüsseln/Werten keine Leerzeichen vorhanden sind.

   * **Eigenschaft 1**
       * Schlüssel:&ensp;&ensp;`spark.dotnet.shell.command`
       * Wert: `/usr/share/dotnet-tools/dotnet-try,kernel-server,--default-kernel,csharp`

   * **Eigenschaft 2** Verwenden Sie die Version von .NET für Apache Spark, die Sie in der vorherigen Skriptaktion verwendet haben.
       * Schlüssel:&ensp;&ensp;`spark.dotnet.packages`
       * Wert: `["nuget: Microsoft.Spark, 0.6.0", "nuget: Microsoft.Spark.Extensions.Delta, 0.6.0"]`

   * **Eigenschaft 3**
       * Schlüssel:&ensp;&ensp;`spark.dotnet.interpreter`
       * Wert: `try`

   Die folgende Abbildung zeigt beispielsweise die Einstellung für die hinzugefügte Eigenschaft 1:

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/add-sparkconfig.png)

   Nachdem Sie die drei Eigenschaften hinzugefügt haben, klicken Sie auf **SAVE** (Speichern). Falls eine Warnung mit Konfigurationsempfehlungen angezeigt wird, klicken Sie auf **PROCEED ANYWAY** (Vorgang trotzdem fortsetzen).

4. Starten Sie die betroffenen Komponenten neu.

   Nach dem Hinzufügen neuer Eigenschaften müssen Sie Komponenten neu starten, die von den Änderungen betroffen sind. Wählen Sie im oberen Bereich **RESTART** (Neu starten) und dann in der Dropdownliste **Restart All Affected** (Alle betroffenen neu starten) aus.

   ![Festlegen der Konfigurationen](./media/hdinsight-notebook-installation/restart-affected.png)

   Wählen Sie bei Aufforderung **CONFIRM RESTART ALL** (Neustart für alle bestätigen) und **OK** aus, um den Vorgang abzuschließen.

## <a name="submit-jobs-through-a-jupyter-notebook"></a>Übermitteln von Aufträgen über ein Jupyter Notebook

Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie jetzt Ihre .NET für Apache Spark-Aufträge über Jupyter Notebooks übermitteln.

1. Erstellen Sie ein neues .NET für Apache Spark-Notebook. Starten Sie ein Jupyter Notebook aus Ihrem HDI-Cluster im Azure-Portal.

   ![Jupyter Notebook starten](./media/hdinsight-notebook-installation/launch-notebook.png)

   Wählen Sie **Neu** >  **.NET Spark (C#)** aus, um ein Notebook zu erstellen.

   ![Jupyter Notebook](./media/hdinsight-notebook-installation/create-sparkdotnet-notebook.png)

2. Übermitteln Sie Aufträge mit .NET for Apache Spark.

   Verwenden Sie den folgenden Codeausschnitt, um einen DataFrame zu erstellen:

   ```csharp
   var df = spark.Range(0,5);
   df.Show();
   ```

   ![Übermitteln eines Spark-Auftrags](./media/hdinsight-notebook-installation/create-df.png)

   Verwenden Sie den folgenden Codeausschnitt, um eine benutzerdefinierte Funktion zu erstellen und diese mit DataFrames zu verwenden:

   ```csharp
   var myawesomeudf = Udf<int, string>((id) => $"hello {id}");
   df.Select(myawesomeudf(df["id"])).Show();
   ```

   ![Übermitteln eines Spark-Auftrags](./media/hdinsight-notebook-installation/run-udf.png)

## <a name="next-steps"></a>Nächste Schritte

* [Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [HDInsight-Dokumentation](https://docs.microsoft.com/azure/hdinsight/)
