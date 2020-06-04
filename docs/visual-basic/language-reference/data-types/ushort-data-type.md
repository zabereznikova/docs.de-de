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
ms.openlocfilehash: ee31156e00059699125fd72a7f091afbb21beab0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415478"
---
# <a name="ushort-data-type-visual-basic"></a>Ushort-Datentyp (Visual Basic)

Enthält ganze 16-Bit-Ganzzahlen (2 Bytes) ohne Vorzeichen, die einen Wert von 0 bis 65.535 enthalten.  
  
## <a name="remarks"></a>Bemerkungen

 Verwenden Sie den- `UShort` Datentyp, um Binärdaten aufzunehmen, die zu groß für sind `Byte` .  
  
 Der Standardwert von `UShort` lautet 0.  

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine Variable deklarieren und initialisieren, `UShort` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden ganze Zahlen gleich 65.034, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, den- `UShort` Werten zugewiesen.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das- `US` oder- `us` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den- `UShort` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Programmiertipps
  
- **Negative Zahlen.** Da `UShort` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus ( `-` )-Operator für einen Ausdruck verwenden, der den Typ ergibt `UShort` , konvertiert Visual Basic den Ausdruck in den `Integer` ersten.  
  
- **CLS-Kompatibilität.** Der- `UShort` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.
  
- **Tet.** Der `UShort` -Datentyp wird zu `Integer` , `UInteger` , `Long` , `ULong` , `Decimal` , `Single` und erweitert `Double` . Dies bedeutet `UShort` , dass Sie in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.  
  
- **Geben Sie Zeichen ein.** Das Anfügen der Literaltypzeichen `US` an einen literalvorgang erzwingt den `UShort` Datentyp. `UShort`hat kein Bezeichnertyp Zeichen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.UInt16>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
