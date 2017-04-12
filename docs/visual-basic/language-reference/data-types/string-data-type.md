---
title: String-Datentyp (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9221a89a1fb46609b4b8550968e3a2bbe874772c
ms.lasthandoff: 03/13/2017

---
# <a name="string-data-type-visual-basic"></a>String-Datentyp (Visual Basic)
Enthält Sequenzen vorzeichenlose 16-Bit (2-Byte)-Codepunkte Bereichs im Wert von 0 bis 65535. Jede *Codepunkt*, oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar. Eine Zeichenfolge darf zwischen 0 und etwa zwei Milliarden (2 ^ 31) Unicode-Zeichen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `String` -Datentyp, um mehrere Zeichen ohne den Verwaltungsaufwand für Array speichern `Char()`, ein Array von `Char` Elemente.  
  
 Der Standardwert von `String` ist `Nothing` (ein null-Verweis). Beachten Sie, dass dies nicht dasselbe wie eine leere Zeichenfolge ist (Wert `""`).  
  
## <a name="unicode-characters"></a>Unicode-Zeichen  
 Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen auf einer Standardtastatur (USA). Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert. Die zweiten 128 Codepunkte (128 – 255) darstellen, Sonderzeichen, wie z. B. lateinischen Buchstaben, Akzente, Währungssymbole und Bruchzahlen. Unicode verwendet die übrigen Codepunkte (256 bis&65535;) für eine Vielzahl von Symbolen. Dies schließt internationale Textzeichen, diakritische Zeichen und mathematische und technische Symbole.  
  
 Sie verwenden die Methoden wie <xref:System.Char.IsDigit%2A>und <xref:System.Char.IsPunctuation%2A>auf ein einzelnes Zeichen in eine `String` Variable, deren Unicode-Klassifizierung ermitteln.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A>  
  
## <a name="format-requirements"></a>Formatanforderungen  
 Muss ein `String` Zeichenfolgenliteral in Anführungszeichen (`" "`). Wenn Sie ein Anführungszeichen als eines der Zeichen in der Zeichenfolge einfügen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`). Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von den Anführungszeichen, die Anfang und Ende der `String` literal.  
  
## <a name="string-manipulations"></a>Zeichenfolgen  
 Nachdem Sie eine Zeichenfolge zuweisen ein `String` , diese Zeichenfolge wird *unveränderlich*, d.h. nicht ändern, deren Größe oder den Inhalt. Wenn Sie eine Zeichenfolge in keiner Weise ändern, wird Visual Basic eine neue Zeichenfolge erstellt und verwirft die vorhergehende. Die `String` -Variable zeigt dann auf die neue Zeichenfolge.  
  
 Sie können den Inhalt der Bearbeiten einer `String` Variable mithilfe einer Vielzahl von Zeichenfolgenfunktionen. Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A>Funktion</xref:Microsoft.VisualBasic.Strings.Left%2A>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Eine Zeichenfolge, die von einer anderen Komponente erstellt möglicherweise mit führenden oder nachstehenden Leerzeichen aufgefüllt werden. Wenn Sie eine solche Zeichenfolge empfangen, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A>Funktionen entfernen.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A>  
  
 Weitere Informationen über Zeichenfolgen finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Negative Zahlen.** Denken Sie daran, dass die Zeichen durch gehalten `String` Vorzeichen aufweisen und keine negativen Werte darstellen. In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.  
  
-   **Interop-Überlegungen.** Wenn Sie mit nicht geschriebenen für .NET Framework-Komponenten anbinden, z. B. Automatisierungs- oder COM-Objekte, müssen Sie Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) in anderen Umgebungen. Wenn Sie ein Zeichenfolgenargument mit 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte` Elemente anstelle von `String` im neuen Visual Basic-Code.  
  
-   **Typzeichen.** Durch Anhängen des Typkennzeichens `$` an einen beliebigen Bezeichner wird die `String` -Datentyp. `String`verfügt über kein Literalzeichen. Der Compiler behandelt jedoch Literale in Anführungszeichen eingeschlossen (`" "`) als `String`.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=fullName>Klasse.</xref:System.String?displayProperty=fullName>  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName>   
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Gewusst wie: Aufrufen eine Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)

