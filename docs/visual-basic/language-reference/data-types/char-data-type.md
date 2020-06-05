---
title: Char-Datentyp
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
ms.openlocfilehash: 3dbbf9f6a2c4079775e05f5d2dcd8704c1ec4259
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387477"
---
# <a name="char-data-type-visual-basic"></a>Char-Datentyp (Visual Basic)

Enthält nicht signierte 16-Bit-Code Punkte (2 Bytes), die den Wert von 0 bis 65535 enthalten. Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.

## <a name="remarks"></a>Bemerkungen

Verwenden `Char` Sie den-Datentyp, wenn Sie nur ein einzelnes Zeichen speichern müssen und nicht den mehr Aufwand von benötigen `String` . In einigen Fällen können Sie `Char()` ein Array von-Elementen verwenden, `Char` um mehrere Zeichen zu speichern.

Der Standardwert von `Char` ist das Zeichen mit dem Codepunkt 0.

## <a name="unicode-characters"></a>Unicode-Zeichen

Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur. Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert. Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile. Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen, einschließlich der weltweiten Textzeichen, der Diakritik und mathematischen und technischen Symbolen.

Sie können Methoden wie <xref:System.Char.IsDigit%2A> und für <xref:System.Char.IsPunctuation%2A> eine `Char` Variable verwenden, um die Unicode-Klassifizierung zu bestimmen.

## <a name="type-conversions"></a>Typkonvertierungen

Visual Basic wandelt nicht direkt zwischen `Char` und den numerischen Typen um. Mit der-Funktion oder der-Funktion können Sie <xref:Microsoft.VisualBasic.Strings.Asc%2A> einen- <xref:Microsoft.VisualBasic.Strings.AscW%2A> `Char` Wert in einen-Wert konvertieren, der den zugehörigen `Integer` Codepunkt darstellt Sie können die- <xref:Microsoft.VisualBasic.Strings.Chr%2A> Funktion oder die- <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Funktion verwenden, um einen- `Integer` Wert in einen-Wert zu konvertieren `Char`

Wenn der Schalter für die Typüberprüfung (die [Option Strict-Anweisung) aktiviert](../statements/option-strict-statement.md)ist, müssen Sie das Literaltypzeichen an ein einzelzeichenfolgenliteralzeichen anfügen, um es als `Char` Datentyp zu identifizieren. Dies wird anhand des folgenden Beispiels veranschaulicht. Die erste Zuweisung zur `charVar` Variablen generiert den Compilerfehler [BC30512](../../misc/bc30512.md) , weil `Option Strict` auf ON fest steht. Die zweite wird erfolgreich kompiliert, da das `c` Literaltypzeichen das Literale als- `Char` Wert identifiziert.

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

- **Interop-Überlegungen.** Wenn Sie eine Schnittstelle mit Komponenten, die nicht für die .NET Framework geschrieben wurden, z. b. Automatisierungs-oder COM-Objekte, beachten Sie, dass die Zeichen Typen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es `Byte` `Char` im neuen Visual Basic Code als anstelle von.

- **Tet.** Der- `Char` Datentyp wird zu erweitert `String` . Dies bedeutet, dass Sie `Char` in konvertieren `String` und keinen finden <xref:System.OverflowException?displayProperty=nameWithType> .

- **Geben Sie Zeichen ein.** Das Anfügen des Literaltypzeichens an ein Zeichen folgen- `C` Literalzeichen erzwingt das Zeichen in den- `Char` Datentyp. `Char`hat kein Bezeichnertyp Zeichen.

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Char?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [Datentypen](index.md)
- [String-Datentyp](string-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
