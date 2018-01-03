---
title: Funktionsausdruck (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb1790d363755fe9b8bd711409734f7c3a405f3e
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="function-expression-visual-basic"></a>Funktionsausdruck (Visual Basic)
Deklariert die Parameter und den Code, der einen Lambda-Ausdruck von Funktion definieren.  
  
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
|`parameterlist`|Dies ist optional. Eine Liste der Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen. Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Erforderlich. Ein einzelner Ausdruck. Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.|  
|`statements`|Erforderlich. Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung. (Siehe [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* ist eine Funktion ohne Namen, die einen Wert berechnet und zurückgibt. Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument für `RemoveHandler`. Weitere Informationen über Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion. Die Unterschiede sind wie folgt aus:  
  
-   Ein Lambda-Ausdruck weist keine Namen auf.  
  
-   Lambda-Ausdrücke dürfen keine Modifizierer enthalten, wie z. B. `Overloads` oder `Overrides`.  
  
-   Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen. Stattdessen wird der Typ nicht abgeleitet aus dem Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder den Rückgabewert eines mehrzeiligen Lambda-Ausdrucks. Wenn der Text eines Lambdaausdrucks einzeilige ist z. B. `Where cust.City = "London"`, der Rückgabetyp ist `Boolean`.  
  
-   Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine Anweisung sein. Der Text kann einen Aufruf an eine Funktionsprozedur, aber nicht auf einen Aufruf an eine Subprozedur sein.  
  
-   Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen abgeleitet werden müssen.  
  
-   Optional und Paramarray-Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Den folgenden Beispielen werden zwei Methoden zum einfachen Lambda-Ausdrücke zu erstellen. Im ersten Beispiel wird eine `Dim` , einen Namen für die Funktion anzugeben. Um die Funktion aufzurufen, senden Sie einen Wert für den Parameter.  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel eines Lambda-Ausdrucks, das Argument inkrementiert und gibt den Wert zurück. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a>Beispiel  
 Lambda-Ausdrücke zugrunde liegen, viele der Standardabfrageoperatoren in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], explizit in methodenbasierten Abfragen verwendet werden können. Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage, gefolgt von der Übersetzung der Abfrage in das Format der Methode.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Weitere Informationen zu Abfragemethoden, finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/queries.md). Weitere Informationen zu den Standardabfrageoperatoren, finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)  
 [Wertvergleiche](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [Boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)  
 [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
