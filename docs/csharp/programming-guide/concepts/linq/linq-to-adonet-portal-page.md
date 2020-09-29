---
title: LINQ to ADO.NET (Portalseite)
description: Mit LINQ to ADO.NET können Sie in ADO.NET mithilfe des Programmiermodells von LINQ jedes aufzählbare Objekt abfragen. Hier erfahren Sie mehr über die drei LINQ-Technologien in ADO.NET.
ms.date: 07/20/2015
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
ms.openlocfilehash: 6d8a6a7a90abe12dacec9a017f80c1ff1abd46f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202551"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Portalseite)

Mit LINQ to ADO.NET können Sie in ADO.NET mithilfe des LINQ-Programmiermodells (Language Integrated Query) jedes aufzählbare Objekt abfragen.  
  
> [!NOTE]
> Die LINQ to ADO.NET-Dokumentation befindet sich im Abschnitt „ADO.NET“ des .NET Framework SDK: [LINQ und ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).  
  
 Es gibt drei separate ADO.NET LINQ-Technologien (Language Integrated Query): LINQ to DataSet, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] und LINQ to Entities. LINQ to DataSet ermöglicht umfangreichere, optimierte Abfragen von <xref:System.Data.DataSet>. [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] ermöglicht es Ihnen, SQL Server-Datenbankschemas direkt abzufragen, und mit LINQ to Entities können Sie ein Entity Data Model abfragen.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  

 <xref:System.Data.DataSet> ist eine der am häufigsten verwendeten Komponenten in ADO.NET und ein Schlüsselelement des getrennten Programmiermodells, auf dem ADO.NET aufgebaut ist. Trotz seiner Bedeutung sind die Abfragefunktionen des <xref:System.Data.DataSet> begrenzt.  
  
 Mit LINQ to DataSet können Sie umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> integrieren, indem Sie die gleiche Abfragefunktionalität verwenden, die für viele andere Datenquellen verfügbar ist.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  

 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] stellt eine Laufzeitinfrastruktur zum Verwalten relationaler Daten als Objekte bereit. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Ergebnisse zurück in Objekte, die Sie bearbeiten können.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bietet Unterstützung für gespeicherte Prozeduren und benutzerdefinierte Funktionen in der Datenbank sowie für die Vererbung im Objektmodell.  
  
 Weitere Informationen finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  

 Durch das Entity Data Model werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die LINQ-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Dies wird auch als LINQ to Entities bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ und ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Language Integrated Query (LINQ) (C#)](./index.md)
