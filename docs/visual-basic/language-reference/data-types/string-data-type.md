---
title: String-Datentyp (Visual Basic)
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
ms.openlocfilehash: 3e87dc6527b4351467b1155439ee8266157c16ff
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842290"
---
# <a name="string-data-type-visual-basic"></a>String-Datentyp (Visual Basic)
Enthält Sequenzen von unsignierten 16-Bit (2-Byte)-Codepunkte dieses Bereichs im Wert von 0 bis 65535 an. Jede *Codepunkt*, oder Zeichencode ein einzelnes Unicodezeichens darstellt. Eine Zeichenfolge kann zwischen 0 und etwa zwei Milliarden enthalten (2 ^ 31) Unicode-Zeichen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `String` -Datentyp, um mehrere Zeichen, ohne den Aufwand des Array-Verwaltung von aufzunehmen `Char()`, ein Array von `Char` Elemente.  
  
 Der Standardwert von `String` ist `Nothing` (ein null-Verweis). Beachten Sie, dass dies nicht identisch mit der leeren Zeichenfolge ist (Wert `""`).  
  
## <a name="unicode-characters"></a>Unicode-Zeichen  
 Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen, die auf einer US-Standardtastatur. Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert. Die zweite 128 Codepunkte (128 – 255) stellen die Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzenten, Währungssymbole und Bruchzahlen dar. Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen. Dies schließt weltweit Textzeichen, diakritische Zeichen und mathematischen und technischen Symbole.  
  
 Können Sie Methoden wie z. B. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf ein einzelnes Zeichen in einem `String` Variable, um zu bestimmen, die Unicode-Klassifizierung.  
  
## <a name="format-requirements"></a>Formatanforderungen  
 Sie setzen eine `String` Zeichenfolgenliteral in Anführungszeichen (`" "`). Wenn Sie ein Anführungszeichen als eines der Zeichen in der Zeichenfolge einfügen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`). Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von der Anführungszeichen, das Starten und Beenden der `String` literal.  
  
## <a name="string-manipulations"></a>Zeichenfolgenbearbeitungen  
 Nachdem Sie eine Zeichenfolge, die zugewiesen eine `String` -Variablen Zeichenfolge ist *unveränderliche*, das bedeutet, dass nicht ändern, deren Größe oder den Inhalt. Wenn Sie eine Zeichenfolge in keiner Weise ändern, wird Visual Basic erstellt eine neue Zeichenfolge, und bricht ab dem vorherigen Beispiel. Die `String` Variable verweist dann auf die neue Zeichenfolge.  
  
 Sie können den Inhalt bearbeiten einer `String` Variable, indem Sie mithilfe einer Vielzahl von Funktionen für Zeichenfolgen. Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A> Funktion  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Eine Zeichenfolge, die von einer anderen Komponente erstellt, möglicherweise mit voran- oder nachgestellten Leerzeichen aufgefüllt werden. Wenn Sie eine solche Zeichenfolge erhalten haben, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> Funktionen diese Leerzeichen entfernt werden sollen.  
  
 Weitere Informationen zu zeichenfolgenbearbeitungen, finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** Beachten Sie, dass die Zeichen von gehalten `String` nicht signiert sind und keine negativen Werte darstellen. In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.  
  
-   **Interop-Überlegungen.** Wenn die Komponenten, die nicht für .NET Framework geschrieben wurden verbunden ist z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) verfügen in anderen Umgebungen. Wenn Sie ein Zeichenfolgenargument von 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie sie als `Byte()`, ein Array von `Byte` Elemente anstelle von `String` im neuen Visual Basic-Code.  
  
-   **Typzeichen.** Der Bezeichner-Typzeichen Anfügen `$` an einen beliebigen Bezeichner wird die `String` -Datentyp. `String` hat kein literal-Typzeichen. Der Compiler behandelt jedoch Literale, die in Anführungszeichen eingeschlossen (`" "`) als `String`.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=nameWithType> Klasse.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.String?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
