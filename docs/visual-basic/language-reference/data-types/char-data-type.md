---
title: Char-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Char
helpviewer_keywords:
- literal type characters [Visual Basic], C
- Char data type
- C literal type character [Visual Basic]
- data types [Visual Basic], assigning
- Char data type [Visual Basic], character literals
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
ms.openlocfilehash: 8313c2282a3b4b7b035f9f3b685a786c4471f53a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630145"
---
# <a name="char-data-type-visual-basic"></a>Char-Datentyp (Visual Basic)

Enthält nicht signierte 16-Bit-Code Punkte (2 Bytes), die den Wert von 0 bis 65535 enthalten. Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.

## <a name="remarks"></a>Hinweise

Verwenden Sie `Char` den-Datentyp, wenn Sie nur ein einzelnes Zeichen speichern müssen und nicht den mehr Aufwand `String`von benötigen. In einigen Fällen können Sie ein `Char()`Array von `Char` -Elementen verwenden, um mehrere Zeichen zu speichern.

Der Standardwert von `Char` ist das Zeichen mit dem Codepunkt 0.

## <a name="unicode-characters"></a>Unicode-Zeichen

Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur. Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert. Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile. Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen, einschließlich der weltweiten Textzeichen, der Diakritik und mathematischen und technischen Symbolen.

Sie können Methoden wie <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> für eine `Char` Variable verwenden, um die Unicode-Klassifizierung zu bestimmen.

## <a name="type-conversions"></a>Typkonvertierungen

Visual Basic wandelt nicht direkt zwischen `Char` und den numerischen Typen um. Mit der-Funktion <xref:Microsoft.VisualBasic.Strings.Asc%2A> oder <xref:Microsoft.VisualBasic.Strings.AscW%2A> der-Funktion können `Char` Sie einen- `Integer` Wert in einen-Wert konvertieren, der den zugehörigen Codepunkt darstellt Sie können die- <xref:Microsoft.VisualBasic.Strings.Chr%2A> Funktion <xref:Microsoft.VisualBasic.Strings.ChrW%2A> oder die-Funktion `Integer` verwenden, um `Char` einen-Wert in einen-Wert zu konvertieren

Wenn der Schalter für die Typüberprüfung (die [Option Strict-Anweisung) aktiviert](../../../visual-basic/language-reference/statements/option-strict-statement.md)ist, müssen Sie das Literaltypzeichen an ein einzelzeichenfolgenliteralzeichen `Char` anfügen, um es als Datentyp zu identifizieren. Dies wird anhand des folgenden Beispiels veranschaulicht. Die erste Zuweisung zur `charVar` Variablen generiert den Compilerfehler [BC30512](../../misc/bc30512.md) , weil `Option Strict` auf ON fest steht. Die zweite wird erfolgreich kompiliert, da `c` das Literaltypzeichen das Literale `Char` als-Wert identifiziert.

```vb
Option Strict On

Module CharType
    Public Sub Main()
        Dim charVar As Char

        ' This statement generates compiler error BC30512 because Option Strict is On.  
        charVar = "Z"  

        ' The following statement succeeds because it specifies a Char literal.  
        charVar = "Z"c
    End Sub
End Module
```

## <a name="programming-tips"></a>Programmiertipps

- **Negative Zahlen.** `Char`ist ein nicht signierter Typ und kann keinen negativen Wert darstellen. In jedem Fall sollten Sie nicht verwenden `Char` , um numerische Werte zu speichern.

- **Interop-Überlegungen.** Wenn Sie eine Schnittstelle mit Komponenten, die nicht für die .NET Framework geschrieben wurden, z. b. Automatisierungs-oder COM-Objekte, beachten Sie, dass die Zeichen Typen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren `Byte` Sie es `Char` im neuen Visual Basic Code als anstelle von.

- **Tet.** Der `Char` -Datentyp wird zu `String`erweitert. Dies bedeutet, dass Sie `Char` in `String` konvertieren <xref:System.OverflowException?displayProperty=nameWithType>und keinen finden.

- **Geben Sie Zeichen ein.** Das Anfügen des Literaltypzeichens an ein Zeichen folgen-Literalzeichen erzwingt das Zeichen `C` in den `Char` -Datentyp. `Char`hat kein Bezeichnertyp Zeichen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Siehe auch

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
