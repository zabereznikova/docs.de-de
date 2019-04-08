---
title: ISNULL (Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 894d3ab91623aa4246bf7735fb1b7d04e066825a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072635"
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
 `true` Wenn `expression` gibt null ist, andernfalls `false`.  
  
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
 Die folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage verwendet den IS NOT NULL-Operator, um festzustellen, ob ein Abfrageausdruck den Wert nicht null ist. Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell. Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:  
  
1.  Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:  
  
 [!code-csharp[DP EntityServices Concepts 2#ISNULL](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#isnull)]  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
