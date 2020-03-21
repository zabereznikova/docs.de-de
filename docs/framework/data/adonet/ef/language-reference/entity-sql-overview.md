---
title: Übersicht über Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 880b81f2b6d4c4b893d28c919490f88dfb2a42e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150375"
---
# <a name="entity-sql-overview"></a>Übersicht über Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]ist eine SQL-ähnliche Sprache, mit der Sie konzeptionelle Modelle im Entity Framework abfragen können. Konzeptionelle Modelle stellen Daten als [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Entitäten und Beziehungen dar und ermöglichen es Ihnen, diese Entitäten und Beziehungen in einem Format abzufragen, das denjenigen vertraut ist, die SQL verwendet haben.  

 Entity Framework arbeitet mit speicherspezifischen Datenanbietern [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zusammen, um generische Abfragen in speicherspezifische Abfragen zu übersetzen. Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben. Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen. Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung. Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.  
  
 Zusätzlich zum EntityClient-Anbieter können Sie [!INCLUDE[esql](../../../../../../includes/esql-md.md)] mit Entity Framework Abfragen für ein konzeptionelles Modell ausführen und Daten als stark typisierte CLR-Objekte zurückgeben, die Instanzen von Entitätstypen sind. Weitere Informationen finden Sie unter [Arbeiten mit Objekten](../working-with-objects.md).  
  
 In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Unterschiede zwischen Entity SQL und Transact-SQL](how-entity-sql-differs-from-transact-sql.md)  
  
 [Entity SQL-Kurzreferenz](entity-sql-quick-reference.md)  
  
 [Typensystem](type-system-entity-sql.md)  
  
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
  
 [Functions](functions-entity-sql.md)  
  
 [Operatorrangfolge](operator-precedence-entity-sql.md)  
  
 [Paging](paging-entity-sql.md)  
  
 [Vergleichssemantik](comparison-semantics-entity-sql.md)  
  
 [Zusammenstellen verschachtelter Entity SQL-Abfragen](composing-nested-entity-sql-queries.md)  
  
 [Strukturierte Typen, die NULL-Werte zulassen](nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Entity SQL-Sprache](entity-sql-language.md)
- [CSDL-, SSDL- und MSL-Spezifikationen](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
