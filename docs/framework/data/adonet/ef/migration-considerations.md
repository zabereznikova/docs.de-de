---
title: Migrationsüberlegungen (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: 359e373476398bb26f06eb86eb13296ab05d2705
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089886"
---
# <a name="migration-considerations-entity-framework"></a>Migrationsüberlegungen (Entity Framework)
Das [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Entity Framework bietet für eine vorhandene Anwendung mehrere Vorteile. Einer der wichtigsten dieser Vorteile ist die Möglichkeit, mithilfe eines konzeptionellen Modells von der Anwendung verwendete Datenstrukturen vom Schema in der Datenquelle zu trennen. Damit können Änderungen am Speichermodell oder an der Datenquelle selbst vorgenommen werden, ohne dass entsprechende Änderungen an der Anwendung notwendig werden. Weitere Informationen zu den Vorteilen der Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], finden Sie unter [Übersicht über Entity Framework](../../../../../docs/framework/data/adonet/ef/overview.md) und [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Nutzen der Vorteile bei der die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], Sie können eine vorhandene Anwendung Migrieren der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Einige Aufgaben müssen für alle migrierten Anwendungen durchgeführt werden. Diesen gemeinsamen Aufgaben gehören das Aktualisieren der Anwendung zur Verwendung der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 Servicepack 1 (SP1), Definition von Modellen und Zuordnung und Konfiguration des Entity Framework. Beim Migrieren einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] sind weitere Überlegungen erforderlich. Diese Überlegungen sind vom Typ der migrierten Anwendung sowie von deren spezifischer Funktion abhängig. In diesem Thema werden Informationen zur Auswahl der besten Methode zur Aktualisierung einer vorhandenen Anwendung bereitgestellt.  
  
## <a name="general-migration-considerations"></a>Allgemeine Überlegungen zur Migration  
 Folgende Aspekte sollten bei der Migration einer Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] beachtet werden:  
  
-   Jede Anwendung, verwendet der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1 kann zu Entity Framework migriert werden, solange der Datenanbieter für die Datenquelle, die von der Anwendung verwendet wird, Entity Framework unterstützt.  
  
-   Entity Framework unterstützt möglicherweise nicht alle Funktionen eines Datenquellenanbieters, auch wenn dieser Anbieter das Entity Framework unterstützt.  
  
-   Bei einer großen oder komplexen Anwendung, ist es nicht erforderlich, die gesamte Anwendung gleichzeitig zu Entity Framework zu migrieren. Jedoch muss jede Komponente der Anwendung, die das Entity Framework nicht verwendet, geändert werden, wenn sich die Datenquelle ändert.  
  
-   Die von Entity Framework verwendete Datenanbieterverbindung kann mit anderen Komponenten der Anwendung gemeinsam verwendet werden, da [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)][!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]-Datenanbieter für den Zugriff auf die Datenquelle verwendet. Beispielsweise wird der SqlClient-Anbieter vom Entity Framework für den Zugriff auf eine SQL Server-Datenbank verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Allgemeine Migrationsaufgaben  
 Der Pfad zum Migrieren einer bestehenden Anwendung zu [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist sowohl vom Typ der Anwendung, als auch von der bestehenden Datenzugriffsstrategie abhängig. Sie müssen jedoch immer die folgenden Aufgaben ausführen, wenn Sie eine vorhandene Anwendung zum [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] migrieren.  
  
> [!NOTE]
>  Alle diese Aufgaben werden automatisch ausgeführt, wenn Sie die Entity Data Model-Tools beginnend mit Visual Studio 2008 verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
1.  Aktualisieren der Anwendung.  
  
     Ein Projekt mit einer früheren Version von Visual Studio erstellt und die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] muss aktualisiert werden, damit Visual Studio 2008 SP1 und die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab Version 3.5 SP1.  
  
2.  Definieren der Modelle und Zuordnungen.  
  
     Die Modell- und Zuordnungsdateien definieren Entitäten im konzeptionellen Modell, Strukturen in der Datenquelle, wie Tabellen, gespeicherte Prozeduren und Ansichten, und die Zuordnung zwischen den Entitäten und Datenquellenstrukturen. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Definieren Sie das Modell und Zuordnungsdateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).  
  
     Die im Speichermodell definierten Typen müssen mit dem Namen der Objekte in der Datenquelle übereinstimmen. Wenn die vorhandene Anwendung Daten als Objekte bereitstellt, müssen Sie sicherstellen, dass die Entitäten und Eigenschaften, die im konzeptionellen Modell definiert werden, mit den Namen der bestehenden Datenklassen und Eigenschaften übereinstimmen. Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Modellierungs- und Zuordnungsdateien zur Verwendung mit benutzerdefinierten Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100)).  
  
    > [!NOTE]
    >  Der Entity Data Model-Designer wird verwendet, um Entitäten im konzeptionellen Modell umzubenennen, damit sie mit bestehenden Objekten übereinstimmen. Weitere Informationen finden Sie unter [Entity Data Model Designer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3.  Definieren der Verbindungszeichenfolge.  
  
     Beim Ausführen von Abfragen für ein konzeptionelles Modell verwendet [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] eine speziell formatierte Verbindungszeichenfolge. Diese Verbindungszeichenfolge kapselt Informationen über die Modell- und Zuordnungsdateien und die Verbindung zur Datenquelle. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren der Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md).  
  
4.  Konfigurieren Sie Visual Studio-Projekt.  
  
     Verweise auf [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Assemblys und das Modell und die Mapping-Dateien müssen Visual Studio-Projekt hinzugefügt werden. Sie können diese Mappingdateien dem Projekt hinzufügen, um zu gewährleisten, dass sie mit der Anwendung am in der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Konfigurieren eines Entity Framework-Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Überlegungen für Anwendungen mit vorhandenen Objekten  
 Ab [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] Version 4 unterstützt [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] „einfache alte“ CLR-Objekte (POCO), auch Dauerhaftigkeit ignorierende Objekte genannt. In den meisten Fällen können vorhandene Objekte bei nur geringfügigen Änderungen mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] arbeiten. Weitere Informationen finden Sie unter [arbeiten mit POCO-Entitäten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). Sie können auch eine Anwendung Migrieren der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und verwenden Sie die Datenklassen, die von den Entity Framework-Tools generiert werden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Überlegungen für Anwendungen, die ADO.NET-Anbieter verwenden  
 [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] Anbieter, z.B. SqlClient, ermöglichen Sie zum Abfragen einer Datenquelle, um Tabellendaten zurückzugeben. Daten können auch geladen werden, in eine [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)] DataSet. Die folgende Liste enthält Überlegungen zum Aktualisieren einer Anwendung, die einen vorhandenen [!INCLUDE[vstecado](../../../../../includes/vstecado-md.md)]-Anbieter verwendet:  
  
- Anzeigen von Tabellendaten mit einem Datenleser.  

  Es empfiehlt sich, eine [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfragen mithilfe des EntityClient-Anbieters und auflisten über den zurückgegebenen <xref:System.Data.EntityClient.EntityDataReader> Objekt. Dies ist nur erforderlich, wenn Ihre Anwendung Tabellen mithilfe eines Datenlesers anzeigt und nicht die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bereitgestellten Funktionen für die Materialisierung von Daten in Objekte, die Nachverfolgung von Änderungen und die Durchführung von Aktualisierungen benötigt. Sie können den vorhandenen Datenzugriffscode, der die Datenquelle aktualisiert, weiterhin verwenden. Sie können jedoch auch die vorhandene Verbindung verwenden, auf die über die <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A>-Eigenschaft der <xref:System.Data.EntityClient.EntityConnection> zugegriffen wird. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).  
  
- Arbeiten mit DataSets.  

  Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet viele der Datasets, einschließlich dauerhafte Speicherung, gebotenen Funktionen ändern, Überwachung, Datenbindung und Serialisieren von Objekten als XML-Daten. Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
  Wenn die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet keine Funktionen eines Datasets, die von Ihrer Anwendung benötigt, immer noch profitieren Sie von den Vorteilen von LINQ-Abfragen mithilfe von [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)]. Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Überlegungen für Anwendungen, die Daten an Steuerelemente binden  
 Die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] können Sie die Daten in einer Datenquelle, z. B. ein DataSet oder ein kapseln [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Datenquellensteuerelement, und klicken Sie dann Elemente der Benutzeroberfläche an diese Datensteuerelemente gebunden. Die folgende Liste enthält Überlegungen zu Bindungssteuerelementen für Entity Framework-Daten.  
  
- Binden von Daten an Steuerelemente.  

  Wenn Sie das konzeptionelle Modell, Abfragen der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] gibt die Daten als Objekte, die Instanzen von Entitätstypen sind. Diese Objekte können direkt an Steuerelemente gebunden werden, und diese Bindung unterstützt Aktualisierungen. Dies bedeutet, die Änderungen an Daten in einem Steuerelement, z. B. eine Zeile in eine <xref:System.Windows.Forms.DataGridView>automatisch in der Datenbank gespeichert werden, bei der <xref:System.Data.Objects.ObjectContext.SaveChanges%2A> Methode wird aufgerufen.  
  
  Wenn Ihre Anwendung die Ergebnisse einer Abfrage auflistet, um Daten in einem <xref:System.Windows.Forms.DataGridView> oder einem anderen die Datenbindung unterstützenden Steuerelement anzuzeigen, können Sie die Anwendung ändern, um das Steuerelement an das Ergebnis eines <xref:System.Data.Objects.ObjectQuery%601> zu binden.  
  
  Weitere Informationen finden Sie unter [Binden von Objekten an Steuerelemente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Datenquellen-Steuerelemente.  

  Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält ein Datenquellen-Steuerelement die Datenbindung in vereinfacht [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Webanwendungen. Weitere Informationen finden Sie unter [Übersicht über das EntityDataSource-Webserversteuerelement](https://docs.microsoft.com/previous-versions/aspnet/cc488502(v=vs.100)).  
  
## <a name="other-considerations"></a>Andere Überlegungen  
 Im Folgenden werden Überlegungen angestellt, die möglicherweise bei der Migration bestimmter Anwendungstypen zu Entity Framework von Bedeutung sind.  
  
- Anwendungen, die Datendienste verfügbar machen.  

  Webdienste und Anwendungen, die auf Windows Communication Foundation (WCF) beruhen, machen Daten aus einer zugrunde liegenden Datenquelle verfügbar, indem sie ein XML-Nachrichtenformat für Anforderung/Antwort verwenden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt die Serialisierung von Entitätsobjekten mit binärer Serialisierung, XML-Serialisierung oder WCF-Datenvertragsserialisierung. Sowohl binäre als auch WCF-Serialisierung unterstützen die vollständige Serialisierung von Objektdiagrammen. Weitere Informationen finden Sie unter [Erstellen von N-Tier-Anwendungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Anwendungen, die XML-Daten verwenden.  

  Die Objektserialisierung ermöglicht die Erstellung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Datendiensten. Diese Dienste stellen Daten für Anwendungen bereit, die XML-Daten verwenden, z. B. AJAX-basierte Internetanwendungen. Erwägen Sie in diesen Fällen die Verwendung von [!INCLUDE[ssAstoria](../../../../../includes/ssastoria-md.md)]. Diese Datendienste basieren auf dem Entity Data Model und dynamischen Zugriff auf Entitätsdaten mithilfe von standardmäßigen Representational State Transfer (REST) HTTP-Aktionen bieten, z. B. GET, PUT und POST. Weitere Informationen finden Sie unter [WCF Data Services 4.5](../../../../../docs/framework/data/wcf/index.md).  
  
  [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt keinen systemeigenen XML-Datentyp. Das bedeutet, dass beim Mapping einer Entität zu einer Tabelle mit einer XML-Spalte die entsprechende Entitätseigenschaft für die XML-Spalte eine Zeichenfolge ist. Objekte können getrennt und als XML serialisiert werden. Weitere Informationen finden Sie unter [Serialisieren von Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Wenn die Anwendung das Abfragen von XML-Daten erfordert, können Sie dennoch von den Vorteilen von LINQ-Abfragen profitieren, indem Sie LINQ to XML verwenden. Weitere Informationen finden Sie unter [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) oder [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
- Anwendungen, die den Zustand beibehalten.  

  [!INCLUDE[vstecasp](../../../../../includes/vstecasp-md.md)] Webanwendungen müssen häufig den Zustand einer Webseite oder einer Sitzung des Benutzers verwalten. Objekte in einer <xref:System.Data.Objects.ObjectContext> Instanz kann im Ansichtszustand Client oder im Sitzungszustand auf dem Server gespeichert, und später abgerufen und an einem neuen Objektkontext erneut angefügt. Weitere Informationen finden Sie unter [Anfügen und Trennen von Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [Überlegungen zur Bereitstellung](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)
- [Entity Framework-Terminologie](../../../../../docs/framework/data/adonet/ef/terminology.md)
