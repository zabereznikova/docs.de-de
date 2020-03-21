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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401382"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte-Datentyp (Visual Basic)

Enthält signierte 8-Bit-Ganzzahlen (1 Byte), die einen Wert von -128 bis 127 aufweisen.

## <a name="remarks"></a>Bemerkungen

Verwenden `SByte` Sie den Datentyp, um ganzzahlige Werte zu `Integer` enthalten, die nicht `Short`die volle Datenbreite oder sogar die halbe Datenbreite von erfordern. In einigen Fällen kann die Common Language Runtime Ihre `SByte` Variablen eng zusammenpacken und den Speicherverbrauch sparen.

Der Standardwert von `SByte` lautet 0.

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `SByte` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen.

Im folgenden Beispiel werden `SByte` Ganzzahlen gleich -102, die als Dezimal-, Hexadezimal- und Binärliterale dargestellt werden, Werten zugewiesen. In diesem Beispiel müssen `/removeintchecks` Sie mit dem Compilerschalter kompilieren.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral kein Suffix hat, wird eine [ganze Zahl](integer-data-type.md) abgeleitet. Wenn sich das Ganzzahlliteral außerhalb `Integer` des Bereichs des Typs befindet, wird ein [Long](long-data-type.md) abgeleitet. Dies bedeutet, dass in den vorherigen `0x9A` `0b10011010` Beispielen <xref:System.SByte.MaxValue?displayProperty=nameWithType>die numerischen Literale und als 32-Bit-ganzer Ganzzahlen mit einem Wert von 156 interpretiert werden, der überschreitet. Um Code wie diesen erfolgreich zu kompilieren, der `SByte`einer eine nicht dezimale Ganzzahl zuweist, können Sie eine der folgenden Schritte ausführen:

- Deaktivieren Sie ganzzahlige Begrenzungsprüfungen, `/removeintchecks` indem Sie mit dem Compilerschalter kompilieren.

- Verwenden Sie ein [Typzeichen,](../../programming-guide/language-features/data-types/type-characters.md) um explizit den Literalwert zu definieren, den Sie dem `SByte`zuweisen möchten. Im folgenden Beispiel wird `Short` einem `SByte`ein negativer Literalwert zugewiesen. Beachten Sie, dass bei negativen Zahlen das Bit hoher Ordnung des Hochrangworts des numerischen Literals festgelegt werden muss. Im Falle unseres Beispiels ist dies Bit `Short` 15 des Literalwerts.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Programmiertipps

- **CLS-Compliance.** Der `SByte` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Erweiterung.** Der `SByte` Datentyp wird `Short` `Integer`auf `Long` `Decimal`, `Single`, `Double`, , und erweitert. Dies bedeutet, `SByte` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.

- **Typ Zeichen.** `SByte`hat kein Literaltypzeichen oder Bezeichnertypzeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.SByte?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Ganzzahl-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
