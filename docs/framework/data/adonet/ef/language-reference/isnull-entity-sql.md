---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: d54c350196ad1ef7cfafa6d931d9d1ad8f267177
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250554"
---
# <a name="isnull-entity-sql"></a>ISNULL (Entity SQL)
Ermittelt, ob ein Abfrageausdruck den Wert NULL hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>Argumente  
 `expression`  
 Ein gültiger Abfrageausdruck. Dieser darf keine Auflistung sein oder über Auflistungsmember oder einen Datensatztyp mit Auflistungstypeigenschaften verfügen.  
  
 NICHT  
 Negiert das EDM.Boolean-Ergebnis von IS NULL.  
  
## <a name="return-value"></a>Rückgabewert  
 `true` wenn `expression` NULL zurückgibt, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `IS NULL`, um zu ermitteln, ob das Element einer äußeren Verknüpfung den Wert NULL hat:  
  
```  
select c   
      from LOB.Customers as c left outer join LOB.Orders as o   
                              on c.ID = o.CustomerID    
      where o is not null and o.OrderQuantity = @x  
```  
  
 Verwenden Sie `IS NULL`, um zu ermitteln, ob ein Member über einen tatsächlichen Wert verfügt:  
  
```  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 In der folgenden Tabelle wird das Verhalten von `IS NULL` für einige Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|-------------|--------------|  
|null IS NULL|Gibt `true`zurück.|  
|TREAT (null AS EntityType) IS NULL|Gibt `true`zurück.|  
|TREAT (null AS ComplexType) IS NULL|Löst einen Fehler aus.|  
|TREAT (null AS RowType) IS NULL|Löst einen Fehler aus.|  
|EntityType IS NULL|Gibt einen `true` oder `false`zurück.|  
|ComplexType IS NULL|Löst einen Fehler aus.|  
|RowType IS NULL|Löst einen Fehler aus.|  
  
## <a name="example"></a>Beispiel  
 In der [!INCLUDE[esql](../../../../../../includes/esql-md.md)] folgenden-Abfrage wird der is not NULL-Operator verwendet, um zu bestimmen, ob ein Abfrage Ausdruck nicht NULL ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1. Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.  
  
2. Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](entity-sql-reference.md)
