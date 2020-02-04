---
title: Übersicht über
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: d5dc9cf7081c6876118914a0b95853a5a7ca5e57
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980339"
---
# <a name="adonet-overview"></a>Übersicht über ADO.NET
ADO.NET stellt konsistenten Zugriff auf Datenquellen wie SQL Server und XML sowie auf Datenquellen bereit, die durch OLE DB und ODBC verfügbar gemacht werden. Verbraucheranwendungen mit Datenfreigabe können mit ADO.NET eine Verbindung mit diesen Datenquellen herstellen und die enthaltenen Daten abrufen, verarbeiten und aktualisieren.  
  
 ADO.NET trennt den Datenzugriff von der Datenbearbeitung in einzelne Komponenten, die separat oder zusammen verwendet werden können. ADO.NET schließt .NET Framework-Datenanbieter zum Verbinden mit einer Datenbank, zum Ausführen von Befehlen und zum Abrufen von Ergebnissen ein. Diese Ergebnisse werden entweder direkt verarbeitet oder in einem ADO.NET-<xref:System.Data.DataSet>-Objekt platziert, um sie dem Benutzer, kombiniert mit Daten aus mehreren Quellen, bei Bedarf verfügbar zu machen oder um sie an eine andere Ebene zu übergeben. Das `DataSet`-Objekt kann auch unabhängig von einem .NET Framework-Datenanbieter verwendet werden, um Daten zu verwalten, die für die Anwendung lokal sind oder aus einer XML-Datenquelle beschafft werden.  
  
 Die ADO.NET-Klassen befinden sich in System.Data.dll und werden in die in System.Xml.dll vorhandenen XML-Klassen integriert. Beispielcode, der eine Verbindung mit einer Datenbank herstellt, Daten aus der Datenbank abruft und diese Daten dann in einem Konsolenfenster anzeigt, finden Sie unter [ADO.NET Code examples (Beispiele für Codebeispiele](ado-net-code-examples.md)).  
  
 ADO.NET enthält Funktionen für Entwickler von verwaltetem Code. Diese Funktionen sind mit den ADO-Funktionen (ActiveX Data Objects) vergleichbar, die von COM-Entwicklern (Component Object Model) verwendet werden. Wir empfehlen, für den Zugriff auf Daten in Ihren .NET-Anwendungen statt ADO ADO.NET zu verwenden.  
  
 ADO.NET stellt die direkteste Methode des Datenzugriffs innerhalb von .NET Framework bereit. Eine Abstraktion auf höherer Ebene, die es Anwendungen ermöglicht, anstelle des zugrunde liegenden Speicher Modells mit einem konzeptionellen Modell zu arbeiten, finden Sie unter [ADO.NET Entity Framework](./ef/index.md).  
  
 **Datenschutzerklärung**: "System. Data. dll", System. Data. Design. dll, System. Data. OracleClient. dll, System. Data. SQLXML. dll, System. Data. Linq. dll, System. Data. SqlServerCe. dll und System. Data. DataSetExtensions. dll-Assemblys unterscheiden sich nicht zwischen den privaten Daten eines Benutzers und nicht privaten Daten.  Durch diese Assemblys werden keine privaten Daten von Benutzern gesammelt, gespeichert oder transportiert. Es ist aber möglich, dass Drittanbieteranwendungen, die diese Assemblys verwenden, private Daten von Benutzern sammeln, speichern oder transportieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ADO.NET-Architektur](ado-net-architecture.md)  
 Stellt eine Übersicht der Architektur und der Komponenten von ADO.NET bereit.  
  
 [Optionen und Richtlinien der ADO.NET-Technologie](ado-net-technology-options-and-guidelines.md)  
 Beschreibt die in Entity Data Platform enthaltenen Produkte und Technologien.  
  
 [LINQ und ADO.NET](linq-and-ado-net.md)  
 Beschreibt, wie LINQ (Language Integrated Query) in ADO.NET implementiert wird, und bietet Links zu entsprechenden Themen.  
  
 [.NET Framework-Datenanbieter](data-providers.md)  
 Stellt eine Übersicht über den Entwurf der .NET Framework-Datenanbieter und der .NET Framework-Datenanbieter bereit, die in ADO.NET eingeschlossen sind.  
  
 [ADO.NET-DataSets](ado-net-datasets.md)  
 Stellt eine Übersicht zum `DataSet`-Entwurf und den Komponenten bereit.  
  
 [Parallele Ausführung in ADO.NET](side-by-side-execution.md)  
 Erläutert die Unterschiede zwischen den einzelnen ADO.NET-Versionen und deren Auswirkung auf die parallele Ausführung und die Anwendungskompatibilität.  
  
 [ADO.NET-Codebeispiele](ado-net-code-examples.md)  
 Enthält Codebeispiele, die zum Abrufen von Daten ADO.NET-Datenanbieter verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Neues in ADO.NET](whats-new.md)  
 Enthält eine Einführung in neue Funktionen von ADO.NET.  
  
 [Sichern von ADO.NET-Anwendungen](securing-ado-net-applications.md)  
 Beschreibt sichere Programmiermethoden für ADO.NET.  
  
 [Datentypzuordnungen in ADO.NET](data-type-mappings-in-ado-net.md)  
 Beschreibt Datentypzuordnungen zwischen .NET Framework-Datentypen und den .NET Framework-Datenanbietern.  
  
 [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)  
 Beschreibt das Herstellen von Verbindungen mit einer Datenquelle, das Abrufen von Daten und das Ändern von Daten. Dazu gehören auch `DataReaders` und `DataAdapters`.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](index.md)
- [Zugreifen auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)
