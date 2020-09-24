---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 2ac7db5b22ad21eb152788b6c6d6a8e65c1f6a7b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169634"
---
# <a name="set-entity-sql"></a>SET (Entity SQL)

Der SET-Ausdruck wird verwendet, um eine Auflistung von Objekten in eine Menge zu konvertieren, indem eine neue Auflistung zurückgegeben wird, aus der alle doppelten Elemente entfernt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung zurückgibt.  
  
## <a name="remarks"></a>Bemerkungen  

 Der Mengenausdruck `SET(c)` ist logisch äquivalent zur folgenden SELECTAnweisung:  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Siehe [mit Ausnahme](except-entity-sql.md) der Rang folgen Informationen für die Mengen [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Operatoren.  
  
## <a name="example"></a>Beispiel  

 Die folgende Entity SQL-Abfrage verwendet den SET-Ausdruck, um eine Auflistung von Objekten in eine Menge zu konvertieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
