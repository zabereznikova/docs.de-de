---
title: "Function Expression (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Function expression [Visual Basic]"
  - "functions [Visual Basic], function expressions"
  - "lambda expressions [Visual Basic], function expression"
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Function Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert die Parameter und den Code, die einen Lambda\-Funktionsausdruck definieren.  
  
## Syntax  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`parameterlist`|Optional.  Eine Liste der Namen von lokalen Variablen, die die Parameter dieser Prozedur darstellen.  Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist.  Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Erforderlich.  Ein einzelner Ausdruck.  Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.|  
|`statements`|Erforderlich.  Eine Liste von Anweisungen, die mit der Anweisung `Return` einen Wert zurückgibt.  \(Siehe [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).\) Der Typ des Rückgabewerts ist der Rückgabetyp der Funktion.|  
  
## Hinweise  
 Ein *Lambda\-Ausdruck* ist eine Funktion ohne Namen, von der ein einzelner Wert berechnet und zurückgegeben wird.  Sie können einen Lambda\-Ausdruck überall dort verwenden, wo Sie auch einen Delegattyp verwenden können, außer als Argument für `RemoveHandler`.  Weitere Informationen zu Delegaten und der Verwendung von Lambda\-Ausdrücken mit Delegaten, finden Sie unter [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) und [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## Lambda\-Ausdruckssyntax  
 Die Syntax eines Lambda\-Ausdrucks ähnelt der einer Standardfunktion.  Die Unterschiede sind:  
  
-   Ein Lambda\-Ausdruck verfügt über keinen Namen.  
  
-   Lambda\-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   In Lambda\-Ausdrücken wird der Rückgabetyp der Funktion nicht mit einer `As`\-Klausel festgelegt.  Stattdessen wird der Typ von dem Wert, zu dem der Text des einzeiligen Lambda\-Ausdruck ausgewertet wird, oder dem Rückgabewert des mehrzeiligen Lambda\-Ausdruck abgeleitet.  Wenn der Text eines einzeiligen Lambda\-Ausdrucks z. B. `Where cust.City = "London"` lautet, ist dessen Rückgabetyp `Boolean`.  
  
-   Der Text des einzeiligen Lambda\-Ausdruck muss ein Ausdruck sein, keine Anweisung.  Der Text kann aus einem Aufruf einer Funktionsprozedur bestehen, jedoch nicht aus einem Aufruf einer Unterprozedur.  
  
-   Entweder müssen alle Parameter über angegebene Datentypen verfügen, oder alle Datentypen müssen abgeleitet sein.  
  
-   Optionale und ParamArray\-Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## Beispiel  
 In den folgenden Beispielen werden zwei Möglichkeiten für die Erstellung einfacher Lambda\-Ausdrücke gezeigt.  Im ersten Beispiel wird mithilfe von `Dim` ein Name für die Funktion bereitgestellt.  Zum Aufrufen der Funktion übergeben Sie einen Wert als Parameter.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#2)]  
  
## Beispiel  
 Alternativ kann die Funktion gleichzeitig deklariert und ausgeführt werden.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#3)]  
  
## Beispiel  
 Das folgende Beispiel zeigt einen Lambda\-Ausdruck, der das übergebene Argument inkrementiert und den Wert zurückgibt.  Im Beispiel wird die Syntax für einzeilige und mehrzeilige Lambda\-Ausdrücke für eine Funktion veranschaulicht.  Weitere Beispiele finden Sie unter [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/vbvbalrlambdas/Class1.vb#14)]  
  
## Beispiel  
 In [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext-md.md)] liegen zahlreichen Abfrageoperatoren Lambda\-Ausdrücke zugrunde, die in methodenbasierten Abfragen explizit verwendet werden können.  Im folgenden Beispiel wird eine typische [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Abfrage gefolgt von der Übersetzung der Abfrageinformationen in das Methodenformat dargestellt.  
  
```vb#  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Weitere Informationen zu Abfragemethoden finden Sie unter [Queries](../../../visual-basic/language-reference/queries/queries.md).  Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## Siehe auch  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [If Operator](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)