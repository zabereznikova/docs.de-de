---
title: Kanonische Funktionen
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: fed6e45056e318ec0bf34951097304ef3c98f629
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760933"
---
# <a name="canonical-functions"></a>Kanonische Funktionen
In diesem Abschnitt werden die von allen Datenanbietern unterstützten und in allen Abfragetechnologien verwendbaren kanonischen Funktionen erläutert. Kanonische Funktionen können von Anbietern nicht erweitert werden.  
  
 Diese kanonischen Funktionen werden in die entsprechenden Datenquellenfunktionen der Anbieter übersetzt. Dadurch können Funktionsaufrufe für Datenquellen in einer allgemeinen Form ausgedrückt werden.  
  
 Da diese kanonischen Funktionen datenquellenunabhängig sind, werden die Argument- und Rückgabetypen kanonischer Funktionen in Form von Typen im konzeptionellen Modell definiert. Jedoch werden von einigen Datenquellen möglicherweise nicht alle Typen im konzeptionellen Modell unterstützt.  
  
 Wenn in einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfrage kanonische Funktionen verwendet werden, werden in Datenquellen die entsprechenden Funktionen aufgerufen.  
  
 Für alle kanonischen Funktionen sind das Verhalten bei NULL-Eingaben sowie die Fehlerbedingungen explizit angegeben. Speicheranbieter sollten diesen Vorgaben entsprechend vorgehen. Dieses Verhalten wird vom [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] jedoch nicht erzwungen.  
  
 LINQ-Szenarios, Abfragen für die [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] bei CLR-Methoden den Methoden in der zugrunde liegenden Datenquelle zugeordnet werden. Die CLR-Methoden werden kanonischen Funktionen zugeordnet, sodass bestimmte Methoden unabhängig von der Datenquelle ordnungsgemäß zugeordnet werden.  
  
## <a name="canonical-functions-namespace"></a>Namespace kanonischer Funktionen  
 Der Namespace für kanonische Funktionen ist <xref:System.Data.Metadata.Edm>. Der <xref:System.Data.Metadata.Edm>-Namespace wird in allen Abfragen automatisch eingebunden. Wenn jedoch ein anderer Namespace importiert wird, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion (im <xref:System.Data.Metadata.Edm>-Namespace) enthält, muss der Namespace angegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aggregieren kanonischer Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Erläutert die kanonischen Aggregatfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Mathematische kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Erläutert die kanonischen mathematischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Kanonische Zeichenfolgefunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Erläutert die kanonischen Zeichenfolgenfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Kanonische Funktionen für Datum und Zeit](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Erläutert die kanonischen Datums- und Uhrzeitfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Bitweise kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Erläutert die kanonischen bitweisen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Räumliche Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Erläutert die räumlichen kanonischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Andere kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
