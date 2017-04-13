---
title: "OFTYPE (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 6d259ca7-bbf0-40f8-a154-181d25c0d67e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# OFTYPE (Entity SQL)
Gibt eine Auflistung der Objekte von einem Abfrageausdruck eines bestimmten Typs zurück.  
  
## Syntax  
  
```  
  
OFTYPE (expression, [ONLY] test_type)  
```  
  
## Argumente  
 `expression`  
 Jeder gültige Abfrageausdruck, der eine Auflistung von Objekten zurückgibt.  
  
 `test_type`  
 Der Typ, dessen Übereinstimmung mit jedem von `expression` zurückgegebenen Objekt getestet wird. Der Typ muss mit einem Namespace qualifiziert werden.  
  
## Rückgabewert  
 Eine Auflistung von Objekten vom Typ `test_type`, von einem Basistyp oder von einem von `test_type` abgeleiteten Typ. Wenn ONLY angegeben wird, werden nur Instanzen des `test_type` oder eine leere Auflistung zurückgegeben.  
  
## Hinweise  
 Ein `OFTYPE`\-Ausdruck stellt einen Typausdruck dar, der angegeben wird, um einen Typtest für jedes Element einer Auflistung durchzuführen.  Der `OFTYPE`\-Ausdruck liefert eine neue Auflistung des angegebenen Typs, die nur die zu diesem Typ oder einem seiner Untertypen äquivalenten Elemente enthält.  
  
 Ein `OFTYPE`\-Ausdruck ist eine Abkürzung des folgenden Abfrageausdrucks:  
  
```  
select value treat(t as T) from ts as t where t is of (T)  
```  
  
 Wenn beispielsweise "Manager" ein Untertyp von "Employee" \(Mitarbeiter\) ist, liefert der folgende Ausdruck nur die Manager aus einer Auflistung der Mitarbeiter:  
  
```  
OfType(employees, NamespaceName.Manager)  
```  
  
 Mithilfe des Typfilters kann eine Auflistung auch umgewandelt werden:  
  
```  
OfType(executives, NamespaceName.Manager)  
```  
  
 Da alle Direktoren Manager sind, enthält die resultierende Auflistung alle Direktoren, auch wenn die Auflistung nun als eine Auflistung von Managern typisiert ist.  
  
 In der folgenden Tabelle wird das Verhalten des `OFTYPE`\-Operators für verschiedene Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|------------|---------------|  
|OFTYPE \(Collection\(EntityType\), \(EntityType\)|Collection\(EntityType\)|  
|OFTYPE\(Collection\(ComplexType\), ComplexType\)|Löst aus|  
|OFTYPE\(Collection\(RowType\), RowType\)|Löst aus|  
  
## Beispiel  
 Die folgende [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfrage verwendet den OFTYPE\-Operator, um eine Auflistung der OnsiteCourse\-Objekte von einer Auflistung von Kursobjekten zurückzugeben. Die Abfrage basiert auf dem [Modell "School"](http://msdn.microsoft.com/de-de/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#OFTYPE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#oftype)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)