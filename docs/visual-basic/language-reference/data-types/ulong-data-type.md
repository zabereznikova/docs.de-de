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
ms.openlocfilehash: 3c6cd4086e08b808c158948756b4806f098196b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401316"
---
# <a name="ulong-data-type-visual-basic"></a>ULong-Datentyp (Visual Basic)

Enthält ganze Zahlen mit nicht signierten 64-Bit-Ganzzahlen von 0 bis 18.446.744.073.709.551.615 (mehr als 1,84 mal 10 x 19).

## <a name="remarks"></a>Bemerkungen

Verwenden `ULong` Sie den Datentyp, um `UInteger`Binärdaten zu groß für oder die größtmöglichen ganzzahligen Nichtsigniertenwerte zu enthalten.

Der Standardwert von `ULong` lautet 0.

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `ULong` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können `UL` auch `ul` das oder [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `ULong` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** Da `ULong` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen. Wenn Sie den Operator`-`unary minus ( ) für `ULong`einen Ausdruck verwenden, `Decimal` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.

- **CLS-Compliance.** Der `ULong` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für .NET Framework geschrieben wurden, `ulong` z. B. Automatisierungs- oder COM-Objekte, beachten Sie, dass Typen wie z. B. eine andere Datenbreite (32 Bit) in anderen Umgebungen aufweisen können. Wenn Sie ein 32-Bit-Argument an eine solche `UInteger` Komponente `ULong` übergeben, deklarieren Sie es als anstelle von ihrem verwalteten Visual Basic-Code.

  Darüber hinaus unterstützt Automation keine 64-Bit-Ganzzahlen unter Windows 95, Windows 98, Windows ME oder Windows 2000. Sie können ein `ULong` Visual Basic-Argument nicht an eine Automatisierungskomponente auf diesen Plattformen übergeben.

- **Erweiterung.** Der `ULong` Datentyp wird `Decimal` `Single`auf `Double`, und erweitert. Dies bedeutet, `ULong` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.

- **Typ Zeichen.** Das Anfügen der `UL` Literaltypzeichen an `ULong` ein Literal erzwingt, dass es an den Datentyp gebunden wird. `ULong`hat kein Bezeichnertypzeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.UInt64>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
