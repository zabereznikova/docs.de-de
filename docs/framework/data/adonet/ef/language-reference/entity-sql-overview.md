---
title: Übersicht über Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 4d7db9c6a7aaeef900132663a5b0aa7420afe668
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251072"
---
# <a name="entity-sql-overview"></a>Übersicht über Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine SQL-ähnliche Sprache, die die Abfrage von konzeptionellen Modellen in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht. Konzeptionelle Modelle stellen Daten als Entitäten und Beziehungen dar [!INCLUDE[esql](../../../../../../includes/esql-md.md)] und ermöglichen es Ihnen, diese Entitäten und Beziehungen in einem Format abzufragen, das den Benutzern, die SQL verwendet haben, vertraut ist.  
  
 Das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen. Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben. Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen. Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung. Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.  
  
 Neben dem EntityClient-Anbieter ermöglicht [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] die Verwendung von [!INCLUDE[esql](../../../../../../includes/esql-md.md)], um Abfragen für ein konzeptionelles Modell auszuführen und Daten als stark typisierte CLR-Objekte zurückzugeben, die Instanzen von Entitätstypen sind. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../working-with-objects.md).  
  
 In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Unterschiede zwischen Entity SQL und Transact-SQL](how-entity-sql-differs-from-transact-sql.md)  
  
 [Entity SQL-Kurzreferenz](entity-sql-quick-reference.md)  
  
 [Typsystem](type-system-entity-sql.md)  
  
 [Typdefinitionen](type-definitions-entity-sql.md)  
  
 [Konstruktionstypen](constructing-types-entity-sql.md)  
  
 [Zwischenspeichern von Abfrageplänen](query-plan-caching-entity-sql.md)  
  
 [Namespaces](namespaces-entity-sql.md)  
  
 [Identifiers (Bezeichner)](identifiers-entity-sql.md)  
  
 [Parameter](parameters-entity-sql.md)  
  
 [Variablen](variables-entity-sql.md)  
  
 [Nicht unterstützte Ausdrücke](unsupported-expressions-entity-sql.md)  
  
 [Literale](literals-entity-sql.md)  
  
 [NULL-Literale und Typrückschluss](null-literals-and-type-inference-entity-sql.md)  
  
 [Eingabezeichensatz](input-character-set-entity-sql.md)  
  
 [Abfrageausdrücke](query-expressions-entity-sql.md)  
  
 [Funktionen](functions-entity-sql.md)  
  
 [Operatorrangfolge](operator-precedence-entity-sql.md)  
  
 [Paging](paging-entity-sql.md)  
  
 [Vergleichssemantik](comparison-semantics-entity-sql.md)  
  
 [Zusammenstellen verschachtelter Entity SQL-Abfragen](composing-nested-entity-sql-queries.md)  
  
 [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Entity SQL Language (Entity SQL-Sprache)](entity-sql-language.md)
- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](csdl-ssdl-and-msl-specifications.md)
