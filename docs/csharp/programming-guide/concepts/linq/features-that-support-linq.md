---
title: "C# Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], features supporting LINQ"
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# C# Features That Support LINQ
Der folgende Abschnitt gibt eine Einführung in die neuen Sprachkonstrukte in C\# 3.0.  Obwohl diese neuen Funktionen bis zu einem gewissen Grad alle mit [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen verwendet werden, sind sie nicht auf [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] beschränkt und können in jedem Kontext verwendet werden, den Sie als nützlich erachten.  
  
## Abfrageausdrücke  
 Abfrageausdrücke verwenden ähnlich wie SQL oder XQuery eine deklarative Syntax für eine Abfrage über IEnumerable\-Auflistungen.  Eine Abfragesyntax zur Kompilierzeit wird in Methodenaufrufe für eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieterimplementierung der standardmäßigen Abfrageoperator\-Erweiterungsmethoden umgewandelt.  Anwendungen steuern standardmäßige Abfrageoperatoren innerhalb des Bereichs durch die Angabe des entsprechenden Namespaces mit einer `using`\-Direktive.  Beim folgenden Abfrageausdruck wird ein Zeichenfolgenarray verwendet, der anhand des ersten Zeichens in der Zeichenfolge gruppiert wird. Diese Gruppen werden dann sortiert.  
  
```  
var query = from str in stringArray  
            group str by str[0] into stringGroup  
            orderby stringGroup.Key  
            select stringGroup;  
```  
  
 Weitere Informationen finden Sie unter [LINQ\-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md).  
  
## Implizit typisierte Variablen \(var\)  
 Anstatt beim Deklarieren und Initialisieren einer Variable einen Typ explizit anzugeben, können Sie den [var](../../../../csharp/language-reference/keywords/var.md)\-Modifizierer verwenden, um den Compiler zum Ableiten und Zuweisen des Typs anzuweisen, wie hier gezeigt:  
  
```  
var number = 5;  
var name = "Virginia";  
var query = from str in stringArray  
            where str[0] == 'm'  
            select str;  
```  
  
 Als `var` deklarierte Variablen sind ebenso stark typisiert wie Variablen, deren Typ Sie explizit angeben.  Die Verwendung von `var` macht die Erstellung von anonymen Typen möglich, aber es kann auch für alle lokalen Variablen verwendet werden.  Arrays können auch mit impliziter Typisierung deklariert werden.  
  
 Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
## Objekt\- und Auflistungsinitialisierer  
 Objekt\- und Auflistungsinitialisierer ermöglichen die Initialisierung von Objekten ohne den expliziten Aufruf eines Konstruktors für das Objekt.  Initialisierer werden in der Regel in Abfrageausdrücken verwendet, wenn sie die Quelldaten in einen neuen Datentyp projizieren.  Beispiel: Bei einer Klasse mit dem Namen `Customer` mit der öffentlichen `Name`\-Eigenschaft und der öffentlichen `Phone`\-Eigenschaft kann der Objektinitialisierer wie im folgenden Code verwendet werden:  
  
```  
Customer cust = new Customer { Name = "Mike", Phone = "555-1212" };  
```  
  
 Weitere Informationen finden Sie unter [Objekt\- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md).  
  
## Anonyme Typen  
 Ein anonymer Typ wird vom Compiler erstellt, und der Typname ist nur für den Compiler verfügbar.  Mit anonymen Typen können Eigenschaftensätze vorübergehend in einem Abfrageergebnis gruppiert werden, ohne einen separaten benannten Typ definieren zu müssen.  Anonyme Typen werden mit einem neuen Ausdruck und einem Objektinitialisierer initialisiert, wie hier gezeigt:  
  
```  
select new {name = cust.Name, phone = cust.Phone};  
```  
  
 Weitere Informationen finden Sie unter [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## Erweiterungsmethoden  
 Eine Erweiterungsmethode ist eine statische Methode, die mit einem Typ verknüpft werden kann, sodass sie wie eine Instanzenmethode des Typs aufgerufen werden kann.  Dieses Feature ermöglicht Ihnen im Prinzip, neue Methoden vorhandenen Typen "hinzuzufügen", ohne sie tatsächlich zu ändern.  Die standardmäßigen Abfrageoperatoren sind eine Reihe von Erweiterungsmethoden, die [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragefunktionen für jeden Typ bieten, der <xref:System.Collections.Generic.IEnumerable%601> implementiert.  
  
 Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  
  
## Lambda\-Ausdrücke  
 Ein Lambda\-Ausdruck ist eine Inline\-Funktion, die zum Trennen der Eingabeparameter aus dem Funktionstext den Operator \=\> verwendet und die beim Kompilieren in einen Delegaten oder eine Ausdrucksbaumstruktur konvertiert werden kann.  In der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Programmierung arbeiten Sie mit Lambda\-Ausdrücken, wenn Sie direkte Methodenaufrufe für die standardmäßigen Abfrageoperatoren vornehmen, aber nicht bei der Verwendung von Abfragesyntax.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Anonyme Funktionen](../../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)  
  
-   [Lambda\-Ausdrücke](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
  
-   [Ausdrucksbaumstrukturen](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)  
  
## Automatisch implementierte Eigenschaften  
 Automatisch implementierte Eigenschaften machen die Eigenschaftendeklaration präziser.  Wenn Sie eine Eigenschaft wie im folgenden Beispiel gezeigt deklarieren, erstellt der Compiler ein privates, anonymes dahinter liegendes Feld, das nur durch Getter und Setter für die Eigenschaft aufgerufen werden kann.  
  
```  
public string Name {get; set;}  
```  
  
 Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).  
  
## Siehe auch  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Visual Basic Features That Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md)