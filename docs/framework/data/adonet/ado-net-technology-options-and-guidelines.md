---
title: Technologieoptionen und-Richtlinien
ms.date: 03/30/2017
ms.assetid: c8577281-38e6-4ce5-b036-572039a4c3d8
ms.openlocfilehash: 9be44a5b9c06a310581aee57cdb6a304127f8a12
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980274"
---
# <a name="adonet-technology-options-and-guidelines"></a>Optionen und Richtlinien der ADO.NET-Technologie
Die ADO.NET-Datenplattform ist eine Multiversionsstrategie, die die Menge an erforderlichem Code und den Verwaltungsaufwand reduziert, da Entwickler bei der Programmierung auf konzeptionelle EDMs zurückgreifen können. Diese Plattform enthält das ADO.NET Entity Framework und verwandte Technologien.  
  
## <a name="entity-framework"></a>Entity Framework  
 Das ADO.NET Entity Framework wurde entworfen, um Entwicklern die Möglichkeit zu geben, Anwendungen für den Datenzugriff zu erstellen, indem sie bei der Programmierung auf ein konzeptionelles Anwendungsmodell zugreifen können, anstatt direkt mit einem relationalen Speicherschema zu arbeiten. Das Ziel ist es, die Menge des Codes und den Wartungsaufwand zu verringern, die für datenorientierte Anwendungen erforderlich sind. Weitere Informationen finden Sie unter [ADO.NET Entity Framework](./ef/index.md).  
  
### <a name="entity-data-model-edm"></a>Entity Data Model (EDM)  
 Ein EDM ist eine Entwurfsspezifikation, die Anwendungsdaten als Sätze von Entitäten und Beziehungen definiert. Die Daten dieses Modells unterstützen objektrelationales Mapping und Datenprogrammierbarkeit über Anwendungsgrenzen hinweg.  
  
### <a name="object-services"></a>Objektdienste  
 Object Services ermöglicht den Programmierern die Interaktion mit einem konzeptionellen Modell mithilfe eines Satzes von CLR-Klassen. Diese Klassen können automatisch aus dem konzeptionellen Modell generiert oder unabhängig entwickelt werden, um die Struktur des konzeptionellen Modells widerzuspiegeln. Object Services bietet darüber hinaus Infrastrukturunterstützung für das Entity Framework, indem es verschiedene Dienste wie Zustandsverwaltung, Änderungsnachverfolgung, Identitätsauflösung, Laden von und Navigieren in Beziehungen, Weitergeben von Objektänderungen an Datenbankmodifikationen und Abfrageerstellungsunterstützung für Entity SQL bereitstellt. Weitere Informationen finden Sie unter [Übersicht über Object Services (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
### <a name="linq-to-entities"></a>LINQ to Entities  
 LINQ to Entities ist eine LINQ-Implementierung (Language-Integrated Query), die Entwicklern ermöglicht, stark typisierte Abfragen zu erstellen, die mithilfe von LINQ-Ausdrücken und LINQ-Abfrageoperatoren auf den Objektkontext des Entity Framework angewendet werden. LINQ to Entities ermöglicht Entwicklern den Zugriff auf ein konzeptionelles Modell mit einer sehr flexiblen objektrelationalen Zuordnung über Microsoft SQL Server und Datenbanken von Drittanbietern. Weitere Informationen finden Sie unter [LINQ to Entities](./ef/language-reference/linq-to-entities.md).  
  
### <a name="entity-sql"></a>Entity SQL  
 Entity SQL ist eine textbasierte Abfragesprache, die zur Interaktion mit einem Entity Data Model entwickelt wurde. Entity SQL ist ein SQL-Dialekt, der Abfragekonstrukte für übergeordnete Modellkonzepte wie Vererbung, komplexe Typen und explizite Beziehungen enthält. Entwickler können Entity SQL auch direkt in Verbindung mit Object Services verwenden. Weitere Informationen finden Sie unter [Entity SQL Sprache](./ef/language-reference/entity-sql-language.md).  
  
### <a name="entityclient"></a>EntityClient  
 EntityClient ist ein neuer .NET Framework-Datenanbieter, der zur Interaktion mit einem Entity Data Model verwendet wird. EntityClient folgt dem Muster des .NET Framework-Datenanbieters, indem es <xref:System.Data.EntityClient.EntityConnection> und <xref:System.Data.EntityClient.EntityCommand> Objekte verfügbar macht, die einen <xref:System.Data.EntityClient.EntityDataReader> zurückgeben. EntityClient verwendet die Entity SQL-Programmiersprache und stellt flexibles Mapping für speicherspezifische Datenanbieter bereit. Weitere Informationen finden Sie unter [EntityClient-Anbieter für die Entity Framework](./ef/entityclient-provider-for-the-entity-framework.md).  
  
### <a name="entity-data-model-tools"></a>Entity Data Model-Tools  
 Das Entity Framework stellt Befehlszeilentools, Assistenten und Designer bereit, um die Erstellung von EDM-Anwendungen zu erleichtern. Das EntityDataSource-Steuerelement unterstützt Datenbindungsszenarien auf Grundlage des EDM. Die Programmieroberfläche des EntityDataSource-Steuerelements ist anderen Steuerelementen für Datenquellen in Visual Studio ähnlich. Weitere Informationen finden Sie unter [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 LINQ to SQL ist eine Implementierung der objektrelationalen Zuordnung, mit deren Hilfe Sie eine SQL Server-Datenbank unter Verwendung von .NET Framework-Klassen modellieren können. Mit LINQ to SQL können Sie die Datenbank mittels LINQ abfragen sowie Daten in der Datenbank aktualisieren, einfügen und löschen. LINQ to SQL unterstützt Transaktionen, Sichten und gespeicherte Prozeduren und bietet so eine einfache Möglichkeit zum Integrieren von Datenvalidierungs- und Geschäftslogikregeln in das Datenmodell. Mit dem Object Relational Designer (O/R-Designer) können Sie die Entitätsklassen und Zuordnungen modellieren, die auf Objekten in einer Datenbank basieren. Weitere Informationen finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
## <a name="wcf-data-services"></a>WCF Data Services  
 WCF Data Services stellt Datendienste im Internet oder in einem Intranet bereit. Die Daten werden gemäß den Spezifikationen des Entity Data Model in Entitäten und Beziehungen strukturiert. Die in diesem Modell bereitgestellten Daten sind durch das Standard-HTTP-Protokoll adressierbar. Weitere Informationen finden Sie unter [WCF Data Services 4.5](../wcf/index.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über ADO.NET](ado-net-overview.md)
- [Neues in ADO.NET](whats-new.md)
