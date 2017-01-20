---
title: "String Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.String"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "strings [Visual Basic], character"
  - "strings [Visual Basic], fixed-length"
  - "string keyword [Visual Basic]"
  - "fixed-length strings, string data type"
  - "literals, string"
  - "text [Visual Basic], String data type"
  - "$ identifier type character"
  - "String data type"
  - "fixed-length strings"
  - "string literals"
  - "data types [Visual Basic], assigning"
  - "" String literals"
  - "identifier type characters, $"
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# String Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert Sequenzen von 16\-Bit\-\(2\-Byte\)\-Codepunkten ohne Vorzeichen, deren Werte im Bereich von 0 bis 65535 liegen.  Jeder *Codepunkt* oder jedes Zeichencode, stellt ein einzelnes Unicode\-Zeichen dar.  Eine Zeichenfolge kann zwischen 0 und etwa zwei Milliarden \(2 ^ 31\) Unicode\-Zeichen enthalten.  
  
## Hinweise  
 Verwenden Sie den `String`\-Datentyp, um mehrere Zeichen speichern zu können, ohne Arrayverwaltungsaufwand für `Char()` \(ein Array von `Char`\-Elementen\) betreiben zu müssen.  
  
 Der Standardwert von `String` ist `Nothing` \(ein NULL\-Verweis\).  Beachten Sie, dass dies nicht das Gleiche ist wie eine leere Zeichenfolge \(Wert `""`\).  
  
## Unicode\-Zeichen  
 Die ersten 128 Codepunkte \(0 bis 127\) in Unicode entsprechen den Buchstaben und Symbolen auf einer Standardtastatur \(USA\).  Tastatur.  Diese ersten 128 Codepunkte entsprechen denen, die vom ASCII\-Zeichensatz definiert werden.  Die zweiten 128 Codepunkte \(128 bis 255\) sind Sonderzeichen, z. B. Buchstaben aus lateinischen Alphabeten, Akzentzeichen, Währungssymbole und Symbole für mathematische Brüche.  Unicode verwendet die übrigen Codepunkte \(256\-65535\) für eine Vielzahl von Symbolen.  Dies schließt internationale Textzeichen, diakritische Zeichen und mathematische und technische Symbole ein.  
  
 Durch Anwendung von Methoden, wie beispielsweise die <xref:System.Char.IsDigit%2A>\-Methode oder die <xref:System.Char.IsPunctuation%2A>\-Methode, auf ein einzelnes Zeichen in einer `String`\-Variablen können Sie die zugehörige Unicode\-Klassifizierung ermitteln.  
  
## Formatanforderungen  
 Ein `String`\-Literal muss zwischen Anführungszeichen \(`" "`\) stehen.  Wenn ein Anführungszeichen als Zeichen in einer Zeichenfolge enthalten ist, verwenden Sie zwei aufeinander folgende Anführungszeichen \(`""`\).  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 Beachten Sie, dass zwei aufeinander folgende Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge repräsentieren, unabhängig von den Anführungszeichen sind, die Anfang und Ende des `String`\-Literals markieren.  
  
## Zeichenfolgenbearbeitung  
 Sobald Sie einer `String`\-Variablen eine Zeichenfolge zugewiesen haben, ist die Zeichenfolge *unveränderlich*. Das bedeutet, dass Sie die Länge oder den Inhalt der Zeichenfolge nicht ändern können.  Wenn Sie eine Zeichenfolge auf irgendeine Weise ändern, erstellt Visual Basic eine neue Zeichenfolge und verwirft die vorhergehende Zeichenfolge.  Die `String`\-Variable zeigt dann auf die neue Zeichenfolge.  
  
 Sie können den Inhalt einer `String`\-Variablen mit einer Reihe von Zeichenfolgenfunktionen bearbeiten.  Im folgenden Beispiel wird die <xref:Microsoft.VisualBasic.Strings.Left%2A>\-Funktion veranschaulicht.  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 Eine von einer anderen Komponente erstellte Zeichenfolge könnte mit führenden oder nachstehenden Leerzeichen aufgefüllt werden.  Wenn Sie eine solche Zeichenfolge empfangen, können Sie die Leerzeichen mit den Funktionen <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> entfernen.  
  
 Weitere Informationen zum Bearbeiten von Zeichenfolgen finden Sie unter [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).  
  
## Programmiertipps  
  
-   **Negative Zahlen.** Beachten Sie, dass die in einem `String` enthaltenen Zeichen keine Vorzeichen aufweisen und keine negativen Werte darstellen können.  Verwenden Sie `String` auf keinen Fall für numerische Werte.  
  
-   **Interop\-Überlegungen.** Wenn Sie mit Komponenten arbeiten, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), sollten Sie beachten, dass die Zeichen in Zeichenfolgen in anderen Umgebungen eine abweichende Datenbreite haben \(8 Bits\).  Wenn Sie ein Zeichenfolgenargument mit 8\-Bit\-Zeichen an eine solche Komponente übergeben, müssen Sie sie in Ihrem neuen Visual Basic\-Code als `Byte()` deklarieren, d. h. als ein Array aus `Byte`\-Elementen, und nicht als `String`.  
  
-   **Typzeichen.** Durch Anhängen des Typkennzeichens `$` an einen beliebigen Bezeichner wird für diesen ebenfalls der `String`\-Datentyp erzwungen.  `String` hat kein Literal\-Typzeichen.  Der Compiler behandelt jedoch Literale, die in Anführungszeichen \(`" "`\) eingeschlossen sind, als `String`.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=fullName>\-Klasse.  
  
## Siehe auch  
 <xref:System.String?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)