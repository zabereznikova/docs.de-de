---
title: Kanonische Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b80eeedc67678d703664eb705408a72b7e4a2274
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
 [Aggregieren von kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 Erläutert die kanonischen Aggregatfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Kanonische Mathematikfunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 Erläutert die kanonischen mathematischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Kanonische Zeichenfolgefunktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 Erläutert die kanonischen Zeichenfolgenfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Kanonische Funktionen für Datum und Uhrzeit](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 Erläutert die kanonischen Datums- und Uhrzeitfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Bitweise kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 Erläutert die kanonischen bitweisen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Räumliche Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 Erläutert die räumlichen kanonischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].  
  
 [Andere kanonischen Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Konzeptionelles Modell mit SQLServer kanonische Funktionen zuordnen](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [Benutzerdefinierte Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
