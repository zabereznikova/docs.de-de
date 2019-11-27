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
ms.openlocfilehash: 01a0a4a261213d7e6e2016bf49128092e5b22308
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343949"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte-Datentyp (Visual Basic)

Enthält signierte 8-Bit-Ganzzahlen (1 Byte), die den Wert von-128 bis 127 über liegen.

## <a name="remarks"></a>Hinweise

Verwenden Sie den `SByte`-Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von `Integer` oder sogar die halbe Daten Breite `Short`benötigen. In einigen Fällen können die Common Language Runtime ihre `SByte` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.

Der Standardwert von `SByte` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `SByte` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen.

Im folgenden Beispiel werden Ganzzahlen von-102, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, `SByte` Werten zugewiesen. Für dieses Beispiel ist es erforderlich, dass Sie mit dem `/removeintchecks`-Compilerschalter kompilieren.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral kein Suffix aufweist, wird eine [ganze](integer-data-type.md) Zahl abgeleitet. Wenn das ganzzahlige Literale außerhalb des Bereichs des `Integer` Typs liegt, wird eine [lange](long-data-type.md) abgeleitet. Dies bedeutet, dass in den vorherigen Beispielen die numerischen Literale `0x9A` und `0b10011010` als 32-Bit-Ganzzahlen mit Vorzeichen mit einem Wert von 156 interpretiert werden, der <xref:System.SByte.MaxValue?displayProperty=nameWithType>überschreitet. Zur erfolgreichen Kompilierung von Code wie diesem, der einer `SByte`eine nicht dezimale Ganzzahl zuweist, können Sie eine der folgenden Aktionen ausführen:

- Deaktivieren Sie Überprüfungen der ganzzahligen Grenzen, indem Sie die Kompilierung mit dem `/removeintchecks`

- Verwenden Sie ein [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) , um den Literalwert, den Sie dem `SByte`zuweisen möchten, explizit zu definieren. Im folgenden Beispiel wird einem `SByte`ein negativer Literal`Short` Wert zugewiesen. Beachten Sie, dass für negative Zahlen das höchst wertige Bit des großen Worts des numerischen Literals festgelegt werden muss. Im vorliegenden Beispiel ist dies Bit 15 des literalen `Short` Werts.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Programmiertipps

- **CLS-Kompatibilität.** Der `SByte`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Tet.** Der `SByte`-Datentyp wird auf `Short`, `Integer`, `Long`, `Decimal`, `Single`und `Double`erweitert. Dies bedeutet, dass Sie `SByte` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.

- **Geben Sie Zeichen ein.** `SByte` hat kein Literaltyp Zeichen oder Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.SByte?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
