---
title: System.TimeSpan-Methoden
ms.date: 03/30/2017
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
ms.openlocfilehash: dd693a64550293d6894e1d2abc3f651a53fc17fc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126944"
---
# <a name="systemtimespan-methods"></a>System.TimeSpan-Methoden
Die Elementunterstützung für <xref:System.TimeSpan?displayProperty=nameWithType> ist stark abhängig von den verwendeten Versionen von .NET Framework und Microsoft SQL Server.  
  
 Wenn eine Methode, ein Operator oder eine Eigenschaft nicht unterstützt wird, kann das Element von LINQ to SQL nicht für die Ausführung auf dem SQL-Server übersetzt werden. Diese Elemente können im Code möglicherweise dennoch verwendet werden. Sie müssen jedoch ausgewertet werden, bevor die Abfrage in Transact-SQL übersetzt wird oder nachdem die Ergebnisse aus der Datenbank abgerufen wurden.  
  
## <a name="previous-limitations"></a>Einschränkungen vorheriger Versionen  
 Wenn LINQ to SQL mit Versionen von .NET Framework verwendet wird, die älter sind als .NET Framework 3.5 SP1, können die Datenbankfelder von SQL Server nicht <xref:System.TimeSpan?displayProperty=nameWithType>-Werten zugeordnet werden. Dennoch werden Operationen für <xref:System.TimeSpan> unterstützt, da <xref:System.TimeSpan>-Werte von <xref:System.DateTime>-Subtraktionen zurückgegeben oder als Literal oder gebundene Variable in einen Ausdruck integriert werden können.  
  
## <a name="supported-systemtimespan-member-support"></a>Unterstützte Unterstützung der System.TimeSpan-Wert-Elemente

 Die folgenden von LINQ to SQL unterstützten Methoden, Operatoren und Eigenschaften sind für LINQ to SQL-Abfragen verfügbar. Nach der Zuordnung im Objektmodell oder in der externen Mappingdatei können Sie mit LINQ to SQL viele der <xref:System.TimeSpan?displayProperty=nameWithType>-Elemente in Ihren LINQ to SQL-Abfragen aufrufen.  
  
|Unterstützte <xref:System.TimeSpan>-Methoden|Unterstützte <xref:System.TimeSpan>-Operatoren|Unterstützte <xref:System.TimeSpan>-Eigenschaften|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<xref:System.TimeSpan.MinValue>|  
  
> [!NOTE]
>  Zum Zuordnen von <xref:System.TimeSpan?displayProperty=nameWithType>-Elementen zu einer SQL `TIME`-Spalte mit LINQ to SQL ist .NET Framework 3.5 SP1 oder höher erforderlich. Der SQL-`TIME`-Datentyp ist nur in Microsoft SQL Server 2008 und höher verfügbar.  
  
### <a name="addition-and-subtraction"></a>Addition und Subtraktion  
 Vom CLR-<xref:System.TimeSpan?displayProperty=nameWithType>-Typ werden Additionen und Subtraktionen unterstützt, vom SQL-`TIME`-Typ jedoch nicht. Ihre LINQ to SQL-Abfragen werden bei Additionen und Subtraktionen daher Fehler verursachen, wenn sie dem SQL-`TIME`-Typ zugeordnet sind. Sie finden weitere Informationen zum Arbeiten mit SQL Datums- und Uhrzeittypen in [SQL-CLR-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [SQL-CLR-Typenzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
- [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
