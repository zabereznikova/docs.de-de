---
title: LINQ to ADO.NET (Portalseite)
ms.date: 07/20/2015
ms.assetid: bbbd7c76-2981-4b91-b8d2-437547181f52
ms.openlocfilehash: 850e154b40e69cc655ee1b59161351b0b2898033
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539387"
---
# <a name="linq-to-adonet-portal-page"></a>LINQ to ADO.NET (Portalseite)
LINQ to ADO.NET können Sie jedes aufzählbare Objekt in ADO.NET mithilfe von Abfragen die [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Programmiermodell.  
  
> [!NOTE]
>  Die LINQ to ADO.NET-Dokumentation befindet sich im Abschnitt ADO.NET .NET Framework SDK: [LINQ und ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md).
  
 Es gibt drei separate ADO.NET- [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] Technologien: LINQ to DataSet [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], und LINQ to Entities. LINQ to DataSet bietet umfangreichere, optimierte Abfragen der <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] ermöglicht, die Sie direkt Abfragen von SQL Server-Datenbankschemas und LINQ to Entities ermöglicht Ihnen, ein Entity Data Model abzufragen.  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> ist eine der am häufigsten verwendeten Komponenten in ADO.NET und ein Schlüsselelement des getrennten Programmiermodells, auf dem ADO.NET aufgebaut ist. Trotz seiner Bedeutung sind die Abfragefunktionen des <xref:System.Data.DataSet> begrenzt.  
  
 LINQ to DataSet können Sie umfangreichere Abfragefunktionen in <xref:System.Data.DataSet> mit die gleiche Abfragefunktionalität, die für viele andere Datenquellen verfügbar ist.  
  
 Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] stellt eine Laufzeitinfrastruktur zum Verwalten relationaler Daten als Objekte bereit. In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist. Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] die Ergebnisse zurück in Objekte, die Sie bearbeiten können.  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] bietet Unterstützung für gespeicherte Prozeduren und benutzerdefinierte Funktionen in der Datenbank sowie für die Vererbung im Objektmodell.  
  
 Weitere Informationen finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Durch das Entity Data Model werden relationale Daten als Objekte in der .NET-Umgebung verfügbar gemacht. Dadurch wird die Objektebene zu einem optimalen Ziel für die [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Unterstützung, die es Entwicklern ermöglicht, Abfragen an die Datenbank in der Sprache der Geschäftlogik zu formulieren. Diese Funktion wird als LINQ to Entities bezeichnet. Weitere Informationen Sie unter [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ und ADO.NET](../../../../framework/data/adonet/linq-and-ado-net.md)
- [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)
