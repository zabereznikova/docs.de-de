---
title: "Migrationsüberlegungen (Entity Framework)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 038cf7ad9f6004f785fe35eccf38185272b0ed37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="migration-considerations-entity-framework"></a>Migrationsüberlegungen (Entity Framework)
Das [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework bietet für eine vorhandene Anwendung mehrere Vorteile. Einer der wichtigsten dieser Vorteile ist die Möglichkeit, mithilfe eines konzeptionellen Modells von der Anwendung verwendete Datenstrukturen vom Schema in der Datenquelle zu trennen. Damit können Änderungen am Speichermodell oder an der Datenquelle selbst vorgenommen werden, ohne dass entsprechende Änderungen an der Anwendung notwendig werden. Weitere Informationen zu den Vorteilen der Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], finden Sie unter [Übersicht über Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) und [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Nutzen der Vorteile der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], können Sie eine vorhandene Anwendung zum Migrieren der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Einige Aufgaben müssen für alle migrierten Anwendungen durchgeführt werden. Diesen gemeinsamen Aufgaben gehören das Aktualisieren der Anwendung für die Verwendung der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 Servicepack 1 (SP1), Modelle zu definieren und zuordnen und Konfiguration des Entity Framework. Beim Migrieren einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] sind weitere Überlegungen erforderlich. Diese Überlegungen sind vom Typ der migrierten Anwendung sowie von deren spezifischer Funktion abhängig. In diesem Thema werden Informationen zur Auswahl der besten Methode zur Aktualisierung einer vorhandenen Anwendung bereitgestellt.  
  
## <a name="general-migration-considerations"></a>Allgemeine Überlegungen zur Migration  
 Folgende Aspekte sollten bei der Migration einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] beachtet werden:  
  
-   Jede Anwendung, verwendet der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1 kann zu Entity Framework migriert werden, solange der Datenanbieter für die Datenquelle, die von der Anwendung verwendet wird, Entity Framework unterstützt.  
  
-   Entity Framework unterstützt möglicherweise nicht alle Funktionen eines Datenquellenanbieters, auch wenn dieser Anbieter das Entity Framework unterstützt.  
  
-   Bei einer großen oder komplexen Anwendung, ist es nicht erforderlich, die gesamte Anwendung gleichzeitig zu Entity Framework zu migrieren. Jedoch muss jede Komponente der Anwendung, die das Entity Framework nicht verwendet, geändert werden, wenn sich die Datenquelle ändert.  
  
-   Die von Entity Framework verwendete Datenanbieterverbindung kann mit anderen Komponenten der Anwendung gemeinsam verwendet werden, da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]-Datenanbieter für den Zugriff auf die Datenquelle verwendet. Beispielsweise wird der SqlClient-Anbieter vom Entity Framework für den Zugriff auf eine SQL Server-Datenbank verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Allgemeine Migrationsaufgaben  
 Der Pfad zum Migrieren einer bestehenden Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist sowohl vom Typ der Anwendung, als auch von der bestehenden Datenzugriffsstrategie abhängig. Sie müssen jedoch immer die folgenden Aufgaben ausführen, wenn Sie eine vorhandene Anwendung zum [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] migrieren.  
  
> [!NOTE]
>  Diese Aufgaben werden automatisch ausgeführt, wenn Sie die Entity Data Model-Tools beginnend mit [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] verwenden. Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
1.  Aktualisieren der Anwendung.  
  
     Ein Projekt mit einer früheren Version erstellt [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] und [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] muss aktualisiert werden, damit [!INCLUDE[vsOrcas](../../../../../includes/vsorcas-md.md)] SP1 und dem [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1.  
  
2.  Definieren der Modelle und Zuordnungen.  
  
     Die Modell- und Zuordnungsdateien definieren Entitäten im konzeptionellen Modell, Strukturen in der Datenquelle, wie Tabellen, gespeicherte Prozeduren und Ansichten, und die Zuordnung zwischen den Entitäten und Datenquellenstrukturen. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren der Modell- und Zuordnen von Dateien](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a).  
  
     Die im Speichermodell definierten Typen müssen mit dem Namen der Objekte in der Datenquelle übereinstimmen. Wenn die vorhandene Anwendung Daten als Objekte bereitstellt, müssen Sie sicherstellen, dass die Entitäten und Eigenschaften, die im konzeptionellen Modell definiert werden, mit den Namen der bestehenden Datenklassen und Eigenschaften übereinstimmen. Weitere Informationen finden Sie unter [wie: anpassen, modellieren und Zuordnen von Dateien zur Verwendung von benutzerdefinierten Objekten](http://msdn.microsoft.com/en-us/bb40c4db-0121-4e45-a167-8fb06707a708).  
  
    > [!NOTE]
    >  Der Entity Data Model-Designer wird verwendet, um Entitäten im konzeptionellen Modell umzubenennen, damit sie mit bestehenden Objekten übereinstimmen. Weitere Informationen finden Sie unter [Entity Data Model Designer](http://msdn.microsoft.com/en-us/4ccd7ad6-b934-4f7c-82a0-cfd2d4a95faf).  
  
3.  Definieren der Verbindungszeichenfolge.  
  
     Beim Ausführen von Abfragen für ein konzeptionelles Modell verwendet [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] eine speziell formatierte Verbindungszeichenfolge. Diese Verbindungszeichenfolge kapselt Informationen über die Modell- und Zuordnungsdateien und die Verbindung zur Datenquelle. Weitere Informationen finden Sie unter [wie: Definieren der Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Konfigurieren des [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]-Projekts.  
  
     Dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Projekt müssen Verweise auf [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]-Assemblys und die Modell- und Zuordnungsdateien hinzugefügt werden. Sie können diese Mappingdateien dem Projekt hinzufügen, um zu gewährleisten, dass sie mit der Anwendung am in der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Überlegungen für Anwendungen mit vorhandenen Objekten  
 Ab [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Version 4 unterstützt [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] "einfache alte" CLR-Objekte (POCO), auch Dauerhaftigkeit ignorierende Objekte genannt. In den meisten Fällen können vorhandene Objekte bei nur geringfügigen Änderungen mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] arbeiten. Weitere Informationen finden Sie unter [arbeiten mit POCO-Entitäten](http://msdn.microsoft.com/en-us/5e0fb82a-b6d1-41a1-b37b-c12db61629d3). Sie können auch eine Anwendung zum Migrieren der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und verwenden Sie die Datenklassen, die von den Entity Framework-Tools generiert werden. Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Überlegungen für Anwendungen, die ADO.NET-Anbieter verwenden  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]Anbieter, z.B. SqlClient, ermöglichen es Ihnen, Abfragen eine Datenquelle, um Tabellendaten zurückzugeben. Daten können auch geladen werden, in eine [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] DataSet. Die folgende Liste enthält Überlegungen zum Aktualisieren einer Anwendung, die einen vorhandenen [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]-Anbieter verwendet:  
  
 Anzeigen von Tabellendaten mit einem Datenleser.  
 Es empfiehlt sich, eine [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen mithilfe des EntityClient-Anbieters und das zurückgegebene <xref:System.Data.EntityClient.EntityDataReader> Objekt. Dies ist nur erforderlich, wenn Ihre Anwendung Tabellen mithilfe eines Datenlesers anzeigt und nicht die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bereitgestellten Funktionen für die Materialisierung von Daten in Objekte, die Nachverfolgung von Änderungen und die Durchführung von Aktualisierungen benötigt. Sie können den vorhandenen Datenzugriffscode, der die Datenquelle aktualisiert, weiterhin verwenden. Sie können jedoch auch die vorhandene Verbindung verwenden, auf die über die <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A>-Eigenschaft der <xref:System.Data.EntityClient.EntityConnection> zugegriffen wird. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
 Arbeiten mit DataSets.  
 Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] stellt viele der Funktionen aus, die von Datasets, einschließlich dauerhafte Speicherung, änderungsnachverfolgung, Datenbindung und Serialisieren von Objekten als XML-Daten. Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Wenn die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet die Funktionalität des Datasets, die von der Anwendung benötigte, weiterhin profitieren Sie von den Vorteilen von LINQ-Abfragen mithilfe von [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]. Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Überlegungen für Anwendungen, die Daten an Steuerelemente binden  
 Die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] können Sie die Daten in einer Datenquelle, z. B. ein DataSet oder ein kapseln [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Datenquellensteuerelement, und klicken Sie dann Benutzeroberflächenelemente an diese Datensteuerelemente gebunden. Die folgende Liste enthält Überlegungen zu Bindungssteuerelementen für Entity Framework-Daten.  
  
 Binden von Daten an Steuerelemente.  
 Wenn Sie das konzeptionelle Modell Abfragen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] gibt die Daten als Objekte, die Instanzen von Entitätstypen sind. Diese Objekte können direkt an Steuerelemente gebunden werden, und diese Bindung unterstützt Aktualisierungen. Dies bedeutet, die Änderungen an Daten in einem Steuerelement, z. B. eine Zeile in eine <xref:System.Windows.Forms.DataGridView>automatisch abrufen in der Datenbank gespeichert bei der <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> Methode wird aufgerufen.  
  
 Wenn Ihre Anwendung die Ergebnisse einer Abfrage auflistet, um Daten in einem <xref:System.Windows.Forms.DataGridView> oder einem anderen die Datenbindung unterstützenden Steuerelement anzuzeigen, können Sie die Anwendung ändern, um das Steuerelement an das Ergebnis eines <xref:System.Data.Objects.ObjectQuery%601> zu binden.  
  
 Weitere Informationen finden Sie unter [Binden von Objekten an Steuerelemente](http://msdn.microsoft.com/en-us/2fd34855-929b-4303-a91e-4bb69d958f2b).  
  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]-Datenquellensteuerelemente.  
 Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält ein Datenquellensteuerelement, das die Datenbindung in vereinfacht [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] -Webanwendungen. Weitere Informationen finden Sie unter [Entity Framework-Datenquellensteuerelement](http://msdn.microsoft.com/library/1f09af00-9578-4744-a029-765710a3c83f).  
  
## <a name="other-considerations"></a>Andere Überlegungen  
 Im Folgenden werden Überlegungen angestellt, die möglicherweise bei der Migration bestimmter Anwendungstypen zu Entity Framework von Bedeutung sind.  
  
 Anwendungen, die Datendienste verfügbar machen.  
 Webdienste und Anwendungen, die auf Windows Communication Foundation (WCF) beruhen, machen Daten aus einer zugrunde liegenden Datenquelle verfügbar, indem sie ein XML-Nachrichtenformat für Anforderung/Antwort verwenden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt die Serialisierung von Entitätsobjekten mit binärer Serialisierung, XML-Serialisierung oder WCF-Datenvertragsserialisierung. Sowohl binäre als auch WCF-Serialisierung unterstützen die vollständige Serialisierung von Objektdiagrammen. Weitere Informationen finden Sie unter [Erstellen von N-Tier-Anwendungen](http://msdn.microsoft.com/en-us/9439d2ba-6b5f-44e8-be65-8a442d922cbb).  
  
 Anwendungen, die XML-Daten verwenden.  
 Die Objektserialisierung ermöglicht die Erstellung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Datendiensten. Diese Dienste stellen Daten für Anwendungen bereit, die XML-Daten verwenden, z. B. AJAX-basierte Internetanwendungen. Erwägen Sie in diesen Fällen die Verwendung von [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Diese Datendienste basieren auf dem Entity Data Model und Bereitstellen von dynamischen Zugriff auf Entitätsdaten mithilfe von Representational State Transfer (REST) HTTP-Standardaktionen, z. B. GET, PUT und POST. Weitere Informationen finden Sie unter [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt keinen systemeigenen XML-Datentyp. Das bedeutet, dass beim Mapping einer Entität zu einer Tabelle mit einer XML-Spalte die entsprechende Entitätseigenschaft für die XML-Spalte eine Zeichenfolge ist. Objekte können getrennt und als XML serialisiert werden. Weitere Informationen finden Sie unter [Serialisieren von Objekten](http://msdn.microsoft.com/en-us/06c77f9b-5b2e-4c78-b3e3-8c148ba0ea99).  
  
 Wenn die Anwendung das Abfragen von XML-Daten erfordert, können Sie dennoch von den Vorteilen von LINQ-Abfragen profitieren, indem Sie LINQ to XML verwenden. Weitere Informationen finden Sie unter [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).  
  
 Anwendungen, die den Zustand beibehalten.  
 [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)]Webanwendungen müssen häufig den Zustand einer Webseite oder einer benutzersitzung beibehalten. Objekte in einer <xref:System.Data.Objects.ObjectContext> Instanz kann im Ansichtszustand Client oder im Sitzungszustand auf dem Server gespeichert, und später abgerufen und an einem neuen Objektkontext erneut angefügt. Weitere Informationen finden Sie unter [Anfügen und Trennen von Objekten](http://msdn.microsoft.com/en-us/41d5c1ef-1b78-4502-aa10-7e1438d62d23).  
  
## <a name="see-also"></a>Siehe auch  
 [Überlegungen zur Bereitstellung](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)  
 [Entity Framework-Terminologie](../../../../../docs/framework/data/adonet/ef/terminology.md)
