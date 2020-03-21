---
title: Integer-Datentyp
ms.date: 01/31/2018
f1_keywords:
- vb.Integer
- Integer
helpviewer_keywords:
- numbers [Visual Basic], whole
- enumerated values [Visual Basic]
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- literal type characters [Visual Basic], I
- integers [Visual Basic], types
- data types [Visual Basic], integral
- '% identifier type character'
- data types [Visual Basic], assigning
- identifier type characters [Visual Basic], %
- I literal type character [Visual Basic]
- Integer data type
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
ms.openlocfilehash: c5b1041b8ef0ca9898a846fea03888537bb4abbf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401346"
---
# <a name="integer-data-type-visual-basic"></a>Ganzzahl-Datentyp (Visual Basic)

Speichert 32-Bit-(4-Byte-)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von -2.147.483.648 bis einschließlich 2.147.483.647 bewegen.  
  
## <a name="remarks"></a>Bemerkungen

 Der `Integer`-Datentyp bietet in Verbindung mit einem 32-Bit-Prozessor eine optimale Leistung. Die anderen ganzzahligen Typen werden langsamer in den Arbeitsspeicher geladen und im Arbeitsspeicher gespeichert bzw. langsamer aus dem Arbeitsspeicher geladen.  
  
 Der Standardwert von `Integer` lautet 0.  

## <a name="literal-assignments"></a>Literale Zuweisungen

Sie können eine `Integer` Variable deklarieren und initialisieren, indem Sie ihr ein Dezimalliteral, ein hexadezimales Literal, ein Oktalliteral oder (beginnend mit Visual Basic 2017) ein binäres Literal zuweisen. Wenn Sich das Ganzzahlliteral außerhalb des Bereichs von `Integer` befindet – sprich, wenn es kleiner als <xref:System.Int32.MinValue?displayProperty=nameWithType> oder größer als <xref:System.Int32.MaxValue?displayProperty=nameWithType> ist – tritt ein Kompilierfehler auf.

Im folgenden Beispiel werden Ganzzahlen wie 90.946, die als dezimale, hexadezimale und binäre Literale dargestellt werden, den `Integer`-Werten zugewiesen.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#Int)]  

> [!NOTE]
> Sie verwenden das `&h` `&H` Präfix oder bezeichnen ein hexadezimales Literal, `&b` das Präfix oder `&B` `&o` um `&O` ein binäres Literal und das Präfix zu bezeichnen oder ein oktales Literal zu bezeichnen. Dezimale Literale haben kein Präfix.

Ab Visual Basic 2017 können Sie auch das `_`Unterstrichzeichen , als Zifferntrennzeichen verwenden, um die Lesbarkeit zu verbessern, wie das folgende Beispiel zeigt.

[!code-vb[integer](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#IntS)]  

Ab Visual Basic 15.5 können Sie auch das`_`Unterstrichzeichen ( ) als führendes Trennzeichen zwischen dem Präfix und den hexadezimalen, binären oder oktalen Ziffern verwenden. Beispiel:

```vb
Dim number As Integer = &H_C305_F860
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

Numerische Literale können `I` auch das [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md) enthalten, um den `Integer` Datentyp zu bezeichnen, wie das folgende Beispiel zeigt.

```vb
Dim number = &H_035826I
```

## <a name="programming-tips"></a>Programmiertipps

- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für .NET Framework `Integer` geschrieben wurden, z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass diese in anderen Umgebungen eine andere Datenbreite (16 Bit) aufweisen. Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic-Code als `Short` und nicht als `Integer`.  
  
- **Erweiterung.** Der `Integer`-Datentyp wird zu `Long`, `Decimal`, `Single` oder `Double` erweitert. Dies bedeutet, dass Sie `Integer` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.  
  
- **Typ Zeichen.** Durch Anhängen des Literaltypzeichens `I` an ein Literal wird der `Integer`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `%` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Integer`-Datentyp erzwungen.  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int32?displayProperty=nameWithType>-Struktur.  
  
## <a name="range"></a>Range

Wenn Sie für eine Variable mit Ganzzahltyp eine Zahl festlegen, die außerhalb des Bereichs für diesen Typ liegt, tritt ein Fehler auf. Wenn Sie versuchen, sie auf einen Bruch festzulegen, wird die Zahl auf den nächsten ganzzahligen Wert auf- oder abgerundet. Wenn die Zahl zwei Ganzzahlwerten gleichermaßen nahe ist, wird der Wert auf die nächste gerade ganze Zahl gerundet. So werden Rundungsfehler reduziert, die sich beim einheitlichen Runden von in der Mitte liegenden Werten in nur eine Richtung ergeben. Der folgende Code zeigt Beispiele für eine Rundung.  

```vb  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Int32?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)
- [Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
