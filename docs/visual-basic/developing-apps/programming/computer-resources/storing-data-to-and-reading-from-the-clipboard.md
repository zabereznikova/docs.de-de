---
title: Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 243fb237f3f9ba53f8b29079df08531c102c78dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349729"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a>Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage (Visual Basic)

Die Zwischenablage kann zum Speichern von Daten, z.B. Texten und Bildern, verwendet werden. Da die Zwischenablage von allen aktiven Prozessen genutzt wird, kann sie zur Übertragung von Daten zwischen den Prozessen verwendet werden. Mit dem Objekt `My.Computer.Clipboard` können Sie einfach auf die Zwischenablage zugreifen, aus ihr lesen sowie in sie schreiben.  
  
## <a name="reading-from-the-clipboard"></a>Lesen aus der Zwischenablage  

 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A>-Methode, um den Text in der Zwischenablage auszulesen. Der folgende Code liest den Text aus und zeigt ihn in einem Nachrichtenfeld an. Es muss Text in der Zwischenablage gespeichert sein, damit das Beispiel richtig ausgeführt wird.  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>-Methode zum Abrufen eines Bilds aus der Zwischenablage. In diesem Beispiel wird überprüft, ob ein Bild in der Zwischenablage ist, bevor es abgerufen und `PictureBox1` zugewiesen wird.  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Es befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
 Elemente, die in die Zwischenablage gelegt wurden, bleiben dort, auch nachdem die Anwendung heruntergefahren wurde.  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a>Bestimmen des Dateityps, der in der Zwischenablage gespeichert ist  

 Daten in der Zwischenablage können eine Anzahl von verschiedenen Formen annehmen, z.B. eine Audiodatei oder ein Bild. Um zu ermitteln, welche Art von Datei sich in der Zwischenablage befindet, können Sie Methoden wie z.B. <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> und <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> verwenden. Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>-Methode kann verwendet werden, wenn Sie ein benutzerdefiniertes Format überprüfen möchten.  
  
 Verwenden Sie die `ContainsImage`-Funktion, um zu bestimmen, ob die Daten in der Zwischenablage ein Bild sind. Der folgende Code überprüft, ob die Daten ein Bild sind und erstattet dementsprechend Bericht.  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a>Löschen der Zwischenablage  

 Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A>-Methode löscht den Inhalt der Zwischenablage. Da die Zwischenablage von anderen Prozessen gleichzeitig verwendet wird, kann sich das Löschen auf diese Prozesse auswirken.  
  
 Im folgenden Code wird die Verwendung der `Clear`-Methode veranschaulicht.  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a>In die Zwischenablage schreiben  

 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A>-Methode, um Text in die Zwischenablage zu schreiben. Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ in die Zwischenablage.  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 Die `SetText`-Methode kann einen Formatparameter akzeptieren, der einen Typ von <xref:System.Windows.Forms.TextDataFormat> enthält. Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ als RTF-Text in die Zwischenablage.  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A>-Methode, um Daten in die Zwischenablage zu schreiben. In diesem Beispiel wird das `DataObject` `dataChunk` im benutzerdefiniertem Format `specialFormat` in die Zwischenablage geschrieben.  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>-Methode, um Audiodaten in die Zwischenablage zu schreiben. In diesem Beispiel wird das Bytearray `musicReader` erstellt, die Datei `cool.wav` darin gelesen und anschließend in die Zwischenablage geschrieben.  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
> Da auf die Zwischenablage von anderen Benutzern zugegriffen werden kann, verwenden Sie sie nicht, um sensible Informationen wie Passwörter oder vertrauliche Daten zu speichern.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
