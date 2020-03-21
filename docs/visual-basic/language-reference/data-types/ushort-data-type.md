---
title: UShort-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.ushort
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
ms.openlocfilehash: 7cdbd5fb192fd5cc1be6260dcdcdb1f30cf3f865
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401310"
---
# <a name="ushort-data-type-visual-basic"></a>UKurzer Datentyp (Visual Basic)

Enthält nicht signierte 16-Bit-Ganzzahlen (2-Byte) im Wert von 0 bis 65.535.  
  
## <a name="remarks"></a>Bemerkungen

 Verwenden `UShort` Sie den Datentyp, um `Byte`Binärdaten zu groß für zu enthalten.  
  
 Der Standardwert von `UShort` lautet 0.  

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `UShort` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden `UShort` Ganzzahlen von 65.034, die als Dezimal-, Hexadezimal- und Binärliterale dargestellt werden, Werten zugewiesen.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können `US` auch `us` das oder [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UShort` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Programmiertipps
  
- **Negative Zahlen.** Da `UShort` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen. Wenn Sie den Operator`-`unary minus ( ) für `UShort`einen Ausdruck verwenden, `Integer` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.  
  
- **CLS-Compliance.** Der `UShort` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.
  
- **Erweiterung.** Der `UShort` Datentyp wird `Integer` `UInteger`auf `Long` `ULong`, `Decimal` `Single`, `Double`, , , und erweitert. Dies bedeutet, `UShort` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.  
  
- **Typ Zeichen.** Das Anfügen der `US` Literaltypzeichen an `UShort` ein Literal erzwingt, dass es an den Datentyp gebunden wird. `UShort`hat kein Bezeichnertypzeichen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.UInt16>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
