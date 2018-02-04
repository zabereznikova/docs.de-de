---
title: SByte-Datentyp (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d391d7eea27ec7696dbb4c28da8916c744712f32
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="sbyte-data-type-visual-basic"></a>SByte-Datentyp (Visual Basic)

Speichert signierte (1-Byte) 8-Bit-Ganzzahlen, die zwischen-128 bis 127 liegen.  
  
## <a name="remarks"></a>Hinweise

Verwenden der `SByte` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer` oder sogar die halbe Breite der `Short`. In einigen Fällen die common Language Runtime möglicherweise pack Ihre `SByte` Variablen eng zusammen, und speichern Sie den Arbeitsspeicherverbrauch.

Der Standardwert von `SByte` lautet 0.

## <a name="literal-assignments"></a>Literal Zuweisungen
  
Sie können deklarieren und Initialisieren einer `SByte` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal.

Im folgenden Beispiel Ganzzahlen-102, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale zugewiesen sind `SByte` Werte. Dieses Beispiel benötigen Sie, dass beim Kompilieren mit der `/removeintchecks` Compilerschalter.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern. Zum Beispiel:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral ohne Suffix hat eine [Ganzzahl](integer-data-type.md) abgeleitet wird. Integer-literal ist außerhalb des Bereichs der der `Integer` Typ, eine [lange](long-data-type.md) abgeleitet wird. Dies bedeutet, dass in den vorherigen Beispielen, die numerische Literale `0x9A` und `0b10011010` werden als 32-Bit, die mit einem Wert von 156, wodurch überschritten Ganzzahlen mit Vorzeichen interpretiert <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Um Code wie folgt zu kompilieren, die zu eine nicht-Dezimalzahlen Ganzzahl weist eine `SByte`, führen Sie eines der folgenden:

- Grenzen Überprüfungen deaktiviert, durch die Kompilierung mit der `/removeintchecks` Compilerschalter.

- Verwenden einer [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) den literalen Wert explizit zu definieren, die Sie zuweisen möchten die `SByte`. Im folgende Beispiel weist ein negatives Literal `Short` -Wert an ein `SByte`. Beachten Sie, dass für negative Zahlen das höchstwertige Bit von das höherwertige Wort numerisches Literal festgelegt werden muss. Bei unserem Beispiel ist dies bit 15 des Literals `Short` Wert.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Tipps für die Programmierung
  
-   **CLS-Kompatibilität.** Die `SByte` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.

-   **Widening.** Die `SByte` -Datentyp zu `Short`, `Integer`, `Long`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `SByte` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.
  
-   **Typzeichen.** `SByte`hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.
  
## <a name="see-also"></a>Siehe auch

 <xref:System.SByte?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
