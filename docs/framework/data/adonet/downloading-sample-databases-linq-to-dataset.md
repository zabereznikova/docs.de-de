---
title: Herunterladen von Beispieldatenbanken (LINQ to DataSet)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 6450e683f51abe0bdd4eb7f45089f04d11660d5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Herunterladen von Beispieldatenbanken (LINQ to DataSet)
Die Beispiele und exemplarische Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Dokumentation verwenden die AdventureWorks-Beispieldatenbank. Sie können dieses Produkt kostenlos von der Microsoft-Downloadsite herunterladen. Als Datenspeicher für die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Dokumentation wird SQL Server verwendet. Statt SQL Server kann als Datenspeicher auch die kostenlos erhältliche SQL Server Express Edition verwendet werden.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Herunterladen und Installieren der <legacyBold>AdventureWorks</legacyBold>-Datenbank  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>So können Sie die <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank für SQL Server herunterladen und installieren  
  
1.  Öffnen Sie Internet Explorer.  
  
2.  Wechseln Sie zu der [SQL Server 2005 Samples and Sample Databases](http://go.microsoft.com/fwlink/?linkid=31046) Website.  
  
3.  Befolgen Sie die Anweisungen zum Herunterladen der <legacyBold>AdventureWorks</legacyBold>-Beispieldatenbank für Ihren Prozessortyp (z. B. <legacyBold>AdventureWorksDB.msi</legacyBold>), und speichern Sie die MSI-Datei auf Ihrem lokalen Computer.  
  
4.  Wenn Sie bereits eine frühere <legacyBold>AdventureWorks</legacyBold>-Version heruntergeladen und installiert haben oder wenn <legacyBold>AdventureWorks</legacyBold> während der SQL-Einrichtung installiert wurde, müssen Sie diese frühere Version entfernen, bevor Sie <legacyBold>AdventureWorks.msi</legacyBold> ausführen.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>So entfernen Sie eine zuvor heruntergeladene und installierte "AdventureWorks"-Beispieldatenbank  
  
1.  Trennen Sie die Verbindung zur <legacyBold>AdventureWorks</legacyBold>- bzw. <legacyBold>AdventureWorksDW</legacyBold>-Datenbank.  
  
2.  Von **Software**Option **AdventureWorksDB** oder **AdventureWorksBI** , und klicken Sie auf **entfernen**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>So entfernen Sie eine zuvor mit Setup installierte "AdventureWorks"-Beispieldatenbank  
  
1.  Trennen Sie die Verbindung zur <legacyBold>AdventureWorks</legacyBold>- bzw. <legacyBold>AdventureWorksDW</legacyBold>-Datenbank.  
  
2.  Von **Software**Option **Microsoft SQL Server 2005** , und klicken Sie auf **Änderung**.  
  
3.  Von **Komponentenauswahl**Option **Arbeitsstationskomponenten** , und klicken Sie dann auf **Weiter**.  
  
4.  Von **Willkommen beim Installations-Assistenten von SQL Server**, klicken Sie auf **Weiter**.  
  
5.  Von **Systemkonfigurationsüberprüfung**, klicken Sie auf **Weiter**.  
  
6.  Von **Instanz ändern oder entfernen**, klicken Sie auf **installierte Komponenten ändern**.  
  
7.  Von **Funktionsauswahl**, erweitern Sie die **Dokumentation, Beispiele und Beispieldatenbanken** Knoten.  
  
8.  Wählen Sie **Beispielcode und Anwendungen**. Erweitern Sie **Sample Databases**, wählen Sie die Beispieldatenbank entfernt werden soll, und wählen Sie aus **gesamte Funktion wird nicht verfügbar sein**. Klicken Sie auf **Weiter**.  
  
9. Klicken Sie auf **installieren** und beenden Sie den Installations-Assistenten.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>So fügen Sie die "AdventureWorks"-Beispieldatenbankdateien an eine Instanz von SQL Server an  
  
1.  Nachdem die Datei Beispiel Datenbank Installer-Datei heruntergeladen wurde, doppelklicken Sie auf die **AdventureWorksDB.msi** Datei (oder die Datei, die Sie heruntergeladen haben) zum Installieren der Datenbank. Der Standardspeicherort für die Datenbank ist <legacyBold>c:\Programme\Microsoft SQL Server\MSSQL.1\MSSQL\Data</legacyBold>.  
  
2.  Fügen Sie die <legacyBold>AdventureWorks</legacyBold>-Datenbankdateien an eine Instanz von SQL Server an, indem Sie das folgende SQLCMD- oder SQL Server Management Studio-Skript ausführen:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Wenn Sie diese Dateien in einem anderen Verzeichnis oder auf einem anderen Laufwerk installiert haben, müssen Sie die Pfade entsprechend anpassen, bevor Sie die gespeicherte Prozedur `sp_attach_db` ausführen.  
  
## <a name="downloading-sql-server-express-edition"></a>Herunterladen von SQL Server Express Edition  
 Die Beispiele und exemplarische Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abschnitt SQL Server 2005 als Datenspeicher verwenden, jedoch können geändert werden, um SQL Server Express Edition verwenden. SQL Server Express Edition ist frei verfügbar, und Sie können diese Lösung mit Anwendungen verteilen. Wenn Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwenden, ist SQL Server Express Edition in allen Editionen ab der Professional Edition enthalten.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>So können Sie SQL Server Express Edition herunterladen und installieren  
  
1.  Öffnen Sie Internet Explorer.  
  
2.  Wechseln Sie zu der [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) Downloadseite.  
  
3.  Befolgen Sie die Installationsanleitungen auf der Website.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
