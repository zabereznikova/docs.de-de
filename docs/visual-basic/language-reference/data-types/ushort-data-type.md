---
title: UShort-Datentyp (Visual Basic)
ms.date: 04/20/2017
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.ushort
helpviewer_keywords:
- numbers [Visual Basic], whole
- literal type characters [Visual Basic], US
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- UShort data type
- US literal type characters [Visual Basic]
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 513e8ce4694788d33c5aa14e34b95e88b6d37ff1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ushort-data-type-visual-basic"></a>UShort-Datentyp (Visual Basic)

Enthält, die 16-Bit (2-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 65.535.  
  
## <a name="remarks"></a>Hinweise

 Verwenden der `UShort` -Datentyp zu groß für Binärdaten enthalten `Byte`.  
  
 Der Standardwert von `UShort` lautet 0.  

# <a name="literal-assignments"></a>Literal Zuweisungen

Sie können deklarieren und Initialisieren einer `UShort` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel Ganzzahlen 65,034, die als dezimale, hexadezimale, dargestellt sind gleich und binäre Literale zugewiesen sind `UShort` Werte.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Numerische Literale zählen auch die `US` oder `us` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `UShort` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H035826us
```

## <a name="programming-tips"></a>Tipps für die Programmierung
  
-   **Negative Zahlen.** Da `UShort` ein Typ ohne Vorzeichen ist es nicht darstellen kann eine negative Zahl. Bei Verwendung der unäres minus (`-`) Operator auf einen Ausdruck, der ausgewertet wird, um geben `UShort`, konvertiert den Ausdruck, der Visual Basic `Integer` erste.  
  
-   **CLS-Kompatibilität.** Die `UShort` Datentyp ist nicht Teil der [Common Language Specification](http://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, die verwendet werden.
  
-   **Widening.** Die `UShort` -Datentyp zu `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `UShort` keinem dieser Typen ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Typzeichen.** Anhängen des Literaltypzeichens `US` an ein Literal wird der `UShort` -Datentyp. `UShort`verfügt über keine Typkennzeichen aus.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.UInt16>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
