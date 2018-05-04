---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 3008939798af98d449ec14e4d774ebc1a6e0d89d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="set-entity-sql"></a>SET (Entity SQL)
Der SET-Ausdruck wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
SET ( expression )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Der Mengenausdruck `SET(c)` ist logisch äquivalent zur folgenden SELECTAnweisung:  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Finden Sie unter [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) Informationen zur Rangfolge der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Mengenoperatoren.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den SET-Ausdruck, um eine Auflistung von Objekten in eine Menge zu konvertieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
