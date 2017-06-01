---
title: "Migrationsaspekte (Entity Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Migrationsaspekte (Entity Framework)
Das [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework bietet für eine vorhandene Anwendung mehrere Vorteile.  Einer der wichtigsten dieser Vorteile ist die Möglichkeit, mithilfe eines konzeptionellen Modells von der Anwendung verwendete Datenstrukturen vom Schema in der Datenquelle zu trennen.  Damit können Änderungen am Speichermodell oder an der Datenquelle selbst vorgenommen werden, ohne dass entsprechende Änderungen an der Anwendung notwendig werden.  Weitere Informationen zu den Vorteilen der Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] finden Sie unter [Übersicht über das Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) und [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Um von den Vorteilen von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] zu profitieren, können vorhandene Anwendungen zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] migriert werden.  Einige Aufgaben müssen für alle migrierten Anwendungen durchgeführt werden.  Zu diesen gemeinsamen Aufgaben gehören das Aktualisieren der Anwendung zur Verwendung von [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 Service Pack 1 \(SP1\), die Definition von Modellen und Zuordnungen und die Konfiguration des Entity Framework.  Beim Migrieren einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] sind weitere Überlegungen erforderlich.  Diese Überlegungen sind vom Typ der migrierten Anwendung sowie von deren spezifischer Funktion abhängig.  In diesem Thema werden Informationen zur Auswahl der besten Methode zur Aktualisierung einer vorhandenen Anwendung bereitgestellt.  
  
## Allgemeine Überlegungen zur Migration  
 Folgende Aspekte sollten bei der Migration einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] beachtet werden:  
  
-   Jede Anwendung, die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1 verwendet, kann zu Entity Framework migriert werden, solange der Datenanbieter für die Datenquelle, die bei der Anwendung verwendet wird, Entity Framework unterstützt.  
  
-   Entity Framework unterstützt möglicherweise nicht alle Funktionen eines Datenquellenanbieters, auch wenn dieser Anbieter das Entity Framework unterstützt.  
  
-   Bei einer großen oder komplexen Anwendung, ist es nicht erforderlich, die gesamte Anwendung gleichzeitig zu Entity Framework zu migrieren.  Jedoch muss jede Komponente der Anwendung, die das Entity Framework nicht verwendet, geändert werden, wenn sich die Datenquelle ändert.  
  
-   Die von Entity Framework verwendete Datenanbieterverbindung kann mit anderen Komponenten der Anwendung gemeinsam verwendet werden, da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Datenanbieter für den Zugriff auf die Datenquelle verwendet.  Beispielsweise wird der SqlClient\-Anbieter vom Entity Framework für den Zugriff auf eine SQL Server\-Datenbank verwendet.  Weitere Informationen finden Sie unter [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## Allgemeine Migrationsaufgaben  
 Der Pfad zum Migrieren einer bestehenden Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist sowohl vom Typ der Anwendung, als auch von der bestehenden Datenzugriffsstrategie abhängig.  Sie müssen jedoch immer die folgenden Aufgaben ausführen, wenn Sie eine vorhandene Anwendung zum [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] migrieren.  
  
> [!NOTE]
>  Diese Aufgaben werden automatisch ausgeführt, wenn Sie die Entity Data Model\-Tools beginnend mit [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] verwenden.  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
1.  Aktualisieren der Anwendung.  
  
     Ein Projekt, das unter Verwendung einer früheren Version von [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] und dem [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] erstellt wurde, muss aktualisiert werden, damit [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 und [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1 verwendet werden können.  
  
2.  Definieren der Modelle und Zuordnungen.  
  
     Die Modell\- und Zuordnungsdateien definieren Entitäten im konzeptionellen Modell, Strukturen in der Datenquelle, wie Tabellen, gespeicherte Prozeduren und Ansichten, und die Zuordnung zwischen den Entitäten und Datenquellenstrukturen.  Weitere Informationen finden Sie unter [How to: Manually Define the Model and Mapping Files](http://msdn.microsoft.com/de-de/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  
  
     Die im Speichermodell definierten Typen müssen mit dem Namen der Objekte in der Datenquelle übereinstimmen.  Wenn die vorhandene Anwendung Daten als Objekte bereitstellt, müssen Sie sicherstellen, dass die Entitäten und Eigenschaften, die im konzeptionellen Modell definiert werden, mit den Namen der bestehenden Datenklassen und Eigenschaften übereinstimmen.  Weitere Informationen finden Sie unter [How to: Customize Modeling and Mapping Files to Work with Custom Objects](http://msdn.microsoft.com/de-de/bb40c4db-0121-4e45-a167-8fb06707a708).  
  
    > [!NOTE]
    >  Der Entity Data Model\-Designer wird verwendet, um Entitäten im konzeptionellen Modell umzubenennen, damit sie mit bestehenden Objekten übereinstimmen.  Weitere Informationen finden Sie unter [Entity Data Model Designer](http://msdn.microsoft.com/de-de/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  
  
3.  Definieren der Verbindungszeichenfolge.  
  
     Beim Ausführen von Abfragen für ein konzeptionelles Modell verwendet [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] eine speziell formatierte Verbindungszeichenfolge.  Diese Verbindungszeichenfolge kapselt Informationen über die Modell\- und Zuordnungsdateien und die Verbindung zur Datenquelle.  Weitere Informationen finden Sie unter [Vorgehensweise: Definieren der Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Konfigurieren des [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]\-Projekts.  
  
     Dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Projekt müssen Verweise auf [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]\-Assemblys und die Modell\- und Zuordnungsdateien hinzugefügt werden.  Sie können diese Mappingdateien dem Projekt hinzufügen, um zu gewährleisten, dass sie mit der Anwendung am in der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden.  Weitere Informationen finden Sie unter [How to: Manually Configure an Entity Framework Project](http://msdn.microsoft.com/de-de/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
## Überlegungen für Anwendungen mit vorhandenen Objekten  
 Ab [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Version 4 unterstützt [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] "einfache alte" CLR\-Objekte \(POCO\), auch Dauerhaftigkeit ignorierende Objekte genannt.  In den meisten Fällen können vorhandene Objekte bei nur geringfügigen Änderungen mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] arbeiten.  Weitere Informationen finden Sie unter [Working with POCO Entities](http://msdn.microsoft.com/de-de/5e0fb82a-b6d1-41a1-b37b-c12db61629d3). Sie können auch eine Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] migrieren und die Datenklassen verwenden, die von den Entity Framework\-Tools generiert werden.  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
## Überlegungen für Anwendungen, die ADO.NET\-Anbieter verwenden  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Anbieter, z.B. SqlClient, ermöglichen das Abfragen einer Datenquelle, um Tabellendaten zurückzugeben.  Daten können auch in ein [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-DataSet geladen werden.  Die folgende Liste enthält Überlegungen zum Aktualisieren einer Anwendung, die einen vorhandenen [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]\-Anbieter verwendet:  
  
 Anzeigen von Tabellendaten mit einem Datenleser.  
 Es empfiehlt sich, eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfrage mithilfe des EntityClient\-Anbieters auszuführen und das zurückgegebene <xref:System.Data.EntityClient.EntityDataReader>\-Objekt aufzulisten.  Dies ist nur erforderlich, wenn Ihre Anwendung Tabellen mithilfe eines Datenlesers anzeigt und nicht die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bereitgestellten Funktionen für die Materialisierung von Daten in Objekte, die Nachverfolgung von Änderungen und die Durchführung von Aktualisierungen benötigt. Sie können den vorhandenen Datenzugriffscode, der die Datenquelle aktualisiert, weiterhin verwenden. Sie können jedoch auch die vorhandene Verbindung verwenden, auf die über die <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A>\-Eigenschaft der <xref:System.Data.EntityClient.EntityConnection> zugegriffen wird.  Weitere Informationen finden Sie unter [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 Arbeiten mit DataSets.  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] stellt viele der Funktionen bereit, die durch DataSet bereitgestellt werden, einschließlich dauerhafte Speicherung, Änderungsnachverfolgung, Datenbindung und das Serialisieren von Objekten als XML\-Daten.  Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Wenn [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] von Ihrer Anwendung benötigte Funktionen von DataSet nicht bereitstellt, können Sie dennoch von den Vorteilen von LINQ\-Abfragen profitieren, indem Sie [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] verwenden.  Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## Überlegungen für Anwendungen, die Daten an Steuerelemente binden  
 Mit [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] können Daten in Datenquellen gekapselt werden, etwa als DataSet oder [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]\-Datenquellenkontrolle, und anschließend können Benutzeroberflächenelemente an diese Datensteuerelemente gebunden werden.  Die folgende Liste enthält Überlegungen zu Bindungssteuerelementen für Entity Framework\-Daten.  
  
 Binden von Daten an Steuerelemente.  
 Wenn das konzeptionelle Modell abgefragt wird, gibt [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] die Daten als Objekte zurück, die Instanzen von Entitätstypen sind.  Diese Objekte können direkt an Steuerelemente gebunden werden, und diese Bindung unterstützt Aktualisierungen. Das bedeutet, dass Änderungen an Daten in einem Steuerelement, z.B. eine Zeile in einem <xref:System.Windows.Forms.DataGridView>, automatisch in der Datenbank gespeichert werden, wenn die <xref:System.Data.Objects.ObjectContext.SaveChanges%2A>\-Methode aufgerufen wird.  
  
 Wenn Ihre Anwendung die Ergebnisse einer Abfrage auflistet, um Daten in einem <xref:System.Windows.Forms.DataGridView> oder einem anderen die Datenbindung unterstützenden Steuerelement anzuzeigen, können Sie die Anwendung ändern, um das Steuerelement an das Ergebnis eines <xref:System.Data.Objects.ObjectQuery%601> zu binden.  
  
 Weitere Informationen finden Sie unter [Binding Objects to Controls](http://msdn.microsoft.com/de-de/2fd34855-929b-4303-a91e-4bb69d958f2b).  
  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]\-Datenquellensteuerelemente.  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält ein Datenquellensteuerelement, das entworfen wurde, um die Datenbindung in [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]\-Webanwendungen zu vereinfachen.  Weitere Informationen finden Sie unter [Entity Framework\-Datenquellensteuerelement](../Topic/EntityDataSource%20Web%20Server%20Control%20Overview.md).  
  
## Andere Überlegungen  
 Im Folgenden werden Überlegungen angestellt, die möglicherweise bei der Migration bestimmter Anwendungstypen zu Entity Framework von Bedeutung sind.  
  
 Anwendungen, die Datendienste verfügbar machen.  
 Webdienste und Anwendungen, die auf Windows Communication Foundation \(WCF\) beruhen, machen Daten aus einer zugrunde liegenden Datenquelle verfügbar, indem sie ein XML\-Nachrichtenformat für Anforderung\/Antwort verwenden.  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt die Serialisierung von Entitätsobjekten mit binärer Serialisierung, XML\-Serialisierung oder WCF\-Datenvertragsserialisierung.  Sowohl binäre als auch WCF\-Serialisierung unterstützen die vollständige Serialisierung von Objektdiagrammen.  Weitere Informationen finden Sie unter [Building N\-Tier Applications](http://msdn.microsoft.com/de-de/9439d2ba-6b5f-44e8-be65-8a442d922cbb).  
  
 Anwendungen, die XML\-Daten verwenden.  
 Die Objektserialisierung ermöglicht die Erstellung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]\-Datendiensten.  Diese Dienste stellen Daten für Anwendungen bereit, die XML\-Daten verwenden, z. B. AJAX\-basierte Internetanwendungen.  Erwägen Sie in diesen Fällen die Verwendung von [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)].  Diese Datendienste beruhen auf dem Entity Data Model und stellen einen dynamischen Zugriff auf Entitätsdaten bereit, indem sie Representational State Transfer \(REST\)\-HTTP\-Standardaktionen, z. B. GET, PUT und POST, verwenden.  Weitere Informationen finden Sie unter [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt keinen systemeigenen XML\-Datentyp.  Das bedeutet, dass beim Mapping einer Entität zu einer Tabelle mit einer XML\-Spalte die entsprechende Entitätseigenschaft für die XML\-Spalte eine Zeichenfolge ist.  Objekte können getrennt und als XML serialisiert werden.  Weitere Informationen finden Sie unter [Serializing Objects](http://msdn.microsoft.com/de-de/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99).  
  
 Wenn die Anwendung das Abfragen von XML\-Daten erfordert, können Sie dennoch von den Vorteilen von LINQ\-Abfragen profitieren, indem Sie LINQ to XML verwenden.  Weitere Informationen finden Sie unter [LINQ to XML](../../../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
 Anwendungen, die den Zustand beibehalten.  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]\-Webanwendungen müssen häufig den Zustand einer Webseite oder einer Benutzersitzung beibehalten.  Objekte in einer <xref:System.Data.Objects.ObjectContext>\-Instanz, können im Clientansichtszustand oder im Sitzungszustand auf dem Server gespeichert werden und später abgerufen und einem neuen Objektkontext erneut angefügt werden.  Weitere Informationen finden Sie unter [Attaching and Detaching Objects](http://msdn.microsoft.com/de-de/41d5c1ef-1b78-4502-aa10-7e1438d62d23).  
  
## Siehe auch  
 [Überlegungen zur Bereitstellung](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)   
 [Entity Framework\-Terminologie](../../../../../docs/framework/data/adonet/ef/terminology.md)