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
ms.openlocfilehash: e672402535215ca30d19cc480e39b42b0364f137
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590808"
---
# <a name="char-data-type-visual-basic"></a>Char-Datentyp (Visual Basic)
Enthält, die vorzeichenlose 16-Bit (2-Byte) Codepunkten im Bereich von 0 bis 65535. Jede *Codepunkt*, oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `Char` -Datentyp, wenn Sie nur einen einzigen halten müssen Zeichen und nicht den Mehraufwand für `String`. In einigen Fällen können Sie `Char()`, ein Array von `Char` Elemente, um mehrere Zeichen enthalten.  
  
 Der Standardwert von `Char` ist das Zeichen mit einem Codepunkt 0.  
  
## <a name="unicode-characters"></a>Unicode-Zeichen  
 Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen auf eine US-Standardtastatur. Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert. Die zweite 128 Codepunkte (128 bis 255) darstellen Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzente, Währungssymbole und Sekundenbruchteilen. Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen, z. B. weltweite Textzeichen, diakritische Zeichen und mathematische und technische Symbole.  
  
 Können Sie Methoden wie z. B. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf eine `Char` Variable, deren Unicode-Klassifizierung ermitteln.  
  
## <a name="type-conversions"></a>Typkonvertierungen  
 Visual Basic nicht direkt zwischen konvertiert `Char` und numerischen Typen. Können Sie die <xref:Microsoft.VisualBasic.Strings.Asc%2A> oder <xref:Microsoft.VisualBasic.Strings.AscW%2A> Funktion konvertiert eine `Char` -Wert an ein `Integer` , dessen Codepunkt darstellt. Können Sie die <xref:Microsoft.VisualBasic.Strings.Chr%2A> oder <xref:Microsoft.VisualBasic.Strings.ChrW%2A> Funktion konvertiert eine `Integer` -Wert in einen `Char` , diesen Codepunkt besitzt.  
  
 Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist, müssen Sie ein Einzelzeichen ein Zeichenfolgenliteral als Identifikation des Literaltypzeichens angefügt der `Char` -Datentyp. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** `Char` ein Typ ohne Vorzeichen und einen negativen Wert nicht darstellen kann. In jedem Fall sollten Sie nicht verwenden `Char` für numerische Werte.  
  
-   **Interop-Überlegungen.** Wenn Sie eine mit Komponenten, die nicht für .NET Framework geschrieben wurden Schnittstelle z. B. Automatisierungs- oder COM-Objekte, denken Sie daran Zeichentypen eine andere Datenbreite (8 Bit) in anderen Umgebungen. Wenn Sie ein 8-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie es als `Byte` anstelle von `Char` im neuen Visual Basic-Code.  
  
-   **Widening.** Die `Char` -Datentyp zu `String`. Dies bedeutet, Sie können konvertieren `Char` auf `String` und tritt eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `C` in eine einzelne Zeichenfolge Literal wird der `Char` -Datentyp. `Char` verfügt über keine Typkennzeichen aus.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Char?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
