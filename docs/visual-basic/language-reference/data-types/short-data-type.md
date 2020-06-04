---
title: Short-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Short
helpviewer_keywords:
- numbers [Visual Basic], whole
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- data types [Visual Basic], integral
- S literal type character [Visual Basic]
- Short data type
- literal type characters [Visual Basic], S
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
ms.openlocfilehash: 176d27c86127dac1d9c9c0231790f7a5c2a2fefc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415556"
---
# <a name="short-data-type-visual-basic"></a>Short-Datentyp (Visual Basic)

Enthält ganze 16-Bit-Zahlen (2 Bytes) mit Vorzeichen, die den Wert von-32.768 bis 32.767 über liegen.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie den- `Short` Datentyp, um ganzzahlige Werte zu enthalten, die nicht die vollständige Daten Breite von erfordern `Integer` . In einigen Fällen können die Common Language Runtime die `Short` Variablen eng zusammenpacken und den Speicherverbrauch verbrauchen.  
  
 Der Standardwert von `Short` lautet 0.  
  
## <a name="literal-assignments"></a>Literalzuweisungen

Sie können eine Variable deklarieren und initialisieren, `Short` indem Sie Ihr ein Dezimaltrennzeichen, ein hexadezimales Literalzeichen, ein Oktalliterale oder (beginnend mit Visual Basic 2017) ein binäres Literalzeichen zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden ganze Zahlen gleich 1.034, die als Dezimale, hexadezimale und binäre Literale dargestellt werden, implizit von [ganzzahligen](integer-data-type.md) Werten in- `Short` Werte konvertiert.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Sie verwenden das Präfix `&h` oder `&H` , um ein hexadezimales Literalzeichen, das Präfix `&b` oder `&B` ein binäres Literalformat anzugeben, oder das Präfix `&o` oder `&O` , um ein Oktalliteral anzugeben. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch den Unterstrich () `_` als Ziffern Trennzeichen verwenden, um die Lesbarkeit zu verbessern, wie im folgenden Beispiel gezeigt.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Beginnend mit Visual Basic 15,5 können Sie auch den Unterstrich ( `_` ) als vorangeführtem Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können auch das `S` [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Short` Datentyp anzugeben, wie im folgenden Beispiel gezeigt.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Programmiertipps

- **Tet.** Der- `Short` Datentyp wird zu `Integer` , `Long` , `Decimal` , `Single` oder erweitert `Double` . Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.  
  
- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen. `Short`hat kein Bezeichnertyp Zeichen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Int16?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Integer-Datentyp](integer-data-type.md)
- [Long-Datentyp](long-data-type.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
