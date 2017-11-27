---
title: String-Datentyp (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.String
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90f126a5cca36969617446e81a8d13434e39df75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="string-data-type-visual-basic"></a>String-Datentyp (Visual Basic)
Enthält Sequenzen vorzeichenlose 16-Bit (2-Byte)-Codepunkte dieses Bereichs liegt im Bereich zwischen 0 und 65535 an. Jede *Codepunkt*, oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar. Eine Zeichenfolge darf zwischen 0 und etwa zwei Milliarden (2 ^ 31) Unicode-Zeichen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `String` Datentyps zum Speichern von mehreren Zeichen ohne den Arrayverwaltungsaufwand `Char()`, ein Array von `Char` Elemente.  
  
 Der Standardwert von `String` ist `Nothing` (ein null-Verweis). Beachten Sie, dass dies nicht mit der leeren Zeichenfolge identisch ist (Wert `""`).  
  
## <a name="unicode-characters"></a>Unicode-Zeichen  
 Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen auf eine US-Standardtastatur. Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert. Die zweite 128 Codepunkte (128 bis 255) darstellen Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzente, Währungssymbole und Sekundenbruchteilen. Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen. Dies schließt weltweite Textzeichen, diakritische Zeichen und mathematische und technische Symbole.  
  
 Sie verwenden die Methoden wie z. B. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf ein einzelnes Zeichen in einer `String` Variable, deren Unicode-Klassifizierung ermitteln.  
  
## <a name="format-requirements"></a>Formatanforderungen  
 Sie setzen eine `String` Zeichenfolgenliteral in Anführungszeichen (`" "`). Wenn Sie als eines der Zeichen in der Zeichenfolge ein Anführungszeichen einschließen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`). Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen von Anführungszeichen unabhängig sind, das Starten und Beenden der `String` literal.  
  
## <a name="string-manipulations"></a>Zeichenfolgenmanipulationen  
 Nachdem Sie eine Zeichenfolge zum Zuweisen eine `String` Variable, diese Zeichenfolge wird *unveränderlichen*, das bedeutet, dass seine Länge oder den Inhalt ändern kann nicht. Wenn Sie eine Zeichenfolge in irgendeiner Weise ändern, Visual Basic erstellt eine neue Zeichenfolge, und die vorherige Abfrage abbricht. Die `String` Variable verweist dann auf die neue Zeichenfolge.  
  
 Sie können den Inhalt bearbeiten eine `String` Variable, indem Sie mithilfe einer Vielzahl von String-Funktionen. Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A> Funktion  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Eine Zeichenfolge, die von einer anderen Komponente erstellt möglicherweise mit führende oder nachfolgende Leerzeichen aufgefüllt werden. Wenn Sie solch eine Zeichenfolge empfangen, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> Funktionen diese Leerzeichen entfernt werden sollen.  
  
 Weitere Informationen zu zeichenfolgenmanipulationen, finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** Denken Sie daran, dass die Zeichen vom reservierten `String` ohne Vorzeichen sind, und keine negativen Werte darstellen. In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.  
  
-   **Interop-Überlegungen.** Wenn Sie Komponenten, die nicht für .NET Framework geschrieben wurden Datenbreite z. B. Automatisierungs- oder COM-Objekte, denken Sie daran Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) in anderen Umgebungen. Wenn Sie ein Argument für eine 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte` Elemente, anstelle von `String` im neuen Visual Basic-Code.  
  
-   **Typzeichen.** Die Typkennzeichen Anfügen `$` an einen beliebigen Bezeichner wird die `String` -Datentyp. `String`hat kein literal-Typzeichen. Der Compiler behandelt jedoch Literale, die in Anführungszeichen eingeschlossen (`" "`) als `String`.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=nameWithType> Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
