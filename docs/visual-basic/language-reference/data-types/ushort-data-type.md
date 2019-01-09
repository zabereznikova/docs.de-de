---
title: UShort-Datentyp (Visual Basic)
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
ms.openlocfilehash: f1ccb2f2e297ecac8f5ac96c0af42ff6bfb9363b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146042"
---
# <a name="ushort-data-type-visual-basic"></a>UShort-Datentyp (Visual Basic)

Enthält 16-Bit (2-Byte)-Ganzzahlen ohne Vorzeichen im Bereich von 0 bis 65.535.  
  
## <a name="remarks"></a>Hinweise

 Verwenden der `UShort` Datentyp zu groß für die Binärdaten enthält `Byte`.  
  
 Der Standardwert von `UShort` lautet 0.  

# <a name="literal-assignments"></a>Zuweisung von literalen

Sie können deklarieren und initialisieren eine `UShort` Variable, indem Sie ihm ein dezimales Literal, ein hexadezimales Literal ein oktales Literal, zuweisen oder (beginnend mit Visual Basic 2017) ein binäres Literal. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 65.034, die als dezimale, hexadezimale Werte dargestellt werden und binäre Literale werden zugewiesen, `UShort` Werte.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` um anzugeben, ein hexadezimales Literal, das Präfix `&b` oder `&B` um ein binäres Literal und das Präfix anzugeben `&o` oder `&O` um ein oktales Literal zu kennzeichnen. Dezimale Literale haben kein Präfix.

Starten Visual Basic 2017, Sie können auch den Unterstrich, `_`, als Zifferntrennzeichen zum Verbessern der Lesbarkeit, wie im folgenden Beispiel gezeigt.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Ab Visual Basic 15.5 können Sie können auch den Unterstrich (`_`) als vorangestelltes Trennzeichen zwischen Präfix und die Ziffern hexadezimalen, Binär- oder Oktalziffern. Zum Beispiel:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch einschließen, die `US` oder `us` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) zur Angabe der `UShort` -Datentyp, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Tipps für die Programmierung
  
-   **Negative Zahlen.** Da `UShort` ein Typ ohne Vorzeichen, kann er eine negative Zahl ist keine darstellen. Bei Verwendung der unäres minus (`-`) Operator auf ein Ausdruck, der ausgewertet wird, um geben `UShort`, konvertiert den Ausdruck, der Visual Basic `Integer` erste.  
  
-   **CLS-Kompatibilität.** Die `UShort` Datentyp ist nicht Teil der [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, der verwendet wird.
  
-   **Erweiternde.** Die `UShort` -Datentyp wird zu `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`, und `Double`. Dies bedeutet, Sie können konvertieren `UShort` in alle diese Typen unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `US` an ein Literal wird der `UShort` -Datentyp. `UShort` verfügt über keine Typkennzeichen aus.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.UInt16>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
