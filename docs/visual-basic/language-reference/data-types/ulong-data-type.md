---
title: ULong-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.ulong
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- literal type characters [Visual Basic], UL
- ULong data type
- UL literal type characters [Visual Basic]
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343882"
---
# <a name="ulong-data-type-visual-basic"></a>ULong-Datentyp (Visual Basic)

Enthält nicht signierte 64-Bit-Ganzzahlen (8 Byte) mit einem Wert von 0 bis 18446744073709551615 (mehr als 1,84 mal 10 ^ 19).

## <a name="remarks"></a>Hinweise

Verwenden Sie den `ULong`-Datentyp, um Binärdaten zu enthalten, die für `UInteger`zu groß sind, oder die größtmöglichen ganzzahligen Werte ohne Vorzeichen.

Der Standardwert von `ULong` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `ULong` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das `UL` oder `ul` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `ULong` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `ULong` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `ULong`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Decimal`.

- **CLS-Kompatibilität.** Der `ULong`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten interagieren, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Typen wie `ulong` in anderen Umgebungen eine andere Daten Breite (32 Bits) aufweisen können. Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UInteger`, anstatt `ULong` in Ihrem verwalteten Visual Basic-Code zu verwenden.

  Außerdem werden in Windows 95, Windows 98, Windows Me oder Windows 2000 keine 64-Bit-Ganzzahlen unterstützt. Es ist nicht möglich, ein Visual Basic `ULong`-Argument an eine Automatisierungskomponente auf diesen Plattformen zu übergeben.

- **Tet.** Der `ULong`-Datentyp wird auf `Decimal`, `Single`und `Double`erweitert. Dies bedeutet, dass Sie `ULong` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.

- **Geben Sie Zeichen ein.** Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `UL` werden, wird der Datentyp `ULong` `ULong` hat kein Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.UInt64>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
