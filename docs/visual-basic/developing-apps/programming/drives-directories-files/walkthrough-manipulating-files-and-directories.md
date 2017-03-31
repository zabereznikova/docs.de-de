---
title: Bearbeiten von Dateien und Verzeichnissen in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, reading text
- reading files, text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files, walkthroughs
- Visual Basic code, file access
- files, writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files, walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: stevehoag
ms.author: shoag
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 89137b3c927a7ac8ed126f2be3695c4aa72a85fb
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a>Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic
Diese exemplarische Vorgehensweise enthält eine Einführung in die Grundlagen der Datei-E/A in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Es wird beschrieben, wie Sie eine kleine Anwendung erstellen können, in der Textdateien in einem Verzeichnis aufgelistet und überprüft werden. Die Anwendung stellt Dateiattribute und die erste Zeile des Inhalts jeder ausgewählten Textdatei zur Verfügung. Es besteht die Möglichkeit, Informationen in eine Protokolldatei zu schreiben.  
  
 In dieser exemplarischen Vorgehensweise werden Member von `My.Computer.FileSystem Object` verwendet, die unter [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügbar sind. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.FileIO.FileSystem>. Am Ende dieser exemplarischen Vorgehensweise finden Sie ein entsprechendes Beispiel, in dem Klassen aus dem Namespace <xref:System.IO> verwendet werden.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Klicken Sie im Menü **Datei** auf **Neues Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Erweitern Sie im Bereich **Installierte Vorlagen** **Visual Basic**, und klicken Sie dann auf **Windows**. Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
3.  Geben Sie im Feld **Name** `FileExplorer` ein, um den Projektnamen festzulegen, und klicken Sie anschließend auf **OK**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] fügt das Projekt zum **Projektmappen-Explorer** hinzu. Der Windows Forms-Designer wird geöffnet.  
  
4.  Fügen Sie die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.  
  
    |Steuerelement|Eigenschaft|Wert|  
    |-------------|--------------|-----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button** (Schaltfläche)|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> **Browse** (Durchsuchen)|  
    |**Button** (Schaltfläche)|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> **Examine** (Untersuchen)|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> **Save Results** (Ergebnisse speichern)|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a>So wählen Sie einen Ordner und Listendateien in einem Ordner aus  
  
1.  Erstellen Sie einen `Click`-Ereignishandler für `browseButton`, indem Sie auf ein Steuerelement im Formular doppelklicken. Der Code-Editor wird geöffnet.  
  
2.  Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     Mit dem Aufruf `FolderBrowserDialog1.ShowDialog` wird das Dialogfeld **Ordner suchen** geöffnet. Nachdem der Benutzer auf **OK** geklickt hat, wird die Eigenschaft <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> als Argument an die Methode `ListFiles` gesendet, die im nächsten Schritt hinzugefügt wird.  
  
3.  Fügen Sie die folgende `ListFiles`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     Dieser Code löscht zuerst **ListBox**.  
  
     Die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> ruft dann eine Auflistung von Zeichenfolgen ab, eine für jede Datei im Verzeichnis. Die Methode `GetFiles` akzeptiert ein Suchmusterargument, um Dateien abzurufen, die mit einem bestimmten Muster übereinstimmen. In diesem Beispiel werden nur Dateien mit der Dateiendung „.txt“ zurückgegeben.  
  
     Die Zeichenfolgen, die von der Methode `GetFiles` zurückgegeben werden, werden anschließend zu **ListBox** hinzugefügt.  
  
4.  Führen Sie die Anwendung aus. Klicken Sie auf die Schaltfläche **Durchsuchen**. Navigieren Sie im Dialogfeld **Ordner suchen** zu einem Ordner, der .txt-Dateien enthält. Wählen Sie den Ordner anschließend aus, und klicken Sie auf **OK**.  
  
     `ListBox` enthält eine Liste von .txt-Dateien im ausgewählten Ordner.  
  
5.  Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a>So rufen Sie Attribute einer Datei und Inhalt einer Textdatei ab  
  
1.  Erstellen Sie einen `Click`-Ereignishandler für `examineButton`, indem Sie auf ein Steuerelement im Formular doppelklicken.  
  
2.  Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     Der Code stellt sicher, dass ein Element in `ListBox` ausgewählt ist. Anschließend ruft er den Eintrag des Dateipfads aus `ListBox` ab. Die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> wird verwendet, um zu überprüfen, ob die Datei noch vorhanden ist.  
  
     Der Dateipfad wird als Argument an die `GetTextForOutput`-Methode gesendet, die im nächsten Schritt hinzugefügt wird. Diese Methode gibt eine Zeichenfolge zurück, die Dateiinformationen enthält. Die Dateiinformationen werden in einer **MessageBox** angezeigt.  
  
3.  Fügen Sie die folgende `GetTextForOutput`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     Der Code verwendet die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> zum Abrufen von Dateiparametern. Die Dateiparameter werden zu <xref:System.Text.StringBuilder> hinzugefügt.  
  
     Die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> liest den Dateiinhalt in einen <xref:System.IO.StreamReader>. Die erste Zeile des Inhalts wird von `StreamReader` abgerufen und zu `StringBuilder` hinzugefügt.  
  
4.  Führen Sie die Anwendung aus. Klicken Sie auf **Durchsuchen**, und suchen Sie nach einem Ordner, der .txt-Dateien enthält. Klicken Sie auf **OK**.  
  
     Wählen Sie eine Datei aus `ListBox` aus, und klicken Sie anschließend auf **Examine** (Untersuchen). Die Dateiinformationen werden von `MessageBox` angezeigt.  
  
5.  Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-add-a-log-entry"></a>So fügen Sie einen Protokolleintrag hinzu  
  
1.  Fügen Sie am Ende des `examineButton_Click`-Ereignishandlers folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     Der Protokolldateipfad wird vom Code so festgelegt, dass die Protokolldatei in dem Verzeichnis gespeichert wird, das auch das Verzeichnis der ausgewählten Datei ist. Der Text der Protokolldatei wird auf das aktuelle Datum und die Uhrzeit sowie die Dateiinformationen festgelegt.  
  
     Die Methode <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>, mit der das Argument `append` auf `True` festgelegt wird, wird zum Erstellen des Protokolleintrags verwendet.  
  
2.  Führen Sie die Anwendung aus. Navigieren Sie zu einer Textdatei, wählen Sie diese in `ListBox` aus, aktivieren Sie das Kontrollkästchen **Save Results** (Ergebnisse speichern), und klicken Sie auf **Examine** (Untersuchen). Stellen Sie sicher, dass der Protokolleintrag in die `log.txt`-Datei geschrieben ist.  
  
3.  Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-use-the-current-directory"></a>So verwenden Sie das aktuelle Verzeichnis  
  
1.  Erstellen Sie einen Ereignishandler für `Form1_Load`, indem Sie auf das Formular doppelklicken.  
  
2.  Fügen Sie dem Ereignishandler folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     Durch diesen Code wird das Standardverzeichnis auf den Browser des Ordners zum aktuellen Verzeichnis festgelegt.  
  
3.  Führen Sie die Anwendung aus. Wenn Sie zum ersten Mal auf **Durchsuchen** klicken, wird das Dialogfeld **Ordner suchen** im aktuellen Verzeichnis geöffnet.  
  
4.  Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-selectively-enable-controls"></a>So aktivieren Sie Steuerelemente selektiv  
  
1.  Fügen Sie die folgende `SetEnabled`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     Die Methode `SetEnabled` aktiviert oder deaktiviert Steuerelemente. Dies hängt davon ab, ob ein Element in `ListBox` ausgewählt ist.  
  
2.  Erstellen Sie einen `SelectedIndexChanged`-Ereignishandler für `filesListBox`, indem Sie auf das Steuerelement `ListBox` im Formular doppelklicken.  
  
3.  Fügen Sie im Ereignishandler `filesListBox_SelectedIndexChanged` einen Aufruf von `SetEnabled` hinzu.  
  
4.  Fügen Sie am Ende des Ereignishandlers `browseButton_Click` einen Aufruf von `SetEnabled` hinzu.  
  
5.  Fügen Sie am Ende des Ereignishandlers `Form1_Load` einen Aufruf von `SetEnabled` hinzu.  
  
6.  Führen Sie die Anwendung aus. Das Kontrollkästchen **Save Results** (Ergebnisse speichern) und die Schaltfläche **Examine** (Untersuchen) sind deaktiviert, wenn ein Element nicht in `ListBox` ausgewählt ist.  
  
## <a name="full-example-using-mycomputerfilesystem"></a>Ausführliches Beispiel mit Verwendung von „My.Computer.FileSystem“  
 Im Folgenden sehen Sie das vollständige Beispiel.  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a>Ausführliches Beispiel mit Verwendung von „System.IO“  
 Im folgenden entsprechenden Beispiel werden Klassen aus dem Namespace <xref:System.IO> anstelle von `My.Computer.FileSystem`-Objekten verwendet.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Exemplarische Vorgehensweise: Bearbeiten von Dateien mit .NET Framework-Methoden](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)

