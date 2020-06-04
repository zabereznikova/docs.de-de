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
ms.openlocfilehash: f9e6ffe5a49715592399321ab471d73826e05d8e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404394"
---
# <a name="operator-statement"></a>Operator Statement

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

## <a name="parts"></a>Bestandteile

`attrlist`  
Optional. Siehe [Attribut Liste](attribute-list.md).

`Public`  
Erforderlich. Gibt an, dass diese Operator Prozedur [öffentlichen](../modifiers/public.md) Zugriff hat.

`Overloads`  
Optional. Siehe [über Ladungen](../modifiers/overloads.md).

`Shared`  
Erforderlich. Gibt an, dass diese Operator Prozedur eine frei [gegebene](../modifiers/shared.md) Prozedur ist.

`Shadows`  
Optional. Siehe [Shadows](../modifiers/shadows.md).

`Widening`  
Ist für einen Konvertierungs Operator erforderlich, sofern Sie nicht angeben `Narrowing` . Gibt an, dass diese Operator Prozedur eine [erweiternde](../modifiers/widening.md) Konvertierung definiert. Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".

`Narrowing`  
Ist für einen Konvertierungs Operator erforderlich, sofern Sie nicht angeben `Widening` . Gibt an, dass diese Operator Prozedur [eine](../modifiers/narrowing.md) einschränkende Konvertierung definiert. Weitere Informationen finden Sie auf dieser Hilfeseite unter "erweitern und einschränkende Konvertierungen".

`operatorsymbol`  
Erforderlich. Das Symbol oder der Bezeichner des Operators, den diese Operator Prozedur definiert.

`operand1`  
Erforderlich. Der Name und Typ des einzelnen Operanden eines unären Operators (einschließlich eines Konvertierungs Operators) oder der linke Operand eines binären Operators.

`operand2`  
Für binäre Operatoren erforderlich. Der Name und der Typ des rechten Operanden eines binären Operators.

`operand1`und `operand2` haben die folgende Syntax und Teile:

`[ ByVal ] operandname [ As operandtype ]`

|Teil|BESCHREIBUNG|
|----------|-----------------|
|`ByVal`|Optional, aber der Übergabe Mechanismus muss [ByVal](../modifiers/byval.md)lauten.|
|`operandname`|Erforderlich. Der Name der Variablen, die diesen Operanden darstellt. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`operandtype`|Optional, sofern nicht `Option Strict` ist `On` . Datentyp dieses Operanden.|

`type`  
Optional, sofern nicht `Option Strict` ist `On` . Datentyp des Werts, den die Operator Prozedur zurückgibt.

`statements`  
Optional. Block von-Anweisungen, die von der Operator Prozedur ausgeführt werden.

`returnvalue`  
Erforderlich. Der Wert, den die Operator Prozedur an den aufrufenden Code zurückgibt.

`End` `Operator`  
Erforderlich. Beendet die Definition dieser Operator Prozedur.

## <a name="remarks"></a>Bemerkungen

Sie können `Operator` nur in einer Klasse oder Struktur verwenden. Dies bedeutet, dass der *Deklarations Kontext* für einen Operator keine Quelldatei, ein Namespace, ein Modul, eine Schnittstelle, eine Prozedur oder ein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).

Alle Operatoren müssen sein `Public Shared` . Sie können `ByRef` , oder nicht für einen der `Optional` `ParamArray` Operanden angeben.

Sie können das Operator Symbol oder den Bezeichner nicht verwenden, um einen Rückgabewert zu speichern. Sie müssen die `Return` -Anweisung verwenden, und Sie müssen einen Wert angeben. Eine beliebige Anzahl von- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur vorkommen.

Die Definition eines Operators auf diese Weise wird als *Operator Überladung*bezeichnet, unabhängig davon, ob Sie das- `Overloads` Schlüsselwort verwenden. In der folgenden Tabelle sind die Operatoren aufgelistet, die Sie definieren können.

|type|Operatoren|
|----------|---------------|
|Unäroperatoren|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|
|Konvertierung (unär)|`CType`|

Beachten Sie, dass der- `=` Operator in der binären Liste der Vergleichs Operator und nicht der Zuweisungs Operator ist.

Wenn Sie definieren `CType` , müssen Sie entweder `Widening` oder angeben `Narrowing` .

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

- Wenn Sie die `IsTrue` `IsFalse` Operatoren und definieren, müssen beide den Typ zurückgeben `Boolean` .

- Wenn Sie die `<<` `>>` Operatoren und definieren, müssen beide den `Integer` Typ für den `operandtype` von angeben `operand2` .

Der Rückgabetyp muss nicht dem Typ eines der beiden Operanden entsprechen. Beispielsweise kann ein Vergleichs Operator, z `=` . b. oder, `<>` auch dann zurückgeben, `Boolean` Wenn keiner der Operanden ist `Boolean` .

## <a name="logical-and-bitwise-operators"></a>Logische und bitweise Operatoren

Die `And` `Or` `Not` Operatoren,, und `Xor` können in Visual Basic entweder logische oder bitweise Vorgänge ausführen. Wenn Sie jedoch einen dieser Operatoren für eine Klasse oder Struktur definieren, können Sie nur die bitweise Operation definieren.

Der Operator kann nicht `AndAlso` direkt mit einer- `Operator` Anweisung definiert werden. Sie können jedoch verwenden, `AndAlso` Wenn die folgenden Bedingungen erfüllt sind:

- Sie haben für `And` dieselben Operanden Typen definiert, die Sie für verwenden möchten `AndAlso` .

- Ihre Definition von `And` gibt denselben Typ zurück wie die Klasse oder Struktur, in der Sie Sie definiert haben.

- Sie haben den- `IsFalse` Operator für die Klasse oder Struktur definiert, von der Sie definiert haben `And` .

Auf ähnliche Weise können Sie verwenden, `OrElse` Wenn Sie `Or` für dieselben Operanden definiert haben, mit dem Rückgabetyp der Klasse oder Struktur, und Sie `IsTrue` die Klasse oder Struktur definiert haben.

## <a name="widening-and-narrowing-conversions"></a>Widening and Narrowing Conversions

Eine *erweiternde Konvertierung* ist immer erfolgreich, während eine einschränkende *Konvertierung* zur Laufzeit fehlschlagen kann. Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).

Wenn Sie eine Konvertierungs Prozedur als deklarieren `Widening` , darf der Prozedur Code keine Fehler generieren. Dies bedeutet Folgendes:

- Er muss immer einen gültigen Wert des Typs zurückgeben `type` .

- Alle möglichen Ausnahmen und andere Fehlerbedingungen müssen behandelt werden.

- Es muss alle Fehler zurückgegeben werden, die von allen Prozeduren aufgerufen werden.

Wenn die Möglichkeit besteht, dass eine Konvertierungs Prozedur möglicherweise nicht erfolgreich ist oder eine nicht behandelte Ausnahme verursacht, müssen Sie Sie als angeben `Narrowing` .

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die- `Operator` Anweisung verwendet, um die Gliederung einer-Struktur zu definieren, die Operator Prozeduren für die `And` `Or` `IsFalse` Operatoren,, und enthält `IsTrue` . `And`und `Or` jeweils zwei Operanden vom Typ `abc` und Rückgabetyp `abc` . `IsFalse`und `IsTrue` jeweils einen einzigen Operanden vom Typ `abc` und geben zurück `Boolean` . Diese Definitionen ermöglichen es dem aufrufenden Code `And` ,,, `AndAlso` `Or` und `OrElse` mit Operanden vom Typ `abc` zu verwenden.

[!code-vb[VbVbalrStatements#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#44)]

## <a name="see-also"></a>Weitere Informationen

- [IsFalse-Operator](../operators/isfalse-operator.md)
- [IsTrue-Operator](../operators/istrue-operator.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Widening and Narrowing Conversions](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Operatorprozeduren](../../programming-guide/language-features/procedures/operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](../../programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert](../../programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)
