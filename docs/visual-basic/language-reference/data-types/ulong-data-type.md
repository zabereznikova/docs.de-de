---
title: ULong-Datentyp (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b0137f0f33abfdb3f03758323edeaa63ac60117
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ulong-data-type-visual-basic"></a>ULong-Datentyp (Visual Basic)

Enthält die 64-Bit (8 Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 18.446.744.073.709.551.615 (mehr als 1,84 Mal 10 ^ 19).  
  
## <a name="remarks"></a>Hinweise

Verwenden der `ULong` -Datentyp zu groß für Binärdaten enthalten `UInteger`, oder der größtmögliche unsigned Integer-Werte.  
  
Der Standardwert von `ULong` lautet 0.

## <a name="literal-assignments"></a>Literal Zuweisungen

Sie können deklarieren und Initialisieren einer `ULong` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern. Zum Beispiel:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale zählen auch die `UL` oder `ul` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `ULong` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Tipps für die Programmierung
  
-   **Negative Zahlen.** Da `ULong` ein Typ ohne Vorzeichen ist es nicht darstellen kann eine negative Zahl. Bei Verwendung der unäres minus (`-`) Operator auf einen Ausdruck, der ausgewertet wird, um geben `ULong`, konvertiert den Ausdruck, der Visual Basic `Decimal` erste.  
  
-   **CLS-Kompatibilität.** Die `ULong` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.  
  
-   **Interop-Überlegungen.** Wenn Sie Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen Datenbreite bedenken, die z. B. Typen `ulong` können in anderen Umgebungen eine andere Datenbreite (32 Bit). Wenn Sie eine 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UInteger` anstelle von `ULong` im verwalteten Visual Basic-Code.  
  
     Darüber hinaus unterstützt Automatisierung keine 64-Bit-Ganzzahlen unter Windows 95, Windows 98, Windows ME bzw. Windows 2000. Sie können nicht übergeben, eine Visual Basic `ULong` Argument an eine Automatisierungskomponente auf diesen Plattformen.  
  
-   **Widening.** Die `ULong` -Datentyp zu `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `ULong` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Typzeichen.** Anhängen des Literaltypzeichens `UL` an ein Literal wird der `ULong` -Datentyp. `ULong` verfügt über keine Typkennzeichen aus.
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

 <xref:System.UInt64>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
