---
title: Long-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Long
helpviewer_keywords:
- identifier type characters [Visual Basic], &
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- '& identifier type character'
- integer numbers
- literal type characters [Visual Basic], L
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- L literal type character [Visual Basic]
- integers [Visual Basic], types
- Long keyword [Visual Basic]
- data types [Visual Basic], integral
- data types [Visual Basic], assigning
- Long data type
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343975"
---
# <a name="long-data-type-visual-basic"></a>Long-Datentyp (Visual Basic)

Enthält signierte 64-Bit-Ganzzahlen (8 Byte) mit einem Wert von-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 (9.2... E + 18).

## <a name="remarks"></a>Hinweise

Verwenden Sie den `Long`-Datentyp, um ganzzahlige Zahlen zu enthalten, die zu groß für den `Integer` Datentyp sind.

Der Standardwert von `Long` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `Long` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Long` befindet – sprich, wenn es kleiner als <xref:System.Int64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Long`-Werten zugewiesen.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das `L` [Type-Zeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Long` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), denken Sie daran, dass `Long` in anderen Umgebungen eine andere Daten Breite (32 Bits) aufweist. Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Integer`, anstatt `Long` im neuen Visual Basic Code zu verwenden.

- **Tet.** Der `Long`-Datentyp wird zu `Decimal`, `Single`oder `Double`erweitert. Dies bedeutet, dass Sie `Long` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.

- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `L` an ein Literal wird der `Long`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `&` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Long`-Datentyp erzwungen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int64?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.Int64>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
