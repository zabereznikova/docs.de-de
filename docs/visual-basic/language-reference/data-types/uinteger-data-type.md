---
title: UInteger-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: ccff61608aed797734cb4f5ca0571d7ed73ba98b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401376"
---
# <a name="uinteger-data-type"></a>UInteger-Datentyp

Enthält ganze Zahlen mit nicht signierten 32-Bit-Dateien (4-Byte) im Wert von 0 bis 4.294.967.295.

## <a name="remarks"></a>Bemerkungen

Der `UInteger` Datentyp stellt den größten nicht signierten Wert in der effizientesten Datenbreite bereit.

Der Standardwert von `UInteger` lautet 0.

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `UInteger` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UInteger` befindet – sprich, wenn es kleiner als <xref:System.UInt32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 3.000.000.000, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `UInteger`-Werten zugewiesen.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können `UI` auch `ui` das oder [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UInteger` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>Programmiertipps

Die `UInteger` `Integer` und Datentypen bieten eine optimale Leistung auf einem 32-Bit-Prozessor, da die kleineren Ganzzahltypen (`UShort`, `Short`, `Byte`und `SByte`) mehr Zeit zum Laden, Speichern und Abrufen in Anspruch nehmen, obwohl sie weniger Bits verwenden.

- **Negative Zahlen.** Da `UInteger` es sich um einen nicht signierten Typ handelt, kann er keine negative Zahl darstellen. Wenn Sie den Operator`-`unary minus ( ) für `UInteger`einen Ausdruck verwenden, `Long` der als Typ ausgewertet wird, konvertiert Visual Basic den Ausdruck in den ersten.

- **CLS-Compliance.** Der `UInteger` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für .NET Framework geschrieben wurden, `uint` z. B. Automatisierungs- oder COM-Objekte, beachten Sie, dass Typen wie z. B. eine andere Datenbreite (16 Bit) in anderen Umgebungen aufweisen können. Wenn Sie ein 16-Bit-Argument an eine solche `UShort` Komponente `UInteger` übergeben, deklarieren Sie es als anstelle von ihrem verwalteten Visual Basic-Code.

- **Erweiterung.** Der `UInteger` Datentyp wird `Long` `ULong`auf `Decimal` `Single`, `Double`, , und erweitert. Dies bedeutet, `UInteger` dass Sie in einen <xref:System.OverflowException?displayProperty=nameWithType> dieser Typen konvertieren können, ohne auf einen Fehler zu stoßen.

- **Typ Zeichen.** Das Anfügen der `UI` Literaltypzeichen an `UInteger` ein Literal erzwingt, dass es an den Datentyp gebunden wird. `UInteger`hat kein Bezeichnertypzeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.UInt32>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
