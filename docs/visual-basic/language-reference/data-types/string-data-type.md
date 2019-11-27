---
title: String-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: c2c6f9632646c432abb7b6da8887253e526cc994
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343914"
---
# <a name="string-data-type-visual-basic"></a>String-Datentyp (Visual Basic)

Enthält Sequenzen von 16-Bit-Code Punkten (2 Bytes) ohne Vorzeichen, die den Wert zwischen 0 und 65535 liegen. Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar. Eine Zeichenfolge kann zwischen 0 und ungefähr 2 Milliarden (2 ^ 31) Unicode-Zeichen enthalten.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie den `String`-Datentyp, um mehrere Zeichen ohne den zusätzlichen Verwaltungsaufwand `Char()`, ein Array von `Char` Elementen, zu speichern.  
  
 Der Standardwert `String` ist `Nothing` (ein NULL-Verweis). Beachten Sie, dass dies nicht mit der leeren Zeichenfolge (Wert `""`) identisch ist.  
  
## <a name="unicode-characters"></a>Unicode-Zeichen  

 Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur. Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert. Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile. Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen. Dies schließt weltweite Textzeichen, Diakritik und mathematische und technische Symbole ein.  
  
 Sie können Methoden wie <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> eines einzelnen Zeichens in einer `String` Variablen verwenden, um die Unicode-Klassifizierung zu bestimmen.  
  
## <a name="format-requirements"></a>Formatanforderungen  

 Sie müssen eine `String` Literals in Anführungszeichen (`" "`) einschließen. Wenn Sie ein Anführungszeichen als eines der Zeichen in die Zeichenfolge einschließen müssen, verwenden Sie zwei zusammenhängende Anführungszeichen (`""`). Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Beachten Sie, dass die zusammenhängenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von den Anführungszeichen sind, die den `String` literalen beginnen und beenden.  
  
## <a name="string-manipulations"></a>Zeichen folgen Manipulationen  

 Wenn Sie einer `String` Variablen eine Zeichenfolge zuweisen, ist diese Zeichenfolge *unveränderlich*. Dies bedeutet, dass Sie Ihre Länge oder ihren Inhalt nicht ändern können. Wenn Sie eine Zeichenfolge in irgendeiner Weise ändern, erstellt Visual Basic eine neue Zeichenfolge und gibt die vorherige zurück. Die `String` Variable zeigt dann auf die neue Zeichenfolge.  
  
 Sie können den Inhalt einer `String` Variablen bearbeiten, indem Sie eine Vielzahl von Zeichen folgen Funktionen verwenden. Im folgenden Beispiel wird die <xref:Microsoft.VisualBasic.Strings.Left%2A>-Funktion veranschaulicht.  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Eine von einer anderen Komponente erstellte Zeichenfolge kann mit führenden oder nachfolgenden Leerzeichen aufgefüllt werden. Wenn Sie eine solche Zeichenfolge erhalten, können Sie diese Leerzeichen mit den Funktionen <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> entfernen.  
  
 Weitere Informationen zu Zeichen folgen Manipulationen finden Sie unter Zeichen [folgen.](../../../visual-basic/programming-guide/language-features/strings/index.md)  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Negative Zahlen.** Beachten Sie, dass die von `String` gehaltenen Zeichen nicht signiert sind und keine negativen Werte darstellen können. In jedem Fall sollten Sie `String` nicht verwenden, um numerische Werte zu speichern.  
  
- **Interop-Überlegungen.** Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeichen folgen Zeichen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen. Wenn Sie ein Zeichen folgen Argument von 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte` Elementen, anstatt `String` in den neuen Visual Basic Code.  
  
- **Geben Sie Zeichen ein.** Das Anfügen des Bezeichnertyp Zeichens `$` an einen beliebigen Bezeichner zwingt ihn in den `String`-Datentyp. `String` hat kein Literalzeichen. Der Compiler behandelt jedoch Literale, die in Anführungszeichen (`" "`) eingeschlossen sind, als `String`.  
  
- **Frameworktyp.** Der entsprechende Typ in der .NET Framework ist die <xref:System.String?displayProperty=nameWithType> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
