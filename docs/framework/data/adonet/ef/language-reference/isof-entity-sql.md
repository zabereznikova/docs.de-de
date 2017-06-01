---
title: "ISOF (Entity SQL) | Microsoft Docs"
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
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# ISOF (Entity SQL)
Ermittelt, ob der Typ eines Ausdrucks vom angegebenen Typ oder einem seiner Untertypen ist.  
  
## Syntax  
  
```  
  
expression IS [ NOT ] OF ( [ ONLY ] type)  
```  
  
## Argumente  
 `expression`  
 Ein gültiger Abfrageausdruck, dessen Typ bestimmt werden soll.  
  
 NOT  
 Negiert das EDM.Boolean\-Ergebnis von IS OF.  
  
 ONLY  
 Legt fest, dass von IS OF nur dann `true` zurückgegeben wird, wenn `expression` vom Typ `type` und nicht von einem seiner Untertypen ist.  
  
 `type`  
 Der Typ, dessen Übereinstimmung mit dem Typ von `expression` überprüft werden soll. Der Typ muss mit einem Namespace qualifiziert werden.  
  
## Rückgabewert  
 `true`, wenn `expression` vom Typ "T" und "T" entweder ein Basistyp oder ein von `type` abgeleiteter Typ ist. NULL, wenn `expression` zur Laufzeit den Wert NULL hat, andernfalls `false`.  
  
## Hinweise  
 Die Ausdrücke `expression IS NOT OF (type)`  und `expression IS NOT OF (ONLY type)` entsprechen syntaktisch `NOT (expression IS OF (type))` bzw. `NOT (expression IS OF (ONLY type))`.  
  
 In der folgenden Tabelle wird das Verhalten des `IS OF`\-Operators für einige typische und weniger typische Muster dargestellt. Alle Ausnahmen werden von der Clientseite ausgelöst, bevor der Anbieter aufgerufen wird:  
  
|Muster|Verhalten|  
|------------|---------------|  
|null IS OF \(EntityType\)|Löst aus|  
|null IS OF \(ComplexType\)|Löst aus|  
|null IS OF \(RowType\)|Löst aus|  
|TREAT \(null AS EntityType\) IS OF \(EntityType\)|Gibt DBNull zurück.|  
|TREAT \(null AS ComplexType\) IS OF \(ComplexType\)|Löst aus|  
|TREAT \(null AS RowType\) IS OF \(RowType\)|Löst aus|  
|EntityType IS OF \(EntityType\)|Gibt true\/false zurück|  
|ComplexType IS OF \(ComplexType\)|Löst aus|  
|RowType IS OF \(RowType\)|Löst aus|  
  
## Beispiel  
 In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]\-Abfrage wird der IS OF\-Operator verwendet, um den Typ eines Abfrageausdrucks zu ermitteln. Danach wird mithilfe des TREAT\-Operators ein Objekt des Typs "Course" in eine Auflistung von Objekten des Typs "OnsiteCourse" umgewandelt. Die Abfrage basiert auf dem [Modell "School"](http://msdn.microsoft.com/de-de/859a9587-81ea-4a45-9bc0-f8d330e1adac).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)