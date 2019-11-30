---
title: Migrationsüberlegungen (Entity Framework)
ms.date: 03/30/2017
ms.assetid: c85b6fe8-cc32-4642-8f0a-dc0e5a695936
ms.openlocfilehash: 168aec6ef369f446cfac22ee5c4361fa06aaf16d
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569438"
---
# <a name="migration-considerations-entity-framework"></a>Migrationsüberlegungen (Entity Framework)
Die ADO.NET-Entity Framework bietet eine Reihe von Vorteilen für eine vorhandene Anwendung. Einer der wichtigsten dieser Vorteile ist die Möglichkeit, mithilfe eines konzeptionellen Modells von der Anwendung verwendete Datenstrukturen vom Schema in der Datenquelle zu trennen. Damit können Änderungen am Speichermodell oder an der Datenquelle selbst vorgenommen werden, ohne dass entsprechende Änderungen an der Anwendung notwendig werden. Weitere Informationen zu den Vorteilen der Verwendung des Entity Framework finden Sie unter [Entity Framework Übersicht](overview.md) und [Entity Data Model](../entity-data-model.md).  
  
 Wenn Sie die Vorteile der Entity Framework nutzen möchten, können Sie eine vorhandene Anwendung zum Entity Framework migrieren. Einige Aufgaben müssen für alle migrierten Anwendungen durchgeführt werden. Zu diesen allgemeinen Aufgaben gehört das Upgrade der Anwendung für die Verwendung des .NET Framework ab Version 3,5 Service Pack 1 (SP1), das Definieren von Modellen und Mapping sowie das Konfigurieren der Entity Framework. Wenn Sie eine Anwendung zum Entity Framework migrieren, sind weitere Überlegungen zu berücksichtigen. Diese Überlegungen sind vom Typ der migrierten Anwendung sowie von deren spezifischer Funktion abhängig. In diesem Thema werden Informationen zur Auswahl der besten Methode zur Aktualisierung einer vorhandenen Anwendung bereitgestellt.  
  
## <a name="general-migration-considerations"></a>Allgemeine Überlegungen zur Migration  
 Die folgenden Überlegungen gelten, wenn Sie eine Anwendung zum Entity Framework migrieren:  
  
- Jede Anwendung, die die .NET Framework ab Version 3,5 SP1 verwendet, kann zum Entity Framework migriert werden, solange der Datenanbieter für die Datenquelle, die von der Anwendung verwendet wird, die Entity Framework unterstützt.  
  
- Entity Framework unterstützt möglicherweise nicht alle Funktionen eines Datenquellenanbieters, auch wenn dieser Anbieter das Entity Framework unterstützt.  
  
- Bei einer großen oder komplexen Anwendung, ist es nicht erforderlich, die gesamte Anwendung gleichzeitig zu Entity Framework zu migrieren. Jedoch muss jede Komponente der Anwendung, die das Entity Framework nicht verwendet, geändert werden, wenn sich die Datenquelle ändert.  
  
- Die vom Entity Framework verwendete Datenanbieter Verbindung kann für andere Teile der Anwendung freigegeben werden, da die Entity Framework mithilfe von ADO.NET-Datenanbietern auf die Datenquelle zugreifen. Beispielsweise wird der SqlClient-Anbieter vom Entity Framework für den Zugriff auf eine SQL Server-Datenbank verwendet. Weitere Informationen finden Sie unter [EntityClient-Anbieter für die Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
## <a name="common-migration-tasks"></a>Allgemeine Migrationsaufgaben  
 Der Pfad zum Migrieren einer vorhandenen Anwendung zum Entity Framework hängt sowohl vom Anwendungstyp als auch von der vorhandenen Datenzugriffs Strategie ab. Beim Migrieren einer vorhandenen Anwendung zum Entity Framework müssen Sie jedoch immer die folgenden Aufgaben ausführen:  
  
> [!NOTE]
> Alle diese Aufgaben werden automatisch ausgeführt, wenn Sie die Entity Data Model Tools verwenden, die mit Visual Studio 2008 beginnen. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
1. Aktualisieren der Anwendung.  
  
     Ein Projekt, das mit einer früheren Version von Visual Studio und dem .NET Framework erstellt wurde, muss aktualisiert werden, damit Visual Studio 2008 SP1 und die .NET Framework ab Version 3,5 SP1 verwendet werden.  
  
2. Definieren der Modelle und Zuordnungen.  
  
     Die Modell- und Zuordnungsdateien definieren Entitäten im konzeptionellen Modell, Strukturen in der Datenquelle, wie Tabellen, gespeicherte Prozeduren und Ansichten, und die Zuordnung zwischen den Entitäten und Datenquellenstrukturen. Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Definieren der Modell-und Mapping-Dateien](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)).  
  
     Die im Speichermodell definierten Typen müssen mit dem Namen der Objekte in der Datenquelle übereinstimmen. Wenn die vorhandene Anwendung Daten als Objekte bereitstellt, müssen Sie sicherstellen, dass die Entitäten und Eigenschaften, die im konzeptionellen Modell definiert werden, mit den Namen der bestehenden Datenklassen und Eigenschaften übereinstimmen. Weitere Informationen finden Sie unter Gewusst [wie: Anpassen von Modellierungs-und Zuordnungs Dateien für die Arbeit mit benutzerdefinierten Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738625(v=vs.100)).  
  
    > [!NOTE]
    > Der Entity Data Model-Designer wird verwendet, um Entitäten im konzeptionellen Modell umzubenennen, damit sie mit bestehenden Objekten übereinstimmen. Weitere Informationen finden Sie unter [Entity Data Model-Designer](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716685(v=vs.100)).  
  
3. Definieren der Verbindungszeichenfolge.  
  
     Der Entity Framework verwendet eine speziell formatierte Verbindungs Zeichenfolge beim Ausführen von Abfragen für ein konzeptionelles Modell. Diese Verbindungszeichenfolge kapselt Informationen über die Modell- und Zuordnungsdateien und die Verbindung zur Datenquelle. Weitere Informationen finden Sie unter Gewusst [wie: Definieren der Verbindungs Zeichenfolge](how-to-define-the-connection-string.md).  
  
4. Konfigurieren Sie das Visual Studio-Projekt.  
  
     Verweise auf Entity Framework Assemblys und die Modell-und Zuordnungsdateien müssen dem Visual Studio-Projekt hinzugefügt werden. Sie können diese Mappingdateien dem Projekt hinzufügen, um zu gewährleisten, dass sie mit der Anwendung am in der Verbindungszeichenfolge angegebenen Speicherort bereitgestellt werden. Weitere Informationen finden Sie unter Vorgehens [Weise: Manuelles Konfigurieren eines Entity Framework Projekts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
## <a name="considerations-for-applications-with-existing-objects"></a>Überlegungen für Anwendungen mit vorhandenen Objekten  
 Beginnend mit dem .NET Framework 4 unterstützt das Entity Framework "Plain Old" CLR Objects (poco), auch Persistenz ignorierende Objekte genannt. In den meisten Fällen können vorhandene Objekte mit dem Entity Framework arbeiten, indem kleinere Änderungen vorgenommen werden. Weitere Informationen finden Sie unter [Arbeiten mit poco-Entitäten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456853(v=vs.100)). Sie können eine Anwendung auch zum Entity Framework migrieren und die Daten Klassen verwenden, die von den Entity Framework Tools generiert werden. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
## <a name="considerations-for-applications-that-use-adonet-providers"></a>Überlegungen für Anwendungen, die ADO.NET-Anbieter verwenden  
 ADO.NET-Anbieter, wie z. b. SqlClient, ermöglichen es Ihnen, eine Datenquelle abzufragen, um Tabellendaten zurückzugeben. Daten können auch in ein ADO.NET-DataSet geladen werden. In der folgenden Liste werden Überlegungen zum Aktualisieren einer Anwendung beschrieben, die einen vorhandenen ADO.NET-Anbieter verwendet:  
  
- Anzeigen von Tabellendaten mit einem Datenleser.  

  Sie können eine [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage mit dem EntityClient-Anbieter ausführen und das zurückgegebene <xref:System.Data.EntityClient.EntityDataReader> Objekt auflisten. Dies geschieht nur, wenn Ihre Anwendung tabellarische Daten mithilfe eines Daten Readers anzeigt und nicht die von der Entity Framework bereitgestellten Funktionen für die Materialisierung von Daten in Objekte, das Nachverfolgen von Änderungen und das vornehmen von Aktualisierungen benötigt. Sie können den vorhandenen Datenzugriffscode, der die Datenquelle aktualisiert, weiterhin verwenden. Sie können jedoch auch die vorhandene Verbindung verwenden, auf die über die <xref:System.Data.EntityClient.EntityConnection.StoreConnection%2A>-Eigenschaft der <xref:System.Data.EntityClient.EntityConnection> zugegriffen wird. Weitere Informationen finden Sie unter [EntityClient-Anbieter für die Entity Framework](entityclient-provider-for-the-entity-framework.md).  
  
- Arbeiten mit DataSets.  

  Der Entity Framework stellt viele der Funktionen bereit, die von DataSet bereitgestellt werden, einschließlich in-Memory-Persistenz, Änderungs Nachverfolgung, Datenbindung und Serialisieren von Objekten als XML-Daten. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](working-with-objects.md).  
  
  Wenn die Entity Framework nicht die Funktionalität des Datasets bereitstellt, das von Ihrer Anwendung benötigt wird, können Sie die Vorteile von LINQ-Abfragen mithilfe LINQ to DataSet weiterhin nutzen. Weitere Informationen finden Sie unter [LINQ to DataSet](../linq-to-dataset.md).  
  
## <a name="considerations-for-applications-that-bind-data-to-controls"></a>Überlegungen für Anwendungen, die Daten an Steuerelemente binden  
 Mit der .NET Framework können Sie Daten in einer Datenquelle Kapseln, z. b. ein DataSet oder ein ASP.NET-Datenquellen-Steuerelement, und dann Benutzeroberflächen Elemente an diese Daten Steuerelemente binden. Die folgende Liste enthält Überlegungen zu Bindungssteuerelementen für Entity Framework-Daten.  
  
- Binden von Daten an Steuerelemente.  

  Wenn Sie das konzeptionelle Modell Abfragen, gibt der Entity Framework die Daten als Objekte zurück, die Instanzen von Entitäts Typen sind. Diese Objekte können direkt an Steuerelemente gebunden werden, und diese Bindung unterstützt Updates. Dies bedeutet, dass Änderungen an Daten in einem Steuerelement, z. b. eine Zeile in einer <xref:System.Windows.Forms.DataGridView>, automatisch in der Datenbank gespeichert werden, wenn die <xref:System.Data.Objects.ObjectContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
  Wenn Ihre Anwendung die Ergebnisse einer Abfrage auflistet, um Daten in einem <xref:System.Windows.Forms.DataGridView> oder einem anderen die Datenbindung unterstützenden Steuerelement anzuzeigen, können Sie die Anwendung ändern, um das Steuerelement an das Ergebnis eines <xref:System.Data.Objects.ObjectQuery%601> zu binden.  
  
  Weitere Informationen finden Sie unter [Binden von Objekten an Steuerelemente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738469(v=vs.100)).  
  
- ASP.NET Datenquellen-Steuerelemente.  

  Die Entity Framework enthält ein Datenquellen-Steuerelement, das zur Vereinfachung der Datenbindung in ASP.NET-Webanwendungen dient. Weitere Informationen finden Sie unter [Übersicht über das EntityDataSource-Webserver Steuer](https://docs.microsoft.com/previous-versions/aspnet/cc488502(v=vs.100))Element.  
  
## <a name="other-considerations"></a>Andere Überlegungen  
 Im Folgenden werden Überlegungen angestellt, die möglicherweise bei der Migration bestimmter Anwendungstypen zu Entity Framework von Bedeutung sind.  
  
- Anwendungen, die Datendienste verfügbar machen.  

  Webdienste und Anwendungen, die auf Windows Communication Foundation (WCF) beruhen, machen Daten aus einer zugrunde liegenden Datenquelle verfügbar, indem sie ein XML-Nachrichtenformat für Anforderung/Antwort verwenden. Der Entity Framework unterstützt die Serialisierung von Entitäts Objekten mithilfe der Binär-, XML-oder WCF-Datenvertragsserialisierung. Sowohl binäre als auch WCF-Serialisierung unterstützen die vollständige Serialisierung von Objektdiagrammen. Weitere Informationen finden Sie unter [Building N-Tier Applications](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896304(v=vs.100)).  
  
- Anwendungen, die XML-Daten verwenden.  

  Die Objektserialisierung ermöglicht es Ihnen, Entity Framework Data Services zu erstellen. Diese Dienste stellen Daten für Anwendungen bereit, die XML-Daten verwenden, z. B. AJAX-basierte Internetanwendungen. In diesen Fällen sollten Sie WCF Data Services verwenden. Diese Datendienste basieren auf dem Entity Data Model und bieten dynamischen Zugriff auf Entitäts Daten mithilfe von standardmäßigen Representational State Transfer (Rest) http-Aktionen wie Get, Put und Post. Weitere Informationen finden Sie unter [WCF Data Services 4.5](../../wcf/index.md).  
  
  Der Entity Framework unterstützt keinen systemeigenen XML-Datentyp. Das bedeutet, dass beim Mapping einer Entität zu einer Tabelle mit einer XML-Spalte die entsprechende Entitätseigenschaft für die XML-Spalte eine Zeichenfolge ist. Objekte können getrennt und als XML serialisiert werden. Weitere Informationen finden Sie unter [Serialisieren von Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738446(v=vs.100)).  
  
  Wenn die Anwendung das Abfragen von XML-Daten erfordert, können Sie dennoch von den Vorteilen von LINQ-Abfragen profitieren, indem Sie LINQ to XML verwenden. Weitere Informationen finden Sie unter [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) oder [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).  
  
- Anwendungen, die den Zustand beibehalten.  

  ASP.NET Webanwendungen müssen den Status einer Webseite oder einer Benutzersitzung häufig beibehalten. Objekte in einer <xref:System.Data.Objects.ObjectContext> Instanz können im Client Ansichts Zustand oder im Sitzungszustand auf dem Server gespeichert und später abgerufen und an einen neuen Objekt Kontext angefügt werden. Weitere Informationen finden Sie unter Anfügen [und trennen von Objekten](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896271(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [Überlegungen zur Bereitstellung](deployment-considerations.md)
- [Entity Framework-Terminologie](terminology.md)
