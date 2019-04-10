---
title: Herunterladen von Beispieldatenbanken (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: 1ef5a5ceac6a7f819551f6221b63197786ab4f09
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59339709"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Herunterladen von Beispieldatenbanken (LINQ to DataSet)
Die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Dokumentation verwenden die AdventureWorks-Beispieldatenbank. Sie können dieses Produkt kostenlos von der Microsoft-Downloadsite herunterladen. Als Datenspeicher für die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Dokumentation wird SQL Server verwendet. Statt SQL Server kann als Datenspeicher auch die kostenlos erhältliche SQL Server Express Edition verwendet werden.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Herunterladen und Installieren der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>So können Sie die &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank für SQL Server herunterladen und installieren  
  
1. Öffnen Sie Internet Explorer.  
  
2. Wechseln Sie zu der [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Website.  
  
3. Befolgen Sie die Anweisungen zum Herunterladen der AdventureWorks-Beispieldatenbank für Ihren Prozessortyp (z. B. AdventureWorksDB.msi), und speichern Sie die MSI-Datei auf Ihrem lokalen Computer.  
  
4. Wenn Sie bereits eine frühere &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Version heruntergeladen und installiert haben oder wenn &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt; während der SQL-Einrichtung installiert wurde, müssen Sie diese frühere Version entfernen, bevor Sie &lt;legacyBold&gt;AdventureWorks.msi&lt;/legacyBold&gt; ausführen.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>So entfernen Sie eine zuvor heruntergeladene und installierte "AdventureWorks"-Beispieldatenbank  
  
1. Trennen Sie die Verbindung zur AdventureWorks- bzw. AdventureWorksDW-Datenbank.  
  
2. Von **Software**Option **AdventureWorksDB** oder **AdventureWorksBI** , und klicken Sie auf **entfernen**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>So entfernen Sie eine zuvor mit Setup installierte "AdventureWorks"-Beispieldatenbank  
  
1. Trennen Sie die Verbindung zur AdventureWorks- bzw. AdventureWorksDW-Datenbank.  
  
2. Von **Software**Option **Microsoft SQL Server 2005** , und klicken Sie auf **Änderung**.  
  
3. Von **Komponentenauswahl**Option **Arbeitsstationskomponenten** , und klicken Sie dann auf **Weiter**.  
  
4. Von **Willkommen beim SQL Server-Installations-Assistenten**, klicken Sie auf **Weiter**.  
  
5. Von **Systemkonfigurationsüberprüfung**, klicken Sie auf **Weiter**.  
  
6. Von **Instanz ändern oder entfernen**, klicken Sie auf **installierte Komponenten ändern**.  
  
7. Von **Funktionsauswahl**, erweitern Sie die **Dokumentation, Beispiele und Beispieldatenbanken** Knoten.  
  
8. Wählen Sie **Beispielcode und Anwendungen**. Erweitern Sie **Sample Databases**, wählen Sie die Beispieldatenbank entfernt werden soll, und wählen Sie **gesamte Feature wird nicht mehr verfügbar sein**. Klicken Sie auf **Weiter**.  
  
9. Klicken Sie auf **installieren** , und schließen Sie den Installations-Assistenten.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>So fügen Sie die "AdventureWorks"-Beispieldatenbankdateien an eine Instanz von SQL Server an  
  
1. Nachdem die Datei-Beispiel-Datenbank-Installer-Datei heruntergeladen wurde, doppelklicken Sie auf die **AdventureWorksDB.msi** Datei (oder die Datei, die Sie heruntergeladen haben) zum Installieren der Datenbank. Der Standardspeicherort für die Datenbank ist &lt;legacyBold&gt;c:\Programme\Microsoft SQL Server\MSSQL.1\MSSQL\Data&lt;/legacyBold&gt;.  
  
2. Fügen Sie die AdventureWorks-Datenbankdateien an eine Instanz von SQL Server an, indem Sie das folgende SQLCMD- oder SQL Server Management Studio-Skript ausführen:  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Wenn Sie diese Dateien in einem anderen Verzeichnis oder auf einem anderen Laufwerk installiert haben, müssen Sie die Pfade entsprechend anpassen, bevor Sie die gespeicherte Prozedur `sp_attach_db` ausführen.  
  
## <a name="downloading-sql-server-express-edition"></a>Herunterladen von SQL Server Express Edition  
 Die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abschnitt SQL Server 2005 als Datenspeicher verwenden, jedoch kann geändert werden, um SQL Server Express Edition verwenden. SQL Server Express Edition ist frei verfügbar, und Sie können diese Lösung mit Anwendungen verteilen. Wenn Sie Visual Studio verwenden, ist SQL Server Express Edition in den Editionen Pro und höheren enthalten.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>So können Sie SQL Server Express Edition herunterladen und installieren  
  
1. Öffnen Sie Internet Explorer.  
  
2. Wechseln Sie zu der [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) Downloadseite.  
  
3. Befolgen Sie die Installationsanleitungen auf der Website.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
