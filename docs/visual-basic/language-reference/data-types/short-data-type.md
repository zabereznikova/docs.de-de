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
ms.openlocfilehash: 8dfdfb56de32e4b3a96729b09ccf46a6fee9a424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401340"
---
# <a name="short-data-type-visual-basic"></a>Kurzer Datentyp (Visual Basic)

Enthält signierte 16-Bit-Ganzzahlen (2 Byte), die im Wert von -32.768 bis 32.767 liegen.  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden `Short` Sie den Datentyp, um ganzzahlige Werte zu `Integer`enthalten, die nicht die volle Datenbreite von erfordern. In einigen Fällen kann die Common `Short` Language Runtime Ihre Variablen eng zusammenpacken und den Speicherverbrauch sparen.  
  
 Der Standardwert von `Short` lautet 0.  
  
## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `Short` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Short` befindet – sprich, wenn es kleiner als <xref:System.Int16.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int16.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden ganze Zahlen gleich 1.034, die als Dezimal-, Hexadezimal- und Binärliterale dargestellt werden, implizit von [Ganzzahl](integer-data-type.md) in `Short` Werte konvertiert.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Short)]

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[Short](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#ShortS)]

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Short = &H_3264
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können `S` auch das [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Short` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.

```vb
Dim number = &H_3264S
```

## <a name="programming-tips"></a>Programmiertipps

- **Erweiterung.** Der `Short` Datentyp wird `Integer` `Long`auf `Decimal` `Single`, `Double`, , oder erweitert. Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.  
  
- **Typ Zeichen.** Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`-Datentyp erzwungen. `Short`hat kein Bezeichnertypzeichen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Int16?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Ganzzahl-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
