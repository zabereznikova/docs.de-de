---
title: Short-Datentyp (Visual Basic)
ms.date: 01/31/2018
author: rpetrusha
ms.author: ronpet
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: ef99743828d8d80844486b651178622ff45fd554
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="short-data-type-visual-basic"></a>Short-Datentyp (Visual Basic)
Speichert signierte 16-Bit (2-Byte) ganze Zahlen, die im Wert von-32.768 bis 32.767 reichen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `Short` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer`. In einigen Fällen kann die common Language Runtime pack Ihre `Short` Variablen eng zusammen, und speichern Sie den Arbeitsspeicherverbrauch.  
  
 Der Standardwert von `Short` lautet 0.  
  
## <a name="literal-assignments"></a>Literal Zuweisungen

Sie können deklarieren und Initialisieren einer `Short` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel Ganzzahlen 1,034 ab, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale werden implizit konvertiert, aus [Ganzzahl](integer-data-type.md) zu `Short` Werte.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern. Zum Beispiel:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale zählen auch die `S` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `Short` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Tipps für die Programmierung

-   **Widening.** Die `Short` -Datentyp zu `Integer`, `Long`, `Decimal`, `Single`, oder `Double`. Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen. `Short` verfügt über keine Typkennzeichen aus.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

 <xref:System.Int16?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
