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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343855"
---
# <a name="ushort-data-type-visual-basic"></a>Ushort-Datentyp (Visual Basic)

Enthält ganze 16-Bit-Ganzzahlen (2 Bytes) ohne Vorzeichen, die einen Wert von 0 bis 65.535 enthalten.  
  
## <a name="remarks"></a>Hinweise

 Verwenden Sie den Datentyp `UShort`, um Binärdaten zu enthalten, die für `Byte`zu groß sind.  
  
 Der Standardwert von `UShort` lautet 0.  

## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine `UShort` Variable deklarieren und initialisieren, indem Sie Ihr ein dezimales Literalzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `UShort` befindet – sprich, wenn es kleiner als <xref:System.UInt16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.UInt16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden ganze Zahlen gleich 65.034, die als Dezimal-, hexadezimale und binäre Literale dargestellt werden, `UShort` Werten zugewiesen.
  
[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShort)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H`, um eine hexadezimale Literale anzugeben, das Präfix `&b` oder `&B`, um ein binäres Literal anzugeben, und das Präfix `&o` oder `&O`, um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich (`_`) als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[UShort](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UShortS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich (`_`) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As UShort = &H_FF8C
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das `US` oder `us` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `UShort` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_5826us
```

## <a name="programming-tips"></a>Programmiertipps
  
- **Negative Zahlen.** Da `UShort` ein nicht signierter Typ ist, kann er keine negative Zahl darstellen. Wenn Sie den unären Minus-Operator (`-`) für einen Ausdruck verwenden, der als Typ `UShort`ausgewertet wird, konvertiert Visual Basic den Ausdruck zuerst in `Integer`.  
  
- **CLS-Kompatibilität.** Der `UShort`-Datentyp ist nicht Teil des [Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die ihn verwendet.
  
- **Tet.** Der `UShort`-Datentyp wird auf `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single`und `Double`erweitert. Dies bedeutet, dass Sie `UShort` in einen dieser Typen konvertieren können, ohne dass <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftreten.  
  
- **Geben Sie Zeichen ein.** Durch das Anfügen der literalzeichenzeichen, die an ein Literalzeichen `US` werden, wird der Datentyp `UShort` `UShort` hat kein Bezeichnertyp Zeichen.  
  
- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.UInt16>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
