---
title: < = (kleiner als oder gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 91dc97b848fd67bad2ecb7abb8f16d72e80c2c4c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250472"
---
# <a name="-less-than-or-equal-to-entity-sql"></a>\<= (Kleiner als oder gleich) (Entity SQL)
Vergleicht zwei Ausdrücke, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression <= expression  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Jeder gültige Ausdruck. Beide Ausdrücke müssen implizit konvertierbare Datentypen sein.  
  
## <a name="result-types"></a>Ergebnistypen  
 `true` , wenn der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist, andernfalls `false`.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator <= verwendet, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
