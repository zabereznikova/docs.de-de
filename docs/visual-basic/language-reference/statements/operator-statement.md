---
title: Operator Statement
ms.date: 07/20/2015
f1_keywords:
- vb.operator
helpviewer_keywords:
- operators [Visual Basic]
- procedures [Visual Basic], operator
- Narrowing keyword [Visual Basic], conversion operators
- Visual Basic code, operators
- Widening keyword [Visual Basic], conversion operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
- Operator statement [Visual Basic]
- CType function [Visual Basic], Operator statement
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
ms.openlocfilehash: cb7fe7929e4b6e61ca3b39be5615e09182f2fe0f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605497"
---
# <a name="operator-statement"></a>Operator Statement
Deklariert das Symbol "Operator", die Operanden und den Code, die eine Operatorprozedur für eine Klasse oder Struktur definieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## <a name="parts"></a>Teile  
 `attrlist`  
 Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Erforderlich. Gibt an, dass die Operatorprozedur hat [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff.  
  
 `Overloads`  
 Dies ist optional. Finden Sie unter [überlädt](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Erforderlich. Gibt an, dass die Operatorprozedur eine [Shared](../../../visual-basic/language-reference/modifiers/shared.md) Prozedur.  
  
 `Shadows`  
 Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Narrowing`. Gibt an, dass die Operatorprozedur definiert eine [Widening](../../../visual-basic/language-reference/modifiers/widening.md) Konvertierung. Siehe "Erweiternde und eingrenzende Konvertierungen" auf dieser Hilfeseite an.  
  
 `Narrowing`  
 Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Widening`. Gibt an, dass die Operatorprozedur definiert eine [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md) Konvertierung. Siehe "Erweiternde und eingrenzende Konvertierungen" auf dieser Hilfeseite an.  
  
 `operatorsymbol`  
 Erforderlich. Das Symbol oder die ID des Operators, der die Operatorprozedur definiert.  
  
 `operand1`  
 Erforderlich. Der Name und Typ der einzelnen Operanden aus, der ein unäroperator (einschließlich eines Konvertierungsoperators) oder der linke Operand eines binären Operators.  
  
 `operand2`  
 Für binäre Operatoren erforderlich. Der Name und Typ des rechten Operanden des binären Operators.  
  
 `operand1` und `operand2` haben die folgende Syntax und Bestandteile:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Segment|Beschreibung|  
|----------|-----------------|  
|`ByVal`|Optional, doch dem Übergabemechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Erforderlich. Der Name der Variablen, die diesen Operanden darstellt. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Dies ist optional, wenn `Option Strict` ist `On`. Der Datentyp dieses Operanden.|  
  
 `type`  
 Dies ist optional, wenn `Option Strict` ist `On`. Datentyp des Werts die Operatorprozedur gibt.  
  
 `statements`  
 Dies ist optional. Der Block von Anweisungen, die die Operatorprozedur ausgeführt wird.  
  
 `returnvalue`  
 Erforderlich. Der Wert, den die Operatorprozedur an den aufrufenden Code zurückgibt.  
  
 `End` `Operator`  
 Erforderlich. Beendet die Definition dieser Operatorprozedur an.  
  
## <a name="remarks"></a>Hinweise  
 Sie können `Operator` nur in einer Klasse oder Struktur. Dies bedeutet, dass die *Deklarationskontext* für ein Operator darf keine Quelldatei, Namespace, Modul, Schnittstelle, Prozedur oder Block sein. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Alle Operatoren muss `Public Shared`. Sie können keine angeben `ByRef`, `Optional`, oder `ParamArray` für beide Operanden.  
  
 Sie können nicht das Symbol "Operator" oder der Bezeichner verwenden, um einen Rückgabewert zu speichern. Verwenden Sie die `Return` -Anweisung, und sie müssen einen Wert angeben. Eine beliebige Anzahl von `Return` Anweisungen können an beliebiger Stelle in der Prozedur.  
  
 Definieren einen Operator auf diese Weise wird aufgerufen, *operatorüberladung*, unabhängig davon, ob Sie verwenden die `Overloads` Schlüsselwort. In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.  
  
|Typ|Operatoren|  
|----------|---------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binär|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung (unär)|`CType`|  
  
 Beachten Sie, dass die `=` in der Liste binärer Operator wird der Vergleichsoperator, der nicht der Zuweisungsoperator.  
  
 Wenn Sie definieren `CType`, geben Sie `Widening` oder `Narrowing`.  
  
## <a name="matched-pairs"></a>Passende Paare  
 Sie müssen bestimmte Operatoren als zueinander passende Paare definieren. Wenn Sie einen Operator eines solch ein paar definieren, müssen Sie den anderen ebenso definieren. Die passende Paare lauten wie folgt:  
  
-   `=` und `<>`  
  
-   `>` und `<`  
  
-   `>=` und `<=`  
  
-   `IsTrue` und `IsFalse`  
  
## <a name="data-type-restrictions"></a>Datentypeinschränkungen  
 Jeder Operator, den Sie definieren muss umfassen, die Klasse oder Struktur, auf dem Sie definieren. Dies bedeutet, dass die Klasse oder Struktur mit dem Datentyp der folgenden angezeigt werden muss:  
  
-   Der Operand eines unären Operators.  
  
-   Mindestens einer der Operanden des binären Operators.  
  
-   Der Operand oder der Rückgabetyp eines Konvertierungsoperators.  
  
 Bestimmte Operatoren aufweisen Datentyp, zusätzliche Einschränkungen, wie folgt:  
  
-   Wenn Sie definieren die `IsTrue` und `IsFalse` Operatoren müssen beide Zurückgeben der `Boolean` Typ.  
  
-   Wenn Sie definieren die `<<` und `>>` Operatoren müssen beide angeben der `Integer` Geben Sie für die `operandtype` von `operand2`.  
  
 Der Rückgabetyp ist keine der beiden Operanden entsprechen. Angenommen, ein Vergleichsoperator z. B. `=` oder `<>` zurückgeben können `Boolean` auch, wenn keiner der Operanden ist `Boolean`.  
  
## <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren  
 Die `And`, `Or`, `Not`, und `Xor` Operatoren können in Visual Basic logische oder bitweise Operationen durchführen. Wenn Sie einer dieser Operatoren für eine Klasse oder Struktur definieren, können Sie nur die bitweise Operation definieren.  
  
 Keine definieren die `AndAlso` Operator direkt mit einem `Operator` Anweisung. Sie können jedoch `AndAlso` , wenn Sie die folgenden Bedingungen erfüllt sind:  
  
-   Sie haben definiert `And` auf den gleichen Operandentypen, die Sie verwenden möchten `AndAlso`.  
  
-   Die Definition der `And` gibt denselben Typ wie die Klasse oder Struktur, auf dem Sie sie definiert haben.  
  
-   Sie haben definiert die `IsFalse` Operator für die Klasse oder Struktur, auf dem Sie definiert haben `And`.  
  
 Auf ähnliche Weise können Sie `OrElse` Wenn Sie definiert haben `Or` auf die gleichen Operanden mit dem Rückgabetyp der Klasse oder Struktur, und Sie definiertes `IsTrue` für die Klasse oder Struktur.  
  
## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions  
 Ein *erweiternde Konvertierung* ist zur Laufzeit immer erfolgreich, während eine *einschränkende Konvertierung* kann zur Laufzeit fehlschlagen. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Wenn Sie eine Konvertierungsprozedur deklarieren `Widening`, Prozedurcode muss keine Fehler generieren. Dies bedeutet Folgendes:  
  
-   Sie muss immer einen gültigen Wert des Typs zurückgeben `type`.  
  
-   Es muss alle möglichen Ausnahmen und andere fehlerbedingungen behandelt werden.  
  
-   Sie müssen jeden zurückgegebenen Fehler von alle Prozeduren behandeln, die aufruft.  
  
 Wenn eine Möglichkeit besteht, die eine Konvertierungsprozedur nicht erfolgreich ausgeführt werden kann, oder die It dazu führen, eine nicht behandelte Ausnahme dass kann, müssen Sie deklarieren, werden `Narrowing`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Operator` Anweisung, um das Gerüst für eine Struktur definieren, die Operatorprozeduren für enthält die `And`, `Or`, `IsFalse`, und `IsTrue` Operatoren. `And` und `Or` akzeptieren jeweils zwei Operanden vom Typ `abc` und dem Rückgabetyp `abc`. `IsFalse` und `IsTrue` akzeptieren jeweils einen einzelnen Operanden vom Typ `abc` und zurückgeben `Boolean`. Diese Definitionen ermöglicht werden, den aufrufenden Code mit `And`, `AndAlso`, `Or`, und `OrElse` mit Operanden vom Typ `abc`.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [Gewusst wie: Aufrufen einer Operatorprozedur](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)  
 [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
