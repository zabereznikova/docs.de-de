---
title: Erstellen von Dateien und Verzeichnissen
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
ms.openlocfilehash: 83dc6ce0d29c1c368c36b51fc84ecad34d72e01f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "74333809"
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a>Exemplarische Vorgehensweise: Bearbeiten von Dateien und Verzeichnissen in Visual Basic

Diese exemplarische Vorgehensweise enthält eine Einführung in die Grundlagen der Datei-E/A in Visual Basic. Es wird beschrieben, wie Sie eine kleine Anwendung erstellen können, in der Textdateien in einem Verzeichnis aufgelistet und überprüft werden. Die Anwendung stellt Dateiattribute und die erste Zeile des Inhalts jeder ausgewählten Textdatei zur Verfügung. Es besteht die Möglichkeit, Informationen in eine Protokolldatei zu schreiben.  
  
 In dieser exemplarischen Vorgehensweise werden Member von `My.Computer.FileSystem Object` verwendet, die in Visual Basic verfügbar sind. Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.FileIO.FileSystem>. Am Ende dieser exemplarischen Vorgehensweise finden Sie ein entsprechendes Beispiel, in dem Klassen aus dem Namespace <xref:System.IO> verwendet werden.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1. Klicken Sie im Menü **Datei** auf **Neues Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2. Erweitern Sie im Bereich **Installierte Vorlagen** **Visual Basic**, und klicken Sie dann auf **Windows**. Klicken Sie im Bereich **Vorlagen** auf **Windows Forms-Anwendung**.  
  
3. Geben Sie im Feld **Name**`FileExplorer` ein, um den Projektnamen festzulegen, und klicken Sie anschließend auf **OK**.  
  
     Visual Studio fügt das Projekt in den **Projektmappen-Explorer** ein. Der Windows Forms-Designer wird geöffnet.  
  
4. Fügen Sie die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.  
  
    |Steuerelement|Eigenschaft|Wert|  
    |-------------|--------------|-----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button** (Schaltfläche)|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> **Browse** (Durchsuchen)|  
    |**Button** (Schaltfläche)|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> **Examine** (Untersuchen)|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> **Save Results** (Ergebnisse speichern)|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a>So wählen Sie einen Ordner und Listendateien in einem Ordner aus  
  
1. Erstellen Sie einen `Click`-Ereignishandler für `browseButton`, indem Sie auf ein Steuerelement im Formular doppelklicken. Der Code-Editor wird geöffnet.  
  
2. Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#103)]  
  
     Mit dem Aufruf `FolderBrowserDialog1.ShowDialog` wird das Dialogfeld **Ordner suchen** geöffnet. Sobald der Benutzer auf **OK** klickt, wird die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>-Eigenschaft als Argument an die `ListFiles`-Methode gesendet, die im nächsten Schritt hinzugefügt wird.  
  
3. Fügen Sie die folgende `ListFiles`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#104](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#104)]  
  
     Dieser Code löscht zuerst **ListBox**.  
  
     Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>-Methode ruft anschließend eine Auflistung von Zeichenfolgen ab, eine für jede Datei im Verzeichnis. Die Methode `GetFiles` akzeptiert ein Suchmusterargument, um Dateien abzurufen, die mit einem bestimmten Muster übereinstimmen. In diesem Beispiel werden nur Dateien mit der Dateiendung „.txt“ zurückgegeben.  
  
     Die Zeichenfolgen, die von der Methode `GetFiles` zurückgegeben werden, werden anschließend zu **ListBox** hinzugefügt.  
  
4. Führen Sie die Anwendung aus. Klicken Sie auf die Schaltfläche **Durchsuchen**. Navigieren Sie im Dialogfeld **Ordner suchen** zu einem Ordner, der .txt-Dateien enthält. Wählen Sie den Ordner anschließend aus, und klicken Sie auf **OK**.  
  
     `ListBox` enthält eine Liste von .txt-Dateien im ausgewählten Ordner.  
  
5. Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a>So rufen Sie Attribute einer Datei und Inhalt einer Textdatei ab  
  
1. Erstellen Sie einen `Click`-Ereignishandler für `examineButton`, indem Sie auf ein Steuerelement im Formular doppelklicken.  
  
2. Fügen Sie dem `Click`-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#105](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#105)]  
  
     Der Code stellt sicher, dass ein Element in `ListBox` ausgewählt ist. Anschließend ruft er den Eintrag des Dateipfads aus `ListBox` ab. Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A>-Methode wird verwendet, um zu überprüfen, ob die Datei noch vorhanden ist.  
  
     Der Dateipfad wird als Argument an die `GetTextForOutput`-Methode gesendet, die im nächsten Schritt hinzugefügt wird. Diese Methode gibt eine Zeichenfolge zurück, die Dateiinformationen enthält. Die Dateiinformationen werden in einer **MessageBox** angezeigt.  
  
3. Fügen Sie die folgende `GetTextForOutput`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#107](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#107)]  
  
     Der Code verwendet die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>-Methode zum Abrufen von Dateiparametern. Die Dateiparameter werden einem <xref:System.Text.StringBuilder> hinzugefügt.  
  
     Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>-Methode liest den Dateiinhalt in ein <xref:System.IO.StreamReader>-Element aus. Die erste Zeile des Inhalts wird von `StreamReader` abgerufen und zu `StringBuilder` hinzugefügt.  
  
4. Führen Sie die Anwendung aus. Klicken Sie auf **Durchsuchen**, und suchen Sie nach einem Ordner, der .txt-Dateien enthält. Klicken Sie auf **OK**.  
  
     Wählen Sie eine Datei aus `ListBox` aus, und klicken Sie anschließend auf **Examine** (Untersuchen). Die Dateiinformationen werden von `MessageBox` angezeigt.  
  
5. Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-add-a-log-entry"></a>So fügen Sie einen Protokolleintrag hinzu  
  
1. Fügen Sie am Ende des `examineButton_Click`-Ereignishandlers folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#106](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#106)]  
  
     Der Protokolldateipfad wird vom Code so festgelegt, dass die Protokolldatei in dem Verzeichnis gespeichert wird, das auch das Verzeichnis der ausgewählten Datei ist. Der Text der Protokolldatei wird auf das aktuelle Datum und die Uhrzeit sowie die Dateiinformationen festgelegt.  
  
     Zum Erstellen des Protokolleintrags wird die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>-Methode verwendet, deren `append`-Argument auf `True` festgelegt ist.  
  
2. Führen Sie die Anwendung aus. Navigieren Sie zu einer Textdatei, wählen Sie diese in `ListBox` aus, aktivieren Sie das Kontrollkästchen **Save Results** (Ergebnisse speichern), und klicken Sie auf **Examine** (Untersuchen). Stellen Sie sicher, dass der Protokolleintrag in die `log.txt`-Datei geschrieben ist.  
  
3. Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-use-the-current-directory"></a>So verwenden Sie das aktuelle Verzeichnis  
  
1. Erstellen Sie einen Ereignishandler für `Form1_Load`, indem Sie auf das Formular doppelklicken.  
  
2. Fügen Sie dem Ereignishandler folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#102)]  
  
     Durch diesen Code wird das Standardverzeichnis auf den Browser des Ordners zum aktuellen Verzeichnis festgelegt.  
  
3. Führen Sie die Anwendung aus. Wenn Sie zum ersten Mal auf **Durchsuchen** klicken, wird das Dialogfeld **Ordner suchen** im aktuellen Verzeichnis geöffnet.  
  
4. Beenden Sie die Ausführung der Anwendung.  
  
### <a name="to-selectively-enable-controls"></a>So aktivieren Sie Steuerelemente selektiv  
  
1. Fügen Sie die folgende `SetEnabled`-Methode hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#108](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#108)]  
  
     Die Methode `SetEnabled` aktiviert oder deaktiviert Steuerelemente. Dies hängt davon ab, ob ein Element in `ListBox` ausgewählt ist.  
  
2. Erstellen Sie einen `SelectedIndexChanged`-Ereignishandler für `filesListBox`, indem Sie auf das Steuerelement `ListBox` im Formular doppelklicken.  
  
3. Fügen Sie im Ereignishandler `filesListBox_SelectedIndexChanged` einen Aufruf von `SetEnabled` hinzu.  
  
4. Fügen Sie am Ende des Ereignishandlers `browseButton_Click` einen Aufruf von `SetEnabled` hinzu.  
  
5. Fügen Sie am Ende des Ereignishandlers `Form1_Load` einen Aufruf von `SetEnabled` hinzu.  
  
6. Führen Sie die Anwendung aus. Das Kontrollkästchen **Save Results** (Ergebnisse speichern) und die Schaltfläche **Examine** (Untersuchen) sind deaktiviert, wenn ein Element nicht in `ListBox` ausgewählt ist.  
  
## <a name="full-example-using-mycomputerfilesystem"></a>Ausführliches Beispiel mit Verwendung von „My.Computer.FileSystem“  

 Im Folgenden sehen Sie das vollständige Beispiel.  
  
 [!code-vb[VbVbcnMyFileSystem#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class2.vb#101)]  
  
## <a name="full-example-using-systemio"></a>Ausführliches Beispiel mit Verwendung von „System.IO“  

 Im folgenden entsprechenden Beispiel werden Klassen aus dem Namespace <xref:System.IO> anstelle von `My.Computer.FileSystem`-Objekten verwendet.  
  
 [!code-vb[VbVbcnMyFileSystem#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/class3.vb#111)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>
- [Exemplarische Vorgehensweise: Bearbeiten von Dateien mit .NET Framework-Methoden](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)
