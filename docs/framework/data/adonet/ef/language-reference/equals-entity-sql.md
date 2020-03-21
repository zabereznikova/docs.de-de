---
title: = (Gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 948eb588-7080-4046-bb48-633b007393bf
ms.openlocfilehash: 101dccd40e9197c7cf0795ccb80ded367676842d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150311"
---
# <a name="-equals-entity-sql"></a>= (Gleich) (Entity SQL)
Überprüft zwei Ausdrücke auf Gleichheit.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
expression = expression  
-- or
expression == expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Beliebiger gültiger Ausdruck. Beide Ausdrücke müssen implizit konvertierbare Datentypen besitzen.  
  
## <a name="result-types"></a>Ergebnistypen  
 `true` , wenn der linke Ausdruck gleich dem rechten Ausdruck ist, andernfalls `false`.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Operator "==" ist äquivalent zum Operator "=".  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator "=" verwendet, um zwei Ausdrücke auf Gleichheit zu überprüfen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-sql[DP EntityServices Concepts#EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#equals)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
