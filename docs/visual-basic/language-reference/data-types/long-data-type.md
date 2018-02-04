---
title: Long-Datentyp (Visual Basic)
ms.date: 01/31/2018
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cf03afc6b2e77ccca74fc26365fc50110e1f71
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="long-data-type-visual-basic"></a>Long-Datentyp (Visual Basic)

Speichert signierte 64-Bit (8 Byte) ganze Zahlen im Bereich von -9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 (9.2... E + 18).  
  
## <a name="remarks"></a>Hinweise

 Verwenden der `Long` -Datentyp, um ganze Zahlen enthalten, die zu groß für sind die `Integer` -Datentyp.  
  
 Der Standardwert von `Long` lautet 0.

## <a name="literal-assignments"></a>Literal Zuweisungen 

Sie können deklarieren und Initialisieren einer `Long` Variable, indem ein decimal Literal, einen hexadezimalen Literalwert ein oktales Literal Vorlagenkörpers oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Long` befindet – sprich, wenn es kleiner als <xref:System.Int64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Long`-Werten zugewiesen.
  
[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]  

> [!NOTE]
> Verwenden Sie das Präfix `&h` oder `&H` zur Angabe einer hexadezimalen Literalwert, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix zu bezeichnen `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Beginnend mit Visual Basic 2017, Sie können auch den Unterstrich `_`, als Ziffer Trennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel dargestellt.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Beginnend mit Visual Basic 15.5, Sie können auch das Unterstrich-Zeichen (`_`) als führende Trennzeichen zwischen Präfix und die, binäre oktalen oder hexadezimalen Ziffern. Zum Beispiel:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale zählen auch die `L` [-Typzeichen](../../programming-guide\language-features\data-types/type-characters.md) zur Angabe der `Long` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Tipps für die Programmierung

-   **Interop-Überlegungen.** Wenn Sie Komponenten für .NET Framework, z. B. Automatisierungs- oder COM-Objekte nicht geschrieben anbinden, müssen Sie beachten, dass `Long` verfügt über eine andere Datenbreite (32 Bit) in anderen Umgebungen. Wenn Sie eine 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Integer` anstelle von `Long` im neuen Visual Basic-Code.  
  
-   **Widening.** Die `Long` -Datentyp zu `Decimal`, `Single`, oder `Double`. Dies bedeutet, dass Sie `Long` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `L` an ein Literal wird der `Long`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `&` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Long`-Datentyp erzwungen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int64?displayProperty=nameWithType>-Struktur.  

## <a name="see-also"></a>Siehe auch

<xref:System.Int64>[-Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
[Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
[Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)   
[Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
[Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
[Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
