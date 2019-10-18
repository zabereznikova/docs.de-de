---
title: SET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319357"
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
  
## <a name="remarks"></a>Hinweise  
 Der Mengenausdruck `SET(c)` ist logisch äquivalent zur folgenden SELECTAnweisung:  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` ist einer der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren. Alle [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Mengenoperatoren werden von links nach rechts ausgewertet. Weitere [Informationen](except-entity-sql.md) zu den [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Mengen Operatoren finden Sie unter.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den SET-Ausdruck, um eine Auflistung von Objekten in eine Menge zu konvertieren. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren unter Gewusst [wie: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt](../how-to-execute-a-query-that-returns-primitivetype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
