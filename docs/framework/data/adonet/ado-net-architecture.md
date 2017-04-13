---
title: "ADO.NET-Architektur | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fcd45b99-ae8f-45ab-8b97-d887beda734e
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# ADO.NET-Architektur
Die traditionelle Datenverarbeitung basierte primär auf einem verbindungsbasierten Modell mit zwei Ebenen.  Da für die Datenverarbeitung immer mehr auf Architekturen mit mehreren Ebenen zurückgegriffen wird, wird verstärkt mit nicht verbundenen Lösungen gearbeitet, um eine bessere Skalierbarkeit der Anwendungen zu erzielen.  
  
## ADO.NET\-Komponenten  
 Die beiden Hauptkomponenten von [!INCLUDE[ado_orcas_long](../../../../includes/ado-orcas-long-md.md)] für den Zugriff auf und die Bearbeitung von Daten sind die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter und das <xref:System.Data.DataSet>.  
  
### .NET Framework\-Datenanbieter  
 Die .NET Framework\-Datenanbieter sind Komponenten, die explizit für die Datenbearbeitung und den schnellen, vorwärts gerichteten, schreibgeschützten Zugriff auf Daten entworfen wurden.  Das `Connection`\-Objekt sorgt für die Verbindung mit einer Datenquelle.  Mit dem `Command`\-Objekt können Sie auf Datenbankbefehle zugreifen, um Daten zurückzugeben oder zu ändern, gespeicherte Prozeduren auszuführen und Parameterinformationen zu senden oder abzurufen.  Der `DataReader` sorgt dafür, dass die Daten mit maximaler Geschwindigkeit per Stream bereitgestellt werden.  Der `DataAdapter` fungiert als Brücke zwischen dem `DataSet`\-Objekt und der Datenquelle.  Der `DataAdapter` verwendet zum Ausführen von SQL\-Befehlen an der Datenquelle `Command`\-Objekte, um damit sowohl Daten in das `DataSet` zu laden als auch um die Datenquelle mit den an den Daten im `DataSet` vorgenommenen Änderungen zu aktualisieren.  Weitere Informationen finden Sie unter [.NET Framework\-Datenanbieter](../../../../docs/framework/data/adonet/data-providers.md) und [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md).  
  
### Das "DataSet"  
 Das ADO.NET\-`DataSet` wurde explizit für den datenquellenunabhängigen Datenzugriff entwickelt.  Aus diesem Grund kann es mit mehreren, unterschiedlichen Datenquellen, mit XML\-Daten oder zum Verwalten von lokalen Anwendungsdaten verwendet werden.  Das `DataSet` enthält eine Auflistung von einem oder mehreren <xref:System.Data.DataTable>\-Objekten, die aus Datenzeilen und \-spalten sowie aus Primärschlüsseln, Fremdschlüsseln, Einschränkungen und Beziehungsinformationen zu den in den `DataTable`\-Objekten enthaltenen Daten bestehen.  Weitere Informationen finden Sie unter [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md).  
  
 Das folgende Diagramm zeigt die Beziehung zwischen einem [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Datenanbieter und einem `DataSet`.  
  
 ![ADO.Net](../../../../docs/framework/data/adonet/media/ado-1-bpuedev11.png "ado\_1\_bpuedev11")  
ADO.NET\-Architektur  
  
### Auswählen eines "DataReader" oder eines "DataSet"  
 Die Entscheidung, ob Ihre Anwendung einen `DataReader` \(siehe [Abrufen von Daten mit einem DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)\) oder ein `DataSet` \(siehe [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)\) verwenden soll, sollten Sie von der gewünschten Funktionalität Ihrer Anwendung abhängig machen.  Ein `DataSet` sollten Sie für folgende Aufgaben verwenden:  
  
-   Lokales Zwischenspeichern von Daten in Ihrer Anwendung, um sie bearbeiten zu können.  Wenn die Ergebnisse einer Abfrage nur gelesen werden sollen, ist der `DataReader` die bessere Wahl.  
  
-   Verschieben von Daten zwischen Ebenen oder von einem XML\-Webdienst.  
  
-   Dynamisches Interagieren mit Daten, wie Datenbindung an ein Windows Forms\-Steuerelement, oder Kombinieren von und Erstellen einer Beziehung zwischen Daten aus mehreren Quellen.  
  
-   Ausführen umfangreicher Datenverarbeitungsschritte ohne eine offene Verbindung zur Datenquelle. Dadurch wird die Verbindung zur Nutzung durch andere Clients freigegeben.  
  
 Wenn Sie die vom `DataSet` bereitgestellte Funktionalität nicht benötigen, können Sie die Geschwindigkeit Ihrer Anwendung verbessern, indem Sie den `DataReader` verwenden, der Ihre Daten vorwärts gerichtet und schreibgeschützt zurückgibt.  Obwohl der `DataAdapter` zum Füllen des `DataSet`\-Inhalts den `DataReader` verwendet \(siehe [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)\), können Sie durch die Verwendung des `DataReader` die Geschwindigkeit der Anwendung erhöhen, da sie auf diese Weise Arbeitsspeicher sparen, der anderenfalls vom `DataSet` beansprucht worden wäre. Außerdem entfällt der Verarbeitungsaufwand für das Erstellen und Füllen des `DataSet`.  
  
## LINQ to DataSet  
 LINQ to DataSet stellt Abfragefunktionen und Typüberprüfungsfunktionen zur Kompilierzeit über die in einem DataSet\-Objekt zwischengespeicherten Daten bereit.  Sie können damit Abfragen in einer der .NET Framework\-Entwicklungssprachen schreiben, z. B. in C\# oder Visual Basic.  Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## LINQ to SQL  
 LINQ to SQL unterstützt Abfragen für ein Objektmodell, das den Datenstrukturen einer relationalen Datenbank zugeordnet ist, ohne dass ein vorläufiges Konzeptmodell verwendet wird.  Jede Tabelle wird durch eine separate Klasse dargestellt, wodurch das Objektmodell eng mit dem relationalen Datenbankschema verbunden wird.  LINQ to SQL übersetzt im Objektmodell vorhandene LINQ\-Abfragen in Transact\-SQL und sendet diese zur Ausführung an die Datenbank.  Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt LINQ to SQL die Ergebnisse zurück in Objekte.  Weitere Informationen finden Sie unter [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## ADO.NET Entity Framework  
 Das ADO.NET Entity Framework wurde entworfen, um Entwicklern die Möglichkeit zu geben, Anwendungen für den Datenzugriff zu erstellen, indem sie bei der Programmierung auf ein konzeptionelles Anwendungsmodell zugreifen können, anstatt direkt mit einem relationalen Speicherschema zu arbeiten.  Das Ziel ist es, die Menge des Codes und den Wartungsaufwand zu verringern, die für datenorientierte Anwendungen erforderlich sind.  Weitere Informationen finden Sie unter [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
## WCF Data Services  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] wird verwendet, um Datendienste im Internet oder in einem Intranet bereitzustellen.  Die Daten werden gemäß den Spezifikationen des Entity Data Model in Entitäten und Beziehungen strukturiert.  Die in diesem Modell bereitgestellten Daten sind durch das Standard\-HTTP\-Protokoll adressierbar.  Weitere Informationen finden Sie unter [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md).  
  
## XML und ADO.NET  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] nutzt die Funktionen von XML, um Datenzugriff bei getrennter Verbindung zu ermöglichen.  [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] wurde gemeinsam mit den XML\-Klassen in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] entworfen. Beide sind Komponenten derselben Architektur.  
  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] und die XML\-Klassen in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] konvergieren im `DataSet`\-Objekt.  Das `DataSet` kann mit Daten aus einer XML\-Quelle gefüllt werden, gleich, ob es sich dabei um eine Datei oder um einen XML\-Stream handelt.  Das `DataSet` kann als W3C\-konformer XML\-Code geschrieben werden, dessen Schema als XSD\-Schema \(XML Schema Definition Language\) ausgeführt ist. Die Quelle der Daten im `DataSet` spielt dabei keine Rolle.  Da das systemeigene Serialisierungsformat des `DataSet` XML ist, handelt es sich um ein hervorragendes Medium zum Verschieben von Daten zwischen den Ebenen der Architektur. Somit ist das `DataSet` eine optimale Wahl für das Remoting von Daten und Schemakontext zu und von einem XML\-Webdienst.  Weitere Informationen finden Sie unter [XML\-Dokumente und XML\-Daten](../../../../docs/standard/data/xml/index.md).  
  
## Siehe auch  
 [Übersicht über ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)