---
title: UInteger-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343890"
---
# <a name="uinteger-data-type"></a>UInteger-Datentyp

Enthält nicht signierte 32-Bit-Ganzzahlen (4 Bytes) mit einem Wert von 0 bis 4.294.967.295.

## <a name="remarks"></a>Hinweise

Der `UInteger`-Datentyp stellt den größten Wert ohne Vorzeichen in der effizientesten Daten Breite bereit.

Der Standardwert von `UInteger` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `UInteger` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das `UI` oder `ui` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UInteger` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Programmiertipps

Die Datentypen "`UInteger`" und "`Integer`" bieten eine optimale Leistung für einen 32-Bit-Prozessor, da die kleineren ganzzahligen Typen (`UShort`, `Short`, `Byte`und `SByte`), auch wenn weniger Bits verwendet werden, mehr Zeit zum Laden, speichern und Abrufen benötigen.

- **Negative Zahlen.** Da `UInteger` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `UInteger`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Long`.

- **CLS-Kompatibilität.** Der `UInteger`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten interagieren, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Typen wie `uint` in anderen Umgebungen eine andere Daten Breite (16 Bits) aufweisen können. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UShort`, anstatt `UInteger` in Ihrem verwalteten Visual Basic-Code zu verwenden.

- **Tet.** Der `UInteger`-Datentyp wird auf `Long`, `ULong`, `Decimal`, `Single`und `Double`erweitert. Dies bedeutet, dass Sie `UInteger` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.

- **Geben Sie Zeichen ein.** Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `UI` werden, wird der Datentyp `UInteger` `UInteger` hat kein Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.UInt32>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
