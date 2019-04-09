---
title: < = (kleiner als oder gleich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 7c46da5c-fa09-4d90-adcc-c7e1b769d8e6
ms.openlocfilehash: 9e5a61cb68895982344eadec083a697bdaff54e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193953"
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
 `true` Wenn der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist; andernfalls `false`.  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der Vergleichsoperator <= verwendet, um zu ermitteln, ob der linke Ausdruck kleiner oder gleich dem rechten Ausdruck ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS_OR_EQUALS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less_or_equals)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
