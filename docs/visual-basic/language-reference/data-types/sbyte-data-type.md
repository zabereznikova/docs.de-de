---
title: SByte-Datentyp
ms.date: 04/20/2017
f1_keywords:
- vb.sbyte
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- SByte data type
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
ms.openlocfilehash: e7d45c74056ce5b6aa66674c99e48b5ab60015f0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415569"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte-Datentyp (Visual Basic)

Enthält signierte 8-Bit-Ganzzahlen (1 Byte), die den Wert von-128 bis 127 über liegen.

## <a name="remarks"></a>Bemerkungen

Verwenden Sie den- `SByte` Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von `Integer` oder sogar die halbe Daten Breite von benötigen `Short` . In einigen Fällen können die Common Language Runtime Ihre `SByte` Variablen eng zusammenpacken und die Arbeitsspeicher Nutzung sparen.

Der Standardwert von `SByte` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine-Variable deklarieren und initialisieren, `SByte` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein oktalliteralformat oder (beginnend mit Visual Basic 2017) ein binäres Literalformat zuweisen.

Im folgenden Beispiel werden ganzzahlige Werte von-102, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, den- `SByte` Werten zugewiesen. Für dieses Beispiel ist es erforderlich, dass Sie mit dem `/removeintchecks` Compilerschalter kompilieren.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral kein Suffix aufweist, wird eine [ganze](integer-data-type.md) Zahl abgeleitet. Wenn das ganzzahlige Literale außerhalb des Bereichs des `Integer` Typs liegt, wird eine [lange](long-data-type.md) abgeleitet. Dies bedeutet, dass in den vorherigen Beispielen die numerischen Literale `0x9A` und `0b10011010` als 32-Bit-Ganzzahlen mit Vorzeichen mit einem Wert von 156 interpretiert werden, der überschreitet <xref:System.SByte.MaxValue?displayProperty=nameWithType> . Zur erfolgreichen Kompilierung von Code, der eine nicht-Dezimalzahl zu einem zuweist `SByte` , können Sie einen der folgenden Schritte ausführen:

- Deaktivieren Sie die Überprüfungen der ganzzahligen Grenzen, indem Sie Sie mit dem `/removeintchecks`

- Verwenden Sie ein [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) , um den Literalwert, den Sie der zuweisen möchten, explizit zu definieren `SByte` . Im folgenden Beispiel wird einem ein negativer `Short` Literalwert zugewiesen `SByte` . Beachten Sie, dass für negative Zahlen das höchst wertige Bit des großen Worts des numerischen Literals festgelegt werden muss. Im vorliegenden Beispiel ist dies Bit 15 des `Short` Literalwerts.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Programmiertipps

- **CLS-Kompatibilität.** Der- `SByte` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Tet.** Der `SByte` -Datentyp wird zu `Short` , `Integer` , `Long` , `Decimal` , `Single` und erweitert `Double` . Dies bedeutet `SByte` , dass Sie in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.

- **Geben Sie Zeichen ein.** `SByte`weist kein Literaltyp Zeichen oder Bezeichnertyp Zeichen auf.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.SByte?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Short-Datentyp](short-data-type.md)
- [Integer-Datentyp](integer-data-type.md)
- [Long-Datentyp](long-data-type.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
