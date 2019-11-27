---
title: Operator-Anweisung
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
ms.openlocfilehash: aa6ae3977977ded05e47d12dabe72f09251f262d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353797"
---
# <a name="operator-statement"></a>Operator-Anweisung

Deklariert das Operator Symbol, die Operanden und den Code, die eine Operator Prozedur für eine Klasse oder Struktur definieren.

## <a name="syntax"></a>Syntax

```vb
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]
    [ statements ]
    [ statements ]
    Return returnvalue
    [ statements ]
End Operator
```

## <a name="parts"></a>-Komponenten

`attrlist`  
Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).

`Public`  
Erforderlich Gibt an, dass diese Operator Prozedur [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff hat.

`Overloads`  
Optional. Siehe [über Ladungen](../../../visual-basic/language-reference/modifiers/overloads.md).

`Shared`  
Erforderlich Gibt an, dass diese Operator Prozedur eine frei [gegebene](../../../visual-basic/language-reference/modifiers/shared.md) Prozedur ist.

`Shadows`  
Optional. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).

`Widening`  
Für einen Konvertierungs Operator erforderlich, es sei denn, Sie geben `Narrowing`an Gibt an, dass diese Operator Prozedur eine [erweiternde](../../../visual-basic/language-reference/modifiers/widening.md) Konvertierung definiert. Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".

`Narrowing`  
Für einen Konvertierungs Operator erforderlich, es sei denn, Sie geben `Widening`an Gibt an, dass diese Operator Prozedur [eine](../../../visual-basic/language-reference/modifiers/narrowing.md) einschränkende Konvertierung definiert. Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".

`operatorsymbol`  
Erforderlich Das Symbol oder der Bezeichner des Operators, den diese Operator Prozedur definiert.

`operand1`  
Erforderlich Der Name und Typ des einzelnen Operanden eines unären Operators (einschließlich eines Konvertierungs Operators) oder der linke Operand eines binären Operators.

`operand2`  
Für binäre Operatoren erforderlich. Der Name und der Typ des rechten Operanden eines binären Operators.

`operand1` und `operand2` haben die folgende Syntax und die folgenden Teile:

`[ ByVal ] operandname [ As operandtype ]`

|-Komponente|Beschreibung|
|----------|-----------------|
|`ByVal`|Optional, aber der Übergabe Mechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)lauten.|
|`operandname`|Erforderlich Der Name der Variablen, die diesen Operanden darstellt. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Optional, es sei denn, `Option Strict` ist `On`. Datentyp dieses Operanden.|

`type`  
Optional, es sei denn, `Option Strict` ist `On`. Datentyp des Werts, den die Operator Prozedur zurückgibt.

`statements`  
Optional. Block von-Anweisungen, die von der Operator Prozedur ausgeführt werden.

`returnvalue`  
Erforderlich Der Wert, den die Operator Prozedur an den aufrufenden Code zurückgibt.

`End` `Operator`  
Erforderlich Beendet die Definition dieser Operator Prozedur.

## <a name="remarks"></a>Hinweise

Sie können `Operator` nur in einer Klasse oder Struktur verwenden. Dies bedeutet, dass der *Deklarations Kontext* für einen Operator keine Quelldatei, ein Namespace, ein Modul, eine Schnittstelle, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).

Alle Operatoren müssen `Public Shared`werden. `ByRef`, `Optional`oder `ParamArray` können nicht für einen der Operanden angegeben werden.

Sie können das Operator Symbol oder den Bezeichner nicht verwenden, um einen Rückgabewert zu speichern. Sie müssen die `Return`-Anweisung verwenden, und Sie müssen einen Wert angeben. Eine beliebige Anzahl von `Return`-Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden.

Die Definition eines Operators auf diese Weise wird als *Operator Überladung*bezeichnet, unabhängig davon, ob Sie das `Overloads`-Schlüsselwort verwenden. In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.

|Typ|Operatoren|
|----------|---------------|
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Konvertierung (unär)|`CType`|

Beachten Sie, dass der `=`-Operator in der binären Liste der Vergleichs Operator, nicht der Zuweisungs Operator ist.

Wenn Sie `CType`definieren, müssen Sie entweder `Widening` oder `Narrowing`angeben.

## <a name="matched-pairs"></a>Übereinstimmende Paare

Sie müssen bestimmte Operatoren als übereinstimmende Paare definieren. Wenn Sie einen der beiden Operatoren eines solchen Paars definieren, müssen Sie auch den anderen definieren. Die übereinstimmenden Paare lauten wie folgt:

- `=` und `<>`

- `>` und `<`

- `>=` und `<=`

- `IsTrue` und `IsFalse`

## <a name="data-type-restrictions"></a>Datentyp Einschränkungen

Jeder Operator, den Sie definieren, muss die Klasse oder Struktur einschließen, in der Sie ihn definieren. Dies bedeutet, dass die Klasse oder Struktur als Datentyp von folgendem angezeigt werden muss:

- Der Operand eines unären Operators.

- Mindestens einer der Operanden eines binären Operators.

- Entweder der Operand oder der Rückgabetyp eines Konvertierungs Operators.

 Für bestimmte Operatoren gelten folgende Einschränkungen für den Datentyp:

- Wenn Sie die Operatoren `IsTrue` und `IsFalse` definieren, müssen beide den `Boolean` Typ zurückgeben.

- Wenn Sie die Operatoren `<<` und `>>` definieren, müssen beide den `Integer` Typ für die `operandtype` `operand2`angeben.

Der Rückgabetyp muss nicht dem Typ eines der beiden Operanden entsprechen. Beispielsweise kann ein Vergleichs Operator wie `=` oder `<>` `Boolean` zurückgeben, auch wenn keiner der Operanden `Boolean`ist.

## <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren

Die Operatoren "`And`", "`Or`", "`Not`" und "`Xor`" können entweder logische oder bitweise Vorgänge in Visual Basic ausführen. Wenn Sie jedoch einen dieser Operatoren für eine Klasse oder Struktur definieren, können Sie nur die bitweise Operation definieren.

Der `AndAlso`-Operator kann nicht direkt mit einer `Operator`-Anweisung definiert werden. Sie können jedoch `AndAlso` verwenden, wenn die folgenden Bedingungen erfüllt sind:

- Sie haben `And` für dieselben Operanden definiert, die Sie für `AndAlso`verwenden möchten.

- Die Definition von `And` gibt denselben Typ zurück wie die Klasse oder Struktur, in der Sie Sie definiert haben.

- Sie haben den `IsFalse`-Operator für die Klasse oder Struktur definiert, für die Sie `And`definiert haben.

Auf ähnliche Weise können Sie `OrElse` verwenden, wenn Sie `Or` auf denselben Operanden mit dem Rückgabetyp der Klasse oder Struktur definiert haben und `IsTrue` für die Klasse oder Struktur definiert haben.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Eine *erweiternde Konvertierung* ist immer erfolgreich, während eine einschränkende *Konvertierung* zur Laufzeit fehlschlagen kann. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Wenn Sie eine Konvertierungs Prozedur deklarieren, die `Widening`werden soll, darf der Prozedur Code keine Fehler generieren. Dies bedeutet Folgendes:

- Sie muss immer einen gültigen Wert vom Typ `type`zurückgeben.

- Alle möglichen Ausnahmen und andere Fehlerbedingungen müssen behandelt werden.

- Es muss alle Fehler zurückgegeben werden, die von allen Prozeduren aufgerufen werden.

Wenn die Möglichkeit besteht, dass eine Konvertierungs Prozedur möglicherweise nicht erfolgreich ist oder eine nicht behandelte Ausnahme verursacht, müssen Sie Sie als `Narrowing`deklarieren.

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die `Operator`-Anweisung verwendet, um die Gliederung einer Struktur zu definieren, die Operator Prozeduren für die Operatoren `And`, `Or`, `IsFalse`und `IsTrue` einschließt. `And` und `Or` beide beide Operanden vom Typ `abc` und den Rückgabetyp `abc`. `IsFalse` und `IsTrue` die jeweils einen einzigen Operanden vom Typ `abc` und `Boolean`zurückgeben. Diese Definitionen ermöglichen es dem aufrufenden Code, `And`, `AndAlso`, `Or`und `OrElse` mit Operanden des Typs `abc`zu verwenden.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Siehe auch

- [IsFalse-Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Widening](../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Gewusst wie: Definieren eines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Gewusst wie: Aufrufen einer Operatorprozedur](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
