---
title: Übersicht über Entity SQL
ms.date: 03/30/2017
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
ms.openlocfilehash: 100d616462cd76e1dde8fc855787ec3118842fc8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606176"
---
# <a name="entity-sql-overview"></a>Übersicht über Entity SQL
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine SQL-ähnliche Sprache, die die Abfrage von konzeptionellen Modellen in [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] ermöglicht. Konzeptionelle Modelle stellen Daten als Entitäten und Beziehungen dar und [!INCLUDE[esql](../../../../../../includes/esql-md.md)] können Sie Abfragen, die Entitäten und Beziehungen in einem Format, vertraut ist, die SQL verwendet haben.  
  
 Das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] arbeitet mit speicherspezifischen Datenanbietern, um generisches [!INCLUDE[esql](../../../../../../includes/esql-md.md)] in speicherspezifische Abfragen zu übersetzen. Der EntityClient-Anbieter bietet die Möglichkeit, einen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Befehl für ein Entitätenmodell auszuführen und vielfältige Datentypen, einschließlich skalarer Ergebnisse, Resultsets und Objektdiagrammen, zurückzugeben. Wenn Sie <xref:System.Data.EntityClient.EntityCommand>-Objekte erstellen, können Sie den Namen einer gespeicherten Prozedur oder den Text einer Abfrage angeben, indem Sie der [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Eigenschaft eine <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType>-Abfragezeichenfolge zuweisen. Der <xref:System.Data.EntityClient.EntityDataReader> stellt die Ergebnisse eines für ein EDM ausgeführten <xref:System.Data.EntityClient.EntityCommand> zur Verfügung. Zum Ausführen des Befehls, das den <xref:System.Data.EntityClient.EntityDataReader> zurückgibt, rufen Sie <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A> auf.  
  
 Neben dem EntityClient-Anbieter ermöglicht [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] die Verwendung von [!INCLUDE[esql](../../../../../../includes/esql-md.md)], um Abfragen für ein konzeptionelles Modell auszuführen und Daten als stark typisierte CLR-Objekte zurückzugeben, die Instanzen von Entitätstypen sind. Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 In diesem Abschnitt werden konzeptionelle Informationen zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bereitgestellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Unterschiede zwischen Entity SQL und Transact-SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [Entity SQL-Kurzreferenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [Typsystem](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [Typdefinitionen](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [Konstruktionstypen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [Zwischenspeichern von Abfrageplänen](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [Namespaces](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [Identifiers (Bezeichner)](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [Parameter](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [Variablen](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [Nicht unterstützte Ausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [Literale](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [NULL-Literale und Typrückschluss](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [Eingabezeichensatz](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [Abfrageausdrücke](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [Operatorrangfolge](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [Vergleichssemantik](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [Zusammenstellen verschachtelter Entity SQL-Abfragen](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [Strukturierte Typen, die NULL-Werte zulassen](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Entity SQL Language (Entity SQL-Sprache)](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
