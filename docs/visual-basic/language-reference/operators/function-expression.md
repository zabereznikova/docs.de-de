---
title: Funktionsausdruck (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9b181b18a28a8b92a392fffdc10e08690d54f545
ms.lasthandoff: 03/13/2017

---
# <a name="function-expression-visual-basic"></a>Funktionsausdruck (Visual Basic)
Deklariert die Parameter und Code, die einen Lambda-Funktionsausdruck definieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`parameterlist`|Optional. Eine Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen. Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Erforderlich. Ein einzelner Ausdruck. Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.|  
|`statements`|Erforderlich. Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung. (Siehe [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des Rückgabewerts ist der Rückgabetyp der Funktion.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* ist eine Funktion ohne Namen, die einen Wert berechnet und zurückgibt. Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument für `RemoveHandler`. Weitere Informationen zu Delegaten und der Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion. Die Unterschiede sind wie folgt:  
  
-   Ein Lambda-Ausdruck keinen Namen.  
  
-   Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen. Stattdessen wird der Typ von dem Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder den Rückgabewert eines mehrzeiligen Lambda-Ausdrucks abgeleitet. Wenn der Text eines einzeiligen Lambda-Ausdrucks ist z. B. `Where cust.City = "London"`, dessen Rückgabetyp `Boolean`.  
  
-   Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine Anweisung sein. Der Text kann aus einem Aufruf einer Funktionsprozedur, jedoch nicht aus einem Aufruf einer Sub-Prozedur bestehen.  
  
-   Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.  
  
-   Optional und Paramarray-Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Den folgenden Beispielen werden zwei Methoden zum Erstellen von einfachen Lambda-Ausdrücke. Die erste Anwendung verwendet eine `Dim` einen Namen für die Funktion angeben. Um die Funktion aufrufen, senden Sie einen Wert für den Parameter.  
  
 [!code-vb[VbVbalrLambdas&#1;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas&#2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.  
  
 [!code-vb[VbVbalrLambdas&3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel eines Lambda-Ausdrucks, das Argument inkrementiert und gibt den Wert zurück. Das Beispiel zeigt sowohl die einzeilige und mehrzeilige Lambda-Ausdruckssyntax für eine Funktion. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Lambda-Ausdrücke zugrunde liegen viele Abfrageoperatoren in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], und in methodenbasierten Abfragen explizit verwendet werden können. Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] Abfrage, gefolgt von der Übersetzung der Abfrage in Methode Format.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Weitere Informationen zu Abfragemethoden finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md). Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)   
 [Wertvergleiche](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Wenn Operator](../../../visual-basic/language-reference/operators/if-operator.md)   
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
