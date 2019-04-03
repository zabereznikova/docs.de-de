---
title: Funktionsausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: 0aa47fd277cfe47b3d8f08b41ffca9c547dcbfe9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839680"
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
|`parameterlist`|Dies ist optional. Eine Liste von Namen lokaler Variablen, die die Parameter dieser Prozedur darstellen. Die Klammern müssen vorhanden sein, selbst wenn die Liste leer ist. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`expression`|Erforderlich. Ein einzelner Ausdruck. Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.|  
|`statements`|Erforderlich. Eine Liste von Anweisungen, die einen Wert zurückgibt, mit der `Return` Anweisung. (Finden Sie unter [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* ist eine Funktion ohne einen Namen, die berechnet, und gibt einen Wert zurück. Sie können einen Lambda-Ausdruck an einer beliebigen Stelle können Sie einen Delegattyp, außer als Argument an `RemoveHandler`. Weitere Informationen zu Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt einer standard-Funktion. Die Unterschiede sind wie folgt aus:  
  
-   Ein Lambda-Ausdruck ist nicht auf einen Namen haben.  
  
-   Lambda-Ausdrücke sind keine Modifizierer, z. B. `Overloads` oder `Overrides`.  
  
-   Lambda-Ausdrücke verwenden Sie keine `As` -Klausel, um den Rückgabetyp der Funktion festlegen. Stattdessen wird der Typ der Wert, dem der Text eines einzeiligen Lambda-Ausdrucks ergibt, oder der Rückgabewert eines mehrzeiligen Lambda-Ausdrucks abgeleitet. Wenn der Text eines einzeiligen Lambda-Ausdrucks ist z. B. `Where cust.City = "London"`, dessen Rückgabetyp `Boolean`.  
  
-   Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um einen Ausdruck, der keine Anweisung sein. Der Text kann aus einem Aufruf einer Funktionsprozedur, aber nicht aus einem Aufruf an eine Subprozedur bestehen.  
  
-   Entweder für alle Parameter müssen angegeben haben, oder alle Datentypen per Rückschluss abgeleitet werden müssen.  
  
-   Optional "und" Paramarray-Parameter sind nicht zulässig.  
  
-   Generische Parameter sind nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen zwei Möglichkeiten zum Erstellen von einfachen Lambda-Ausdrücke. Im ersten Beispiel wird eine `Dim` einen Namen für die Funktion bereitstellen. Um die Funktion aufzurufen, senden Sie einen Wert für den Parameter.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Beispiel  
 Alternativ können Sie deklarieren, und führen Sie die Funktion zur gleichen Zeit.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Es folgt ein Beispiel für einen Lambda-Ausdruck, der inkrementiert des Arguments und gibt den Wert zurück. Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Funktion. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>Beispiel  
 Lambda-Ausdrücke zugrunde liegen viele Abfrageoperatoren in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], explizit in methodenbasierten Abfragen verwendet werden können. Das folgende Beispiel zeigt eine typische [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] Abfrage, gefolgt von der Verschiebung der Abfrage in das Format der Methode.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Weitere Informationen zu Abfragemethoden finden Sie unter [Abfragen](../../../visual-basic/language-reference/queries/index.md). Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Wertvergleiche](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Boolesche Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [If-Operator](../../../visual-basic/language-reference/operators/if-operator.md)
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
