---
title: < (kleiner als) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
ms.openlocfilehash: 389c50a697c90dadb075369fe696f7382caf3cff
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161918"
---
# <a name="-less-than-entity-sql"></a>\< (Kleiner als) (Entity SQL)

Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
expression < expression  
```  
  
## <a name="arguments"></a>Argumente  

 `expression`  
 Jeder gültige Ausdruck. Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen.  
  
## <a name="result-types"></a>Ergebnistypen  

 `true` , wenn der linke Ausdruck kleiner als der rechte Ausdruck ist, andernfalls `false`.  
  
## <a name="example"></a>Beispiel  

 In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator < verwendet, um zu ermitteln, ob der linke Ausdruck kleiner als der rechte Ausdruck ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#LESS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#less)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
