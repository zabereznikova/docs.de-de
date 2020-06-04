---
title: ULong-Datentyp
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
ms.openlocfilehash: ee9297ae917345d44d8e630bd09beea2245b56da
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415517"
---
# <a name="ulong-data-type-visual-basic"></a>ULong-Datentyp (Visual Basic)

Enthält nicht signierte 64-Bit-Ganzzahlen (8 Byte) mit einem Wert von 0 bis 18446744073709551615 (mehr als 1,84 mal 10 ^ 19).

## <a name="remarks"></a>Bemerkungen

Verwenden Sie den- `ULong` Datentyp, um Binärdaten zu enthalten, die zu groß für `UInteger` sind, oder die größtmöglichen ganzzahligen Werte ohne Vorzeichen.

Der Standardwert von `ULong` lautet 0.

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine Variable deklarieren und initialisieren, `ULong` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das- `UL` oder- `ul` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den- `ULong` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `ULong` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus ( `-` )-Operator für einen Ausdruck verwenden, der den Typ ergibt `ULong` , konvertiert Visual Basic den Ausdruck in den `Decimal` ersten.

- **CLS-Kompatibilität.** Der- `ULong` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Typen wie z `ulong` . b. eine andere Daten Breite (32 Bits) in anderen Umgebungen aufweisen können. Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `UInteger` anstelle von `ULong` in Ihrem verwalteten Visual Basic-Code.

  Außerdem werden in Windows 95, Windows 98, Windows Me oder Windows 2000 keine 64-Bit-Ganzzahlen unterstützt. Es ist nicht möglich, ein Visual Basic- `ULong` Argument an eine Automatisierungskomponente auf diesen Plattformen zu übergeben.

- **Tet.** Der `ULong` -Datentyp wird zu `Decimal` , `Single` und erweitert `Double` . Dies bedeutet `ULong` , dass Sie in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.

- **Geben Sie Zeichen ein.** Das Anfügen der Literaltypzeichen `UL` an einen literalvorgang erzwingt den `ULong` Datentyp. `ULong`hat kein Bezeichnertyp Zeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.UInt64>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
