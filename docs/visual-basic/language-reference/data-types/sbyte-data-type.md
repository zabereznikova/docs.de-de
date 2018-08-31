---
title: SByte-Datentyp (Visual Basic)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ab72b2ac2678640697e3cfab426e5a7d6d889a
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43257395"
---
# <a name="sbyte-data-type-visual-basic"></a>SByte-Datentyp (Visual Basic)

Speichert signierte 8-Bit (1-Byte) ganze Zahlen, die im Bereich zwischen-128 und 127 liegen.  
  
## <a name="remarks"></a>Hinweise

Verwenden der `SByte` -Datentyp, um ganzzahlige Werte enthalten, die nicht die gesamten Datenbreite des erfordern `Integer` oder sogar die Hälfte Datenbreite des `Short`. In einigen Fällen die common Language Runtime kann in der Lage, Packen Ihrer `SByte` Variablen, die eng zusammen und Arbeitsspeicher belegt.

Der Standardwert von `SByte` lautet 0.

## <a name="literal-assignments"></a>Zuweisung von literalen
  
Sie können deklarieren und initialisieren eine `SByte` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal.

Im folgenden Beispiel werden Ganzzahlen wie 102, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden zugewiesen, `SByte` Werte. Dieses Beispiel erfordert, dass Sie die Kompilierung mit der `/removeintchecks` Compilerschalter.

[!code-vb[SByte](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByte)]  

> [!NOTE] 
> Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.

[!code-vb[SByteSeparator](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#SByteS)]  

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As SByte = &H_F9
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `SByte` befindet – sprich, wenn es kleiner als <xref:System.SByte.MinValue?displayProperty=nameWithType> oder größer als <xref:System.SByte.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf. Wenn ein Ganzzahlliteral kein Suffix besitzt eine [Ganzzahl](integer-data-type.md) abgeleitet wird. Ist das Ganzzahlliteral außerhalb des Bereichs von der `Integer` Typ eine [lange](long-data-type.md) abgeleitet wird. Das bedeutet, dass in den vorherigen Beispielen, die die numerischen Literale `0x9A` und `0b10011010` werden als 32-Bit-Ganzzahlen mit Vorzeichen mit einem Wert von 156, überschreitet interpretiert <xref:System.SByte.MaxValue?displayProperty=nameWithType>. Um Code wie den folgenden zu kompilieren, die eine nicht-Dezimalzahlen ganze Zahl, und weist eine `SByte`, führen Sie einen der folgenden:

- Deaktivieren Sie die Grenzen Überprüfung ganzer Zahlen durch die Kompilierung mit der `/removeintchecks` Compilerschalter.

- Verwenden einer [Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) , den literalen Wert explizit zu definieren, die Sie zuweisen möchten die `SByte`. Das folgende Beispiel weist ein negatives Literal `Short` -Werts in einen `SByte`. Beachten Sie, dass für negative Zahlen, das höchstwertige Bit von das höherwertige Wort des numerischen Literals muss festgelegt werden. Bei unserem Beispiel ist dies bit 15 des Literals `Short` Wert.

   [!code-vb[SByteTypeChars](../../../../samples/snippets/visualbasic/language-reference/data-types/sbyte-assignment.vb#1)]

## <a name="programming-tips"></a>Tipps für die Programmierung
  
-   **CLS-Kompatibilität.** Die `SByte` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.

-   **Erweiternde.** Die `SByte` -Datentyp wird zu `Short`, `Integer`, `Long`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `SByte` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.
  
-   **Typzeichen.** `SByte` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=nameWithType>-Struktur.
  
## <a name="see-also"></a>Siehe auch

 <xref:System.SByte?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)  
 [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
