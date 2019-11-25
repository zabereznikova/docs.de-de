---
title: Long-Datentyp
ms.date: 01/31/2018
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
ms.openlocfilehash: 16d7409c802e97b1f33474d810134db4d9f0ad6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343975"
---
# <a name="long-data-type-visual-basic"></a>Long data type (Visual Basic)

Holds signed 64-bit (8-byte) integers ranging in value from -9,223,372,036,854,775,808 through 9,223,372,036,854,775,807 (9.2...E+18).

## <a name="remarks"></a>Hinweise

Use the `Long` data type to contain integer numbers that are too large to fit in the `Integer` data type.

Der Standardwert von `Long` lautet 0.

## <a name="literal-assignments"></a>Literal assignments

You can declare and initialize a `Long` variable by assigning it a decimal literal, a hexadecimal literal, an octal literal, or (starting with Visual Basic 2017) a binary literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Long` befindet – sprich, wenn es kleiner als <xref:System.Int64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 4294967296, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Long`-Werten zugewiesen.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Long)]

> [!NOTE]
> You use the prefix `&h` or `&H` to denote a hexadecimal literal, the prefix `&b` or `&B` to denote a binary literal, and the prefix `&o` or `&O` to denote an octal literal. Dezimale Literale haben kein Präfix.

Starting with Visual Basic 2017, you can also use the underscore character, `_`, as a digit separator to enhance readability, as the following example shows.

[!code-vb[long](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Starting with Visual Basic 15.5, you can also use the underscore character (`_`) as a leading separator between the prefix and the hexadecimal, binary, or octal digits. Beispiel:

```vb
Dim number As Long = &H_0FAC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numeric literals can also include the `L` [type character](../../programming-guide/language-features/data-types/type-characters.md) to denote the `Long` data type, as the following example shows.

```vb
Dim number = &H_0FAC_0326_1489_D68CL
```

## <a name="programming-tips"></a>Programmiertipps

- **Interop Considerations.** If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that `Long` has a different data width (32 bits) in other environments. If you are passing a 32-bit argument to such a component, declare it as `Integer` instead of `Long` in your new Visual Basic code.

- **Widening.** The `Long` data type widens to `Decimal`, `Single`, or `Double`. Dies bedeutet, dass Sie `Long` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.

- **Type Characters.** Durch Anhängen des Literaltypzeichens `L` an ein Literal wird der `Long`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `&` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Long`-Datentyp erzwungen.

- **Framework Type.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int64?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.Int64>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
