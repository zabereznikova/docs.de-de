---
title: "Char Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.Char"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal type characters, C"
  - "Char data type"
  - "C literal type character"
  - "data types [Visual Basic], assigning"
  - "Char data type, character literals"
ms.assetid: cd7547a9-7855-4e8e-b216-35d74a362657
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Char Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert 16\-Bit\-\(2\-Byte\)\-Codepunkte ohne Vorzeichen, deren Werte im Bereich von 0 bis 65535 liegen.  Jeder *Codepunkt* oder jedes Zeichencode, stellt ein einzelnes Unicode\-Zeichen dar.  
  
## Hinweise  
 Verwenden Sie den `Char`\-Datentyp, wenn Sie lediglich ein einzelnes Zeichen speichern möchten und der zusätzliche Speicherbedarf für `String` nicht benötigt wird.  In bestimmten Fällen können Sie mit `Char()`, einem Array von `Char`\-Elementen, mehrere Zeichen speichern.  
  
 Der Standardwert von `Char` ist das Zeichen mit dem Codepunkt 0 \(null\).  
  
## Unicode\-Zeichen  
 Die ersten 128 Codepunkte \(0 bis 127\) in Unicode entsprechen den Buchstaben und Symbolen auf einer Standardtastatur \(USA\).  Tastatur.  Diese ersten 128 Codepunkte entsprechen denen, die vom ASCII\-Zeichensatz definiert werden.  Die zweiten 128 Codepunkte \(128 bis 255\) sind Sonderzeichen, z. B. Buchstaben aus lateinischen Alphabeten, Akzentzeichen, Währungssymbole und Symbole für mathematische Brüche.  Die übrigen Codepunkte \(256 bis 65535\) werden für eine Vielzahl von Symbolen verwendet, z. B. internationale Textzeichen, diakritische Zeichen sowie mathematische und technische Symbole.  
  
 Sie können z. B. die <xref:System.Char.IsDigit%2A>\-Methode und die <xref:System.Char.IsPunctuation%2A>\-Methode auf eine `Char`\-Variable anwenden und so deren Unicode\-Klassifizierung ermitteln.  
  
## Typkonvertierung  
 Visual Basic führt keine direkten Konvertierungen zwischen `Char` und den numerischen Typen durch.  Mit der <xref:Microsoft.VisualBasic.Strings.Asc%2A>\-Funktion oder der <xref:Microsoft.VisualBasic.Strings.AscW%2A>\-Funktion können Sie einen `Char`\-Wert in einen `Integer` konvertieren, der seinen Codepunkt darstellt.  Mit der <xref:Microsoft.VisualBasic.Strings.Chr%2A>\-Funktion oder der <xref:Microsoft.VisualBasic.Strings.ChrW%2A>\-Funktion können Sie einen `Integer`\-Wert in einen `Char` mit dem betreffenden Codepunkt konvertieren.  
  
 Wenn die Typüberprüfung \([Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)\) aktiviert ist, müssen Sie das Literaltypzeichen an ein Zeichenfolgenliteral aus einem Zeichen hängen, um es als `Char`\-Datentyp zu kennzeichnen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
Option Strict On  
Dim charVar As Char  
' The following statement attempts to convert a String literal to Char.  
' Because Option Strict is On, it generates a compiler error.  
charVar = "Z"  
' The following statement succeeds because it specifies a Char literal.  
charVar = "Z"C  
```  
  
## Programmiertipps  
  
-   **Negative Zahlen.** `Char` ist ein Typ ohne Vorzeichen und kann keinen negativen Wert darstellen.  Verwenden Sie `Char` auf keinen Fall für numerische Werte.  
  
-   **Interop\-Überlegungen.** Wenn Sie mit Komponenten arbeiten, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), sollten Sie beachten, dass Zeichentypen in anderen Umgebungen eine andere Datenbreite \(8 Bits\) haben.  Wenn Sie ein 8\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic\-Code als `Byte` und nicht als `Char`.  
  
-   **Erweiterung.** Der `Char`\-Datentyp wird zu `String` erweitert.  So können Sie `Char` in `String` konvertieren, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `C` an ein aus einem Zeichen bestehendes Zeichenfolgenliteral wird der `Char`\-Datentyp erzwungen.  `Char` hat kein Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Char?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.Char?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>   
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>   
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>   
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)