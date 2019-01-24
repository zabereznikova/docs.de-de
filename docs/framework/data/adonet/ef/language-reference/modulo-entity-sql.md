---
title: (Modulo) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
ms.openlocfilehash: 543c35c56955fb0a9909fced23357444bc78197a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732595"
---
# <a name="modulo-entity-sql"></a>(Modulo) (Entity SQL)
Gibt den Rest der Division eines Ausdrucks durch einen anderen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a>Argumente  
 `dividend`  
 Der zu dividierende numerische Ausdruck. `dividend` ist jeder gültige Ausdruck eines der numerischen Datentypen.  
  
 `divisor`  
 Der numerische Ausdruck, durch den der Dividend geteilt werden soll. `divisor` ist jeder gültige Ausdruck eines der numerischen Datentypen.  
  
## <a name="result-types"></a>Ergebnistypen  
 Edm.Int32  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "%", um den Rest der Division eines Ausdrucks durch einen anderen zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a>Siehe auch
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
