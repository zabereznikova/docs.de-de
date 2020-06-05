---
title: Function-Ausdruck
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: a9b621ff03f833fcf0f07f876fd864ee963bef75
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371180"
---
# <a name="function-expression-visual-basic"></a>Funktionsausdruck (Visual Basic)
Deklariert die Parameter und den Code, die einen Funktions-Lambda-Ausdruck definieren.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`parameterlist`|Dies ist optional. Eine Liste der Namen der lokalen Variablen, die die Parameter dieser Prozedur darstellen. Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist. Siehe [Parameter Liste](../statements/parameter-list.md).|  
|`expression`|Erforderlich. Ein einzelner Ausdruck. Der Typ des Ausdrucks ist der Rückgabetyp der Funktion.|  
|`statements`|Erforderlich. Eine Liste von-Anweisungen, die mithilfe der-Anweisung einen Wert zurückgibt `Return` . (Siehe [Return-Anweisung](../statements/return-statement.md).) Der Typ des zurückgegebenen Werts ist der Rückgabetyp der Funktion.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein *Lambda-Ausdruck* ist eine Funktion ohne einen Namen, der einen Wert berechnet und zurückgibt. Sie können einen Lambda-Ausdruck überall dort verwenden, wo Sie einen Delegattyp verwenden können, außer als Argument für `RemoveHandler` . Weitere Informationen zu Delegaten und zur Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [delegatanweisung](../statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standardfunktion. Es gibt die folgenden Unterschiede:  
  
- Ein Lambda-Ausdruck weist keinen Namen auf.  
  
- Lambda Ausdrücke können keine Modifizierer aufweisen, wie z `Overloads` `Overrides` . b. oder.  
  
- Lambda-Ausdrücke verwenden keine- `As` Klausel, um den Rückgabetyp der Funktion festzulegen. Stattdessen wird der-Typ von dem Wert abgeleitet, den der Text eines einzeiligen Lambda Ausdrucks ergibt, oder der Rückgabewert eines mehrzeiligen Lambda Ausdrucks. Wenn der Text eines einzeiligen Lambda-Ausdrucks beispielsweise ist `Where cust.City = "London"` , ist der Rückgabetyp `Boolean` .  
  
- Der Text eines einzeiligen Lambda-Ausdrucks muss ein Ausdruck und keine-Anweisung sein. Der Text kann aus einem aufzurufenden Funktions Vorgang bestehen, jedoch nicht mit einem-Vorgang.  
  
- Entweder müssen alle Parameter über bestimmte Datentypen verfügen, oder alle müssen abgeleitet werden.  
  
- Optionale Parameter und ParamArray-Parameter sind nicht zulässig.  
  
- Generische Parameter sind nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen werden zwei Möglichkeiten zum Erstellen einfacher Lambda-Ausdrücke veranschaulicht. Der erste verwendet einen `Dim` , um einen Namen für die Funktion bereitzustellen. Zum Aufrufen der-Funktion senden Sie einen Wert für den-Parameter.  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a>Beispiel  
 Alternativ dazu können Sie die Funktion gleichzeitig deklarieren und ausführen.  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden finden Sie ein Beispiel für einen Lambda-Ausdruck, der sein Argument erhöht und den Wert zurückgibt. Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Funktion. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a>Beispiel  
 Lambda-Ausdrücke unterliegen vielen der Abfrage Operatoren in LINQ (Language-Integrated Query) und können in Methoden basierten Abfragen explizit verwendet werden. Das folgende Beispiel zeigt eine typische LINQ-Abfrage, gefolgt von der Übersetzung der Abfrage in das Methoden Format.  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 Weitere Informationen zu Abfrage Methoden finden Sie unter [Abfragen](../queries/index.md). Weitere Informationen zu Standard Abfrage Operatoren finden Sie unter [Übersicht über Standard Abfrage Operatoren](../../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Function-Anweisung](../statements/function-statement.md)
- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatoren und Ausdrücke](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../programming-guide/language-features/statements.md)
- [Wertvergleiche](../../programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [Boolesche Ausdrücke](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [If-Operator](if-operator.md)
- [Gelockerte Delegatenkonvertierung](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
