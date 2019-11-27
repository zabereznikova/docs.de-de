---
title: Operator ^
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: b9860b7b6e076fc9c0288818aa9e4f2c0fc4c356
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331109"
---
# <a name="-operator-visual-basic"></a>^-Operator (Visual Basic)

Potenziert eine Zahl mit einer anderen Zahl.

## <a name="syntax"></a>Syntax

```vb
number ^ exponent
```

## <a name="parts"></a>-Komponenten

`number`\
Erforderlich Ein beliebiger numerischer Ausdruck.

`exponent`\
Erforderlich Ein beliebiger numerischer Ausdruck.

## <a name="result"></a>Ergebnis

Das Ergebnis wird `number` der Leistungsfähigkeit von `exponent`, immer als `Double` Wert ausgelöst.

## <a name="supported-types"></a>Unterstützte Typen

`Double`. Operanden eines beliebigen Typs werden in `Double`konvertiert.

## <a name="remarks"></a>Hinweise

Visual Basic führt immer eine exponentiell im [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)aus.

Der Wert von `exponent` kann eine Bruch Zahl, eine negative oder beides sein.

Wenn mehr als eine exponentiell in einem einzelnen Ausdruck ausgeführt wird, wird der `^`-Operator ausgewertet, da er von links nach rechts gefunden wird.

> [!NOTE]
> Der `^`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der `^`-Operator verwendet, um eine Zahl zur Potenz eines Exponenten zu erhöhen. Das Ergebnis ist der erste Operand, der für die zweite Potenz ausgelöst wird.

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

Das vorangehende Beispiel erzeugt die folgenden Ergebnisse:

`exp1` ist auf 4 (2 Quadrat) festgelegt.

`exp2` ist auf 19683 (3 Cub, dann auf diesen Wert) festgelegt.

`exp3` ist auf-125 (-5-CUB) festgelegt.

`exp4` ist auf 625 (-5 bis zum vierten Strom) festgelegt.

`exp5` ist auf 2 (Cube-Stamm von 8) festgelegt.

`exp6` ist auf 0,5 (1,0 dividiert durch den Cube-Stamm von 8) festgelegt.

Beachten Sie die Wichtigkeit der Klammern in den Ausdrücken im vorherigen Beispiel. Aufgrund der *Operator Rangfolge*führt Visual Basic normalerweise den `^` Operator vor allen anderen, auch dem unären `–` Operator. Wenn `exp4` und `exp6` ohne Klammern berechnet wurden, haben Sie die folgenden Ergebnisse erzeugt:

`exp4 = -5 ^ 4` wird als – (5 bis zum vierten Strom) berechnet, was zu-625 führen würde.

`exp6 = 8 ^ -1.0 / 3.0` wird als (8 bis – 1 Potenz oder 0,125) dividiert durch 3,0 berechnet, was zu 0.041666666666666666666666666666667 führen würde.

## <a name="see-also"></a>Siehe auch

- [^=-Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
