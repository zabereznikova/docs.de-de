---
title: ROW (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 06da96e8-55d7-486c-991a-4e514d837ff9
ms.openlocfilehash: b83020601373ba93124dfb24308dd048bfa3c6dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319390"
---
# <a name="row-entity-sql"></a>ROW (Entity SQL)
Erstellt anonyme, strukturell typisierte Datensätze aus einem oder mehreren Werten.  
  
## <a name="syntax"></a>Syntax  
  
```  
ROW ( expression [ AS alias ] [,...] )  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein gültiger Abfrageausdruck, der einen Wert zum Erstellen eines Zeilentyps zurückgibt.  
  
 `alias`  
 Gibt einen Alias für den in einem Zeilentyp angegebenen Wert an. Wenn kein Alias angegeben wird, generiert [!INCLUDE[esql](../../../../../../includes/esql-md.md)] mithilfe der Aliasgenerierungsregeln von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen Alias.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeilentyp.  
  
## <a name="remarks"></a>Hinweise  
 Zeilenkonstruktoren werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] zur Erstellung anonymer, strukturell typisierter Datensätze aus einem oder mehreren Werten verwendet. Beim Ergebnistyp eines Zeilenkonstruktors handelt es sich um einen Zeilentyp, dessen Feldtypen den Typen der zur Erstellung der Zeile verwendeten Werten entsprechen. Im folgenden Ausdruck wird beispielsweise ein Wert vom Typ `Record(a int, b string, c int)`erstellt.  
  
```  
ROW(1 AS a, "abc" AS b, a+34 AS c)  
```  
  
 Wenn für einen Ausdruck in einem Zeilenkonstruktor kein Alias angegeben ist, wird vom Entity Framework ein Alias generiert. Weitere Informationen finden Sie im Abschnitt "Regeln für das Aliasing" im Thema [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md) .  
  
 Die folgenden Regeln gelten für Ausdrucksaliasing in einem Zeilenkonstruktor:  
  
-   Ausdrücke in einem Zeilenkonstruktor können nicht auf andere Aliase im gleichen Konstruktor verweisen.  
  
-   Zwei Ausdrücke im gleichen Zeilenkonstruktor können nicht über den gleichen Alias verfügen.  
  
 Weitere Informationen zu Abfragekonstruktoren finden Sie unter [Typen erstellen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md).  
  
## <a name="example"></a>Beispiel  
 In der folgenden Entity SQL-Abfrage wird der ROW-Operator zur Erstellung anonymer, strukturell typisierter Datensätze verwendet. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ROW](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#row)]  
  
## <a name="see-also"></a>Siehe auch

- [Konstruktionstypen](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Typdefinitionen](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
