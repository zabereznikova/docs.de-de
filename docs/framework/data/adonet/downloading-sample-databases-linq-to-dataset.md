---
title: "Herunterladen von Beispieldatenbanken (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Herunterladen von Beispieldatenbanken (LINQ to DataSet)
In den Beispielen und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Dokumentation wird auf die \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank zurückgegriffen.  Sie können dieses Produkt kostenlos von der Microsoft\-Downloadsite herunterladen. Als Datenspeicher für die Beispiele und exemplarischen Vorgehensweisen in der [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]\-Dokumentation wird SQL Server verwendet.  Statt SQL Server kann als Datenspeicher auch die kostenlos erhältliche SQL Server Express Edition verwendet werden.  
  
## Herunterladen und Installieren der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Datenbank  
  
#### So können Sie die \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank für SQL Server herunterladen und installieren  
  
1.  Öffnen Sie Internet Explorer.  
  
2.  Wechseln Sie zur Website [SQL Server 2005 Samples and Sample Databases](http://go.microsoft.com/fwlink/?linkid=31046).  
  
3.  Befolgen Sie die Anweisungen zum Herunterladen der \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Beispieldatenbank für Ihren Prozessortyp \(z. B. \<legacyBold\>AdventureWorksDB.msi\<\/legacyBold\>\), und speichern Sie die MSI\-Datei auf Ihrem lokalen Computer.  
  
4.  Wenn Sie bereits eine frühere \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Version heruntergeladen und installiert haben oder wenn \<legacyBold\>AdventureWorks\<\/legacyBold\> während der SQL\-Einrichtung installiert wurde, müssen Sie diese frühere Version entfernen, bevor Sie \<legacyBold\>AdventureWorks.msi\<\/legacyBold\> ausführen.  
  
#### So entfernen Sie eine zuvor heruntergeladene und installierte "AdventureWorks"\-Beispieldatenbank  
  
1.  Trennen Sie die Verbindung zur \<legacyBold\>AdventureWorks\<\/legacyBold\>\- bzw. \<legacyBold\>AdventureWorksDW\<\/legacyBold\>\-Datenbank.  
  
2.  Wählen Sie in **Software** **AdventureWorksDB** bzw. **AdventureWorksBI** aus, und klicken Sie auf **Entfernen**.  
  
#### So entfernen Sie eine zuvor mit Setup installierte "AdventureWorks"\-Beispieldatenbank  
  
1.  Trennen Sie die Verbindung zur \<legacyBold\>AdventureWorks\<\/legacyBold\>\- bzw. \<legacyBold\>AdventureWorksDW\<\/legacyBold\>\-Datenbank.  
  
2.  Wählen Sie in **Software** **Microsoft SQL Server 2005** aus, und klicken Sie auf **Ändern**.  
  
3.  Wählen Sie in **Komponentenauswahl** **Arbeitsstationskomponenten** aus, und klicken Sie dann **auf Weiter**.  
  
4.  Klicken Sie in auf der Begrüßungsseite des Installations\-Assistenten für Microsoft SQL Server auf **Weiter**.  
  
5.  Klicken Sie in **Systemkonfigurationsüberprüfung** auf **Weiter**.  
  
6.  Klicken Sie in **Instanz ändern oder entfernen** auf **Installierte Komponenten ändern**.  
  
7.  Erweitern Sie in **Funktionsauswahl** den Knoten **Dokumentation, Beispiele und Beispieldatenbanken**.  
  
8.  Wählen Sie **Beispielcode und \-anwendungen** aus.  Erweitern Sie den Knoten **Beispieldatenbanken**, wählen Sie die Beispieldatenbank aus, die entfernt werden soll, und wählen Sie **Die gesamte Funktion wird nicht verfügbar sein.** aus.  Klicken Sie auf **Weiter**.  
  
9. Klicken Sie auf **Installieren**, und stellen Sie den Installations\-Assistenten fertig.  
  
#### So fügen Sie die "AdventureWorks"\-Beispieldatenbankdateien an eine Instanz von SQL Server an  
  
1.  Doppelklicken Sie nach dem Herunterladen der Beispieldatenbankdatei auf die Datei **AdventureWorksDB.msi** \(bzw. die von Ihnen heruntergeladene Datei\), um die Datenbank zu installieren.  Der Standardspeicherort für die Datenbank ist \<legacyBold\>c:\\Programme\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data\<\/legacyBold\>.  
  
2.  Fügen Sie die \<legacyBold\>AdventureWorks\<\/legacyBold\>\-Datenbankdateien an eine Instanz von SQL Server an, indem Sie das folgende SQLCMD\- oder SQL Server Management Studio\-Skript ausführen:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Wenn Sie diese Dateien in einem anderen Verzeichnis oder auf einem anderen Laufwerk installiert haben, müssen Sie die Pfade entsprechend anpassen, bevor Sie die gespeicherte Prozedur `sp_attach_db` ausführen.  
  
## Herunterladen von SQL Server Express Edition  
 Die Beispiele und exemplarischen Vorgehensweisen im Abschnitt zu [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] verwenden als Datenspeicher SQL Server 2005. Sie können aber auch festlegen, dass SQL Server Express Edition verwendet werden soll.  SQL Server Express Edition ist frei verfügbar, und Sie können diese Lösung mit Anwendungen verteilen.  Wenn Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] verwenden, ist SQL Server Express Edition in allen Editionen ab der Professional Edition enthalten.  
  
#### So können Sie SQL Server Express Edition herunterladen und installieren  
  
1.  Öffnen Sie Internet Explorer.  
  
2.  Rufen Sie die Downloadseite von [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) auf.  
  
3.  Befolgen Sie die Installationsanleitungen auf der Website.  
  
## Siehe auch  
 [Erste Schritte](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)