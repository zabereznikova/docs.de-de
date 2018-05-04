---
title: '- (Negativ) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 5d1726be6a4a59891646d05b344f59962d548c75
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="--negative-entity-sql"></a>- (Negativ) (Entity SQL)
Gibt den negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
- expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck mit einem numerischen Datentyp.  
  
## <a name="result-types"></a>Ergebnistypen  
 Der Datentyp von `expression`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `expression` ein Typ ohne Vorzeichen ist, ist der Ergebnistyp der Typ mit Vorzeichen, der dem Typ von `expression`am nächsten kommt. Wenn z. B. `expression` vom Typ "Byte" ist, wird ein Wert vom Typ "Int16" zurückgegeben.  
  
## <a name="example"></a>Beispiel  
 Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "-", um den negativen Wert eines numerischen Ausdrucks zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
