---
title: "Parsing Text Files with the TextFieldParser Object (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "TextFieldParser object, using"
  - "I/O [Visual Basic], parsing files"
  - "files, parsing"
ms.assetid: fc31d6e6-af0c-403f-8a00-d556b2c57567
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Parsing Text Files with the TextFieldParser Object (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Mit dem `TextFieldParser`\-Objekt können Sie sehr große Dateien analysieren und verarbeiten, die Textspalten mit Trennzeichen enthalten, z. B. Protokolldateien oder ältere Datenbankinformationen.  Die Analyse einer Textdatei mit `TextFieldParser` ähnelt dem Durchlaufen einer Textdatei, während die Verarbeitungsmethode für die Extrahierung von Textfeldern mit Methoden zum Bearbeiten von Zeichenfolgen vergleichbar ist.  
  
## Analysieren von verschiedenen Typen von Textdateien  
 Textdateien können Felder verschiedener Breite enthalten, die mit Trennzeichen wie Kommas oder Tabstoppzeichen getrennt sind.  Definieren Sie `TextFieldType` und das Trennzeichen, wie nachfolgend gezeigt. Im Beispiel wird die `SetDelimiters`\-Methode zum Definieren einer tabstoppgetrennten Textdatei verwendet:  
  
 [!code-vb[VbVbalrTextFieldParser#21](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_1.vb)]  
  
 Textdateien können auch Felder mit fester Breite enthalten.  In solchen Fällen müssen Sie den `TextFieldType` als `FixedWidth` definieren und die Breite jedes einzelnen Feldes angeben, wie nachfolgend gezeigt.  Im Beispiel wird die `SetFieldWidths`\-Methode zum Definieren der Textspalten verwendet: die erste Spalte ist 5 Zeichen breit, die zweite 10, die dritte 11 und die vierte Spalte weist eine variable Breite auf.  
  
 [!code-vb[VbVbalrTextFieldParser#22](../../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/parsing-text-files-with-the-textfieldparser-object_2.vb)]  
  
 Nach der Definition des Formats können Sie die Datei durchlaufen und mit der `ReadFields`\-Methode jede Zeile einzeln verarbeiten.  
  
 Wenn ein Feld nicht dem angegebenen Format entspricht, wird eine <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\-Ausnahme ausgelöst.  Beim Auslösen solcher Ausnahmen enthalten die `ErrorLine`\-Eigenschaft und die `ErrorLineNumber`\-Eigenschaft den Text, der die Ausnahme verursacht hat, und die Zeilennummer dieses Textes.  
  
## Analysieren von Dateien mit mehreren Formaten  
 Mithilfe der `PeekChars`\-Methode des `TextFieldParser`\-Objekts kann jedes Feld vor dem Lesen überprüft werden. So können mehrere Formate für die Felder definiert und entsprechende Aktionen veranlasst werden.  Weitere Informationen finden Sie unter [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ReadFields%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.HasFieldsEnclosedInQuotes%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.LineNumber%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TrimWhiteSpace%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A>   
 [Problembehandlung bei Ausnahmen: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)