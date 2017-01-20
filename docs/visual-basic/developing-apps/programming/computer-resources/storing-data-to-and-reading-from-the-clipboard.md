---
title: "Storing Data to and Reading from the Clipboard (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Clipboard, storing data to (My.Computer.Clipboard)"
  - "Clipboard, reading from (My.Computer.Clipboard)"
  - "Clipboard"
  - "My.Computer.Clipboard object, tasks"
  - "data [Visual Basic], Clipboard"
  - "reading data, from Clipboard"
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Storing Data to and Reading from the Clipboard (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die Zwischenablage kann zum Speichern von Daten wie Text und Bildern verwendet werden.  Da die Zwischenablage von allen aktiven Prozessen genutzt wird, kann sie zur Übertragung von Daten zwischen den Prozessen verwendet werden.  Das `My.Computer.Clipboard`\-Objekt können Sie auf einfache Weise die Zwischenablage zuzugreifen und ihn zu lesen und zu schreiben.  
  
## Lesen aus der Zwischenablage  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A>\-Methode, um Text in der Zwischenablage lesen.  Mit dem folgenden Code wird der Text gelesen und in einem Meldungsfeld angezeigt.  In der Zwischenablage muss Text gespeichert sein, damit das Beispiel fehlerfrei ausgeführt werden kann.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_1.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Windows Forms\-Anwendung \> Zwischenablage**.  Weitere Informationen finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>\-Methode, um ein Bild aus der Zwischenablage abzurufen.  Mit diesem Beispiel wird überprüft, ob die Zwischenablage ein Bild enthält, bevor das Bild abgerufen und  `PictureBox1` zugewiesen wird.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_2.vb)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Sie finden das Element in der Codeausschnittauswahl unter **Windows Forms\-Anwendung \> Zwischenablage**. Weitere Informationen dazu finden Sie unter [Codeausschnitte](/visual-studio/ide/code-snippets).  
  
 In der Zwischenablage gespeicherte Elemente bleiben auch nach dem Beenden der Anwendung erhalten.  
  
## Den Dateityp bestimmen in der Zwischenablage gespeichert  
 Die Daten in der Zwischenablage können in verschiedenen Formaten gespeichert werden, z. B. als Text, Audiodaten oder Bilddaten.  Um festzustellen, welchen Dateityp die Zwischenablage enthält, können Sie Methoden wie <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> und <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> verwenden.  Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>\-Methode kann verwendet werden, wenn Sie das Vorhandensein eines benutzerdefinierten Formats überprüfen möchten.  
  
 Verwenden Sie die `ContainsImage`\-Funktion, um festzustellen, ob es sich bei den in der Zwischenablage enthaltenen Daten um ein Bild handelt.  Mit dem folgenden Code wird festgestellt, ob es sich bei den Daten um ein Bild handelt, und es wird eine entsprechende Meldung ausgegeben.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_3.vb)]  
  
## Die Zwischenablage löschen  
 Mit der <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A>\-Methode wird die Zwischenablage gelöscht.  Da die Zwischenablage auch von anderen Prozessen verwendet wird, wirkt sich das Löschen der Zwischenablage unter Umständen auch auf diese Prozesse aus.  
  
 Im folgenden Beispiel wird die Verwendung der `Clear`\-Methode veranschaulicht.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_4.vb)]  
  
## Schreiben in die Zwischenablage  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A>\-Methode, um Text in die Zwischenablage zu schreiben.  Im folgenden Code wird die Zeichenfolge "This is a test string" in die Zwischenablage geschrieben.  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_5.vb)]  
  
 Die `SetText`\-Methode kann den Stilparameter akzeptieren, der einen primitiven Typ <xref:System.Windows.Forms.TextDataFormat>enthält.  Im folgenden Code wird die Zeichenfolge "This is a test string" als RTF\-Text in die Zwischenablage geschrieben.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_6.vb)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A>\-Methode, um Daten in die Zwischenablage zu schreiben.  In diesem Beispiel wird das `DataObject` `dataChunk` im benutzerdefinierten Format `specialFormat` in die Zwischenablage geschrieben.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_7.vb)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>\-Methode, um Audiodaten in die Zwischenablage zu schreiben.  In diesem Beispiel wird das `musicReader`\-Bytearray erstellt, die Datei `cool.wav` wird in dieses Array gelesen und anschließend in die Zwischenablage geschrieben.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading_8.vb)]  
  
> [!IMPORTANT]
>  Da auch andere Benutzer auf die Zwischenablage zugreifen können, sollten Sie sie nicht für sicherheitsrelevante Informationen wie Kennwörter oder vertrauliche Daten verwenden.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>   
 [Gewusst wie: Lesen von Objektdaten aus einer XML\-Datei](../Topic/How%20to:%20Read%20Object%20Data%20from%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Schreiben von Objektdaten in eine XML\-Datei](../Topic/How%20to:%20Write%20Object%20Data%20to%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)