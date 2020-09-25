---
title: '- Negative (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 71749dab073fade854c2a494841e3f6b408ebd1d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204410"
---
# <a name="--negative-entity-sql"></a>- (Negativ) (Entity SQL)

Gibt den negativen Wert eines numerischen Ausdrucks zurück.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Jeder gültige Ausdruck mit einem numerischen Datentyp.  
  
## <a name="result-types"></a>Ergebnistypen  

 Der Datentyp von `expression`.  
  
## <a name="remarks"></a>Bemerkungen  

 Wenn `expression` ein Typ ohne Vorzeichen ist, ist der Ergebnistyp der Typ mit Vorzeichen, der dem Typ von `expression`am nächsten kommt. Wenn z. B. `expression` vom Typ "Byte" ist, wird ein Wert vom Typ "Int16" zurückgegeben.  
  
## <a name="example"></a>Beispiel  

 Die folgende Entity SQL-Abfrage verwendet den arithmetischen Operator "-", um den negativen Wert eines numerischen Ausdrucks zurückzugeben. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
