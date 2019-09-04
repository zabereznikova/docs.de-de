---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: 8e02d2d3171c9f08333ecef7ee22e65100bdf822
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250094"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Erstellt eine Instanz einer Multimenge aus einer Liste von Werten. Alle Werte im MULTISET-Konstruktor müssen von einem kompatiblen `T`-Typ sein. Leere Multimengenkonstruktoren sind nicht zulässig.  
  
## <a name="syntax"></a>Syntax  
  
```  
MULTISET ( expression [{, expression }] )  
or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Eine beliebige Liste gültiger Werte.  
  
## <a name="return-value"></a>Rückgabewert  
 Eine Auflistung vom Typ Multiset\<T >.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt drei Arten von Konstruktoren bereit: Zeilenkonstruktoren, Objektkonstruktoren und Multimengenkonstruktoren (oder Auflistungen). Weitere Informationen finden Sie unter [Konstruieren von Typen](constructing-types-entity-sql.md).  
  
 Der Multimengenkonstruktor erstellt eine Instanz einer Multimenge aus einer Liste von Werten. Alle Werte im Konstruktor müssen von einem kompatiblen Typ sein.  
  
 Zum Beispiel erstellt der folgende Ausdruck eine Multimenge von ganzen Zahlen.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> Unterstützte Multiset-Literale werden nur unterstützt, wenn eine Wrapping-Multimenge über ein einzelnes Multiset-Element verfügt. Beispiel: `{{1, 2, 3}}`. Wenn die Wrapping-Multimenge über mehrere Multimengenelemente verfügt, werden geschachtelte (z. B. `{{1, 2}, {3, 4}}`) Multimengenliterale nicht unterstützt.  
  
## <a name="example"></a>Beispiel  
 Die Folgende Entity SQL-Abfrage verwendet den MULTISET-Operator, um eine Instanz einer Multimenge aus einer Liste mit Werten zu erstellen. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#MULTISET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#multiset)]  
  
## <a name="see-also"></a>Siehe auch

- [Konstruktionstypen](constructing-types-entity-sql.md)
- [Entity SQL-Referenz](entity-sql-reference.md)
