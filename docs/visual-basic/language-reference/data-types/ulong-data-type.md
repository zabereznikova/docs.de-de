---
title: ULong-Datentyp (Visual Basic)
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
ms.openlocfilehash: 82a2badc1bb22a55f753c9075562db3a5ee0d234
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61747083"
---
# <a name="ulong-data-type-visual-basic"></a>ULong-Datentyp (Visual Basic)

64-Bit (8 Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 18.446.744.073.709.551.615 enthält (mehr als 1,84 Mal 10 ^ 19).  
  
## <a name="remarks"></a>Hinweise

Verwenden der `ULong` Datentyp zu groß für die Binärdaten enthält `UInteger`, oder die größten möglichen unsigned Integer-Werte.  
  
Der Standardwert von `ULong` lautet 0.

## <a name="literal-assignments"></a>Zuweisung von literalen

Sie können deklarieren und initialisieren eine `ULong` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `ULong` befindet – sprich, wenn es kleiner als <xref:System.UInt64.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt64.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 7.934.076.125, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `ULong`-Werten zugewiesen.
  
[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ULong)]

> [!NOTE] 
> Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.

[!code-vb[ULong](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#LongS)]

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As ULong = &H_F9AC_0326_1489_D68C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch einschließen, die `UL` oder `ul` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `ULong` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_00_00_0A_96_2F_AC_14_D7ul
```

## <a name="programming-tips"></a>Tipps für die Programmierung
  
- **Negative Zahlen.** Da `ULong` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen. Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `ULong`, konvertiert den Ausdruck, der Visual Basic `Decimal` erste.  
  
- **CLS-Kompatibilität.** Die `ULong` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.  
  
- **Interop-Überlegungen.** Wenn Sie anbinden, Komponenten, die nicht für .NET Framework, z. B. Automatisierungs- oder COM-Objekte, geschriebenen müssen bedenken, die Typen wie `ulong` kann in anderen Umgebungen über eine andere Datenbreite (32 Bit) verfügen. Wenn Sie ein 32-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UInteger` anstelle von `ULong` in verwaltetem Visual Basic-Code.  
  
     Automation unterstützt darüber hinaus keine 64-Bit-Ganzzahlen auf Windows 95, Windows 98, Windows ME oder Windows 2000. Sie können keine übergeben, eine Visual Basic `ULong` Argument an eine Automatisierungskomponente auf diesen Plattformen.  
  
- **Erweiternde.** Die `ULong` -Datentyp wird zu `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `ULong` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
- **Typzeichen.** Durch Anhängen des Literaltypzeichens `UL` an ein Literal wird der `ULong` -Datentyp. `ULong` verfügt über keine Typkennzeichen aus.
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.UInt64>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
