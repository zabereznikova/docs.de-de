---
title: Herunterladen von Beispieldatenbanken (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795175"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Herunterladen von Beispieldatenbanken (LINQ to DataSet)
In den Beispielen und exemplarischen Vorgehensweisen in der LINQ to DataSet-Dokumentation wird die AdventureWorks-Beispieldatenbank verwendet. Sie können dieses Produkt kostenlos von der Microsoft-Downloadsite herunterladen. In den Beispielen und exemplarischen Vorgehensweisen in der LINQ to DataSet-Dokumentation wird SQL Server als Datenspeicher verwendet. Statt SQL Server kann als Datenspeicher auch die kostenlos erhältliche SQL Server Express Edition verwendet werden.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Herunterladen und Installieren der &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Datenbank  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>So können Sie die &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Beispieldatenbank für SQL Server herunterladen und installieren  
  
1. Öffnen Sie Internet Explorer.  
  
2. Wechseln Sie zur Website [SQL Server 2005-Beispiele und-Beispiel Datenbanken](https://go.microsoft.com/fwlink/?linkid=31046) .  
  
3. Befolgen Sie die Anweisungen zum Herunterladen der AdventureWorks-Beispieldatenbank für Ihren Prozessortyp (z. B. AdventureWorksDB.msi), und speichern Sie die MSI-Datei auf Ihrem lokalen Computer.  
  
4. Wenn Sie bereits eine frühere &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt;-Version heruntergeladen und installiert haben oder wenn &lt;legacyBold&gt;AdventureWorks&lt;/legacyBold&gt; während der SQL-Einrichtung installiert wurde, müssen Sie diese frühere Version entfernen, bevor Sie &lt;legacyBold&gt;AdventureWorks.msi&lt;/legacyBold&gt; ausführen.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>So entfernen Sie eine zuvor heruntergeladene und installierte "AdventureWorks"-Beispieldatenbank  
  
1. Trennen Sie die Verbindung zur AdventureWorks- bzw. AdventureWorksDW-Datenbank.  
  
2. Wählen **Sie unter Software**die Option **AdventureWorksDB** oder **AdventureWorksBI** aus, und klicken Sie auf **Entfernen**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>So entfernen Sie eine zuvor mit Setup installierte "AdventureWorks"-Beispieldatenbank  
  
1. Trennen Sie die Verbindung zur AdventureWorks- bzw. AdventureWorksDW-Datenbank.  
  
2. Wählen **Sie unter Software**die Option **Microsoft SQL Server 2005** aus, und klicken Sie auf **ändern**.  
  
3. Wählen Sie in der **Komponentenauswahl**Arbeitsstations **Komponenten** aus, und klicken Sie dann auf **weiter**.  
  
4. Klicken Sie **in der Willkommensseite des Installations-Assistenten für SQL Server**auf **weiter**.  
  
5. Klicken Sie in **Systemkonfigurationsüberprüfung**auf **weiter**.  
  
6. Klicken Sie in **Instanz ändern oder entfernen**auf **installierte Komponenten ändern**.  
  
7. Erweitern Sie unter **Funktionsauswahl**den Knoten **Dokumentation, Beispiele und Beispiel Datenbanken** .  
  
8. Wählen Sie **Beispiel Code und-Anwendungen**aus. Erweitern Sie **Beispiel Datenbanken**, wählen Sie die zu entfernende Beispieldatenbank aus, und wählen Sie das **gesamte Feature wird nicht verfügbar**. Klicken Sie auf **Weiter**.  
  
9. Klicken Sie auf **Installieren** , und schließen Sie den Assistenten ab.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>So fügen Sie die "AdventureWorks"-Beispieldatenbankdateien an eine Instanz von SQL Server an  
  
1. Nachdem die Datei Sample Database Installer-Datei heruntergeladen wurde, doppelklicken Sie auf die Datei **AdventureWorksDB. msi** (oder die Datei, die Sie heruntergeladen haben), um die Datenbank zu installieren. Der Standardspeicherort für die Datenbank ist &lt;legacyBold&gt;c:\Programme\Microsoft SQL Server\MSSQL.1\MSSQL\Data&lt;/legacyBold&gt;.  
  
2. Fügen Sie die AdventureWorks-Datenbankdateien an eine Instanz von SQL Server an, indem Sie das folgende SQLCMD- oder SQL Server Management Studio-Skript ausführen:  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Wenn Sie diese Dateien in einem anderen Verzeichnis oder auf einem anderen Laufwerk installiert haben, müssen Sie die Pfade entsprechend anpassen, bevor Sie die gespeicherte Prozedur `sp_attach_db` ausführen.  
  
## <a name="downloading-sql-server-express-edition"></a>Herunterladen von SQL Server Express Edition  
 In den Beispielen und exemplarischen Vorgehensweisen im LINQ to DataSet Abschnitt wird SQL Server 2005 als Datenspeicher verwendet, Sie können jedoch so geändert werden, dass stattdessen SQL Server Express Edition verwendet wird. SQL Server Express Edition ist frei verfügbar, und Sie können diese Lösung mit Anwendungen verteilen. Wenn Sie Visual Studio verwenden, ist SQL Server Express Edition in den Editionen pro und höher enthalten.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>So können Sie SQL Server Express Edition herunterladen und installieren  
  
1. Öffnen Sie Internet Explorer.  
  
2. Wechseln Sie zur Downloadseite der [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) .  
  
3. Befolgen Sie die Installationsanleitungen auf der Website.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](getting-started-linq-to-dataset.md)
