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
ms.openlocfilehash: 1ed5b19a307d094fc1d5a6bb0251c57052dc9bc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344050"
---
# <a name="char-data-type-visual-basic"></a>Char-Datentyp (Visual Basic)

Enthält nicht signierte 16-Bit-Code Punkte (2 Bytes), die den Wert von 0 bis 65535 enthalten. Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.

## <a name="remarks"></a>Hinweise

Verwenden Sie den `Char`-Datentyp, wenn Sie nur ein einzelnes Zeichen speichern müssen und den Aufwand `String`nicht benötigen. In einigen Fällen können Sie `Char()`, ein Array von `Char` Elementen, verwenden, um mehrere Zeichen zu speichern.

Der Standardwert von `Char` ist das Zeichen mit dem Codepunkt 0.

## <a name="unicode-characters"></a>Unicode-Zeichen

Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur. Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert. Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile. Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen, einschließlich der weltweiten Textzeichen, der Diakritik und mathematischen und technischen Symbolen.

Sie können Methoden wie <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> für eine `Char` Variable verwenden, um die Unicode-Klassifizierung zu bestimmen.

## <a name="type-conversions"></a>Typkonvertierungen

Visual Basic wandelt nicht direkt zwischen `Char` und den numerischen Typen um. Mit der <xref:Microsoft.VisualBasic.Strings.Asc%2A>-oder <xref:Microsoft.VisualBasic.Strings.AscW%2A>-Funktion können Sie einen `Char` Wert in einen `Integer` konvertieren, der den zugehörigen Codepunkt darstellt. Sie können die <xref:Microsoft.VisualBasic.Strings.Chr%2A>-oder <xref:Microsoft.VisualBasic.Strings.ChrW%2A>-Funktion verwenden, um einen `Integer` Wert in ein `Char` mit diesem Codepunkt zu konvertieren.

Wenn der Schalter für die Typüberprüfung (die [Option Strict-Anweisung) aktiviert](../../../visual-basic/language-reference/statements/option-strict-statement.md)ist, müssen Sie das Literaltypzeichen an ein einzelzeichenfolgenliteralzeichen anfügen, um es als `Char` Datentyp zu identifizieren. Das folgende Beispiel veranschaulicht dies. Die erste Zuweisung zur `charVar`-Variablen generiert den Compilerfehler [BC30512](../../misc/bc30512.md) , da `Option Strict` auf ON fest liegt. Die zweite wird erfolgreich kompiliert, da das `c` Literaltypzeichens das Literale als `Char` Wert identifiziert.

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

- **Negative Zahlen.** `Char` ist ein unsignierter Typ und kann keinen negativen Wert darstellen. In jedem Fall sollten Sie `Char` nicht verwenden, um numerische Werte zu speichern.

- **Interop-Überlegungen.** Wenn Sie eine Schnittstelle mit Komponenten, die nicht für die .NET Framework geschrieben wurden, z. b. Automatisierungs-oder COM-Objekte, beachten Sie, dass die Zeichen Typen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Byte`, anstatt `Char` im neuen Visual Basic Code zu verwenden.

- **Tet.** Der `Char`-Datentyp wird zu `String`erweitert. Dies bedeutet, dass Sie `Char` in `String` konvertieren können und dass keine <xref:System.OverflowException?displayProperty=nameWithType>auftritt.

- **Geben Sie Zeichen ein.** Das Anfügen des Literals `C` an eine Zeichenfolge mit einem einzelnen Zeichen erzwingt den Datentyp `Char`. `Char` hat kein Bezeichnertyp Zeichen.

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
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
