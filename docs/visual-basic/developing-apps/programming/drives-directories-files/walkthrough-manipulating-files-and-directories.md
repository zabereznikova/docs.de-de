---
title: "Walkthrough: Manipulating Files and Directories in Visual Basic | Microsoft Docs"
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
  - "files, reading text"
  - "reading files, text"
  - "I/O [Visual Basic], walkthroughs"
  - "text, writing to files"
  - "text, reading from files"
  - "reading text from files, walkthroughs"
  - "Visual Basic code, file access"
  - "files, writing text"
  - "I/O [Visual Basic], writing text to files"
  - "file access, walkthroughs"
  - "writing to files, walkthroughs"
  - "I/O [Visual Basic], reading text from files"
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 49
---
# Walkthrough: Manipulating Files and Directories in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Diese exemplarische Vorgehensweise bietet Ihnen eine Einführung in die Grundlagen der Datei\-E\/A in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].  Sie beschreibt, wie eine kleine Anwendung erstellt wird, von der Textdateien in einem Verzeichnis aufgeführt und überprüft werden.  Für alle markierten Textdateien werden von der Anwendung Dateiattribute und die erste Zeile des Inhalts bereitgestellt.  Eine Option zum Schreiben von Informationen in eine Protokolldatei steht zur Verfügung.  
  
 Diese exemplarische Vorgehensweise verwendet Mitglieder von `My.Computer.FileSystem Object`, die in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verfügbar sind.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.FileIO.FileSystem>.  Am Ende der exemplarischen Vorgehensweise wird ein entsprechendes Beispiel bereitgestellt, das Klassen vom <xref:System.IO>\-Namespace verwendet.  
  
 [!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### So erstellen Sie das Projekt  
  
1.  Klicken Sie im Menü **Datei** auf **Neues Projekt**.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
2.  Erweitern Sie im Bereich **Installierte Vorlagen** den Eintrag **Visual Basic**, und klicken Sie dann auf **Windows**.  Klicken Sie in der Mitte im Bereich **Vorlagen** auf **Windows Forms\-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `FileExplorer` ein, um den Projektnamen festzulegen, und klicken Sie dann auf **OK**.  
  
     Das Projekt wird von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] dem **Projektmappen\-Explorer** hinzugefügt, und der Windows Forms\-Designer wird geöffnet.  
  
4.  Fügen Sie dem Formular die in der folgenden Tabelle genannten Steuerelemente hinzu, und legen Sie deren Eigenschaften wie beschrieben fest.  
  
    |Steuerelement|Property|Wert|  
    |-------------------|--------------|----------|  
    |**ListBox**|**Name**|`filesListBox`|  
    |**Button**|**Name**<br /><br /> **Text**|`browseButton`<br /><br /> Durchsuchen|  
    |**Button**|**Name**<br /><br /> **Text**|`examineButton`<br /><br /> Examine|  
    |**CheckBox**|**Name**<br /><br /> **Text**|`saveCheckBox`<br /><br /> Save Results|  
    |**FolderBrowserDialog**|**Name**|`FolderBrowserDialog1`|  
  
### So wählen Sie einen Ordner aus und listen Dateien in einem Ordner auf  
  
1.  Erstellen Sie einen `Click`\-Ereignishandler für `browseButton`, indem Sie auf das Steuerelement im Formular doppelklicken.  Der Code\-Editor wird geöffnet.  
  
2.  Fügen Sie dem `Click`\-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     Mit dem `FolderBrowserDialog1.ShowDialog`\-Aufruf wird das Dialogfeld **Ordner suchen** geöffnet.  Nach dem Klicken auf **OK** wird die <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>\-Eigenschaft als Argument an die `ListFiles`\-Methode gesendet, die im nächsten Schritt hinzugefügt wird.  
  
3.  Fügen Sie die folgende `ListFiles`\-Methode hinzu:  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     Mit diesem Code wird zuerst **ListBox** gelöscht.  
  
     Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>\-Methode ruft dann eine Auflistung von Zeichenfolgen ab, und zwar eine für jede Datei im Verzeichnis.  Die `GetFiles`\-Methode akzeptiert ein Suchmusterargument zum Abrufen von Dateien, die einem bestimmten Muster entsprechen.  In diesem Beispiel werden nur Dateien mit der Erweiterung ".txt" zurückgegeben.  
  
     Die von der `GetFiles`\-Methode zurückgegebenen Zeichenfolgen werden dann zu **ListBox** hinzugefügt.  
  
4.  Führen Sie die Anwendung aus.  Klicken Sie auf die Schaltfläche **Durchsuchen**.  Navigieren Sie im Dialogfeld **Ordner suchen** zu einem Ordner, der TXT\-Dateien enthält. Markieren Sie dann diesen Ordner, und klicken Sie auf **OK**.  
  
     `ListBox` enthält eine Liste der TXT\-Dateien im ausgewählten Ordner.  
  
5.  Halten Sie die Anwendung an.  
  
### So rufen Sie Attribute einer Datei und Inhalt aus einer Textdatei ab  
  
1.  Erstellen Sie einen `Click`\-Ereignishandler für `examineButton`, indem Sie auf das Steuerelement im Formular doppelklicken.  
  
2.  Fügen Sie dem `Click`\-Ereignishandler den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     Der Code überprüft, ob ein Element in `ListBox` ausgewählt ist.  Anschließend wird der Dateipfadeintrag aus `ListBox` abgerufen.  Mithilfe der <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A>\-Methode wird überprüft, ob die Datei noch vorhanden ist.  
  
     Der Dateipfad wird als Argument an die `GetTextForOutput`\-Methode gesendet, die im nächsten Schritt hinzugefügt wird.  Mit dieser Methode wird eine Zeichenfolge zurückgegeben, die Dateiinformationen enthält.  Die Dateiinformationen werden in **MessageBox** angezeigt.  
  
3.  Fügen Sie die folgende `GetTextForOutput`\-Methode hinzu:  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     Der Code ruft mithilfe der <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A>\-Methode Dateiparameter ab.  Die Dateiparameter werden zu <xref:System.Text.StringBuilder> hinzugefügt.  
  
     Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>\-Methode liest den Dateiinhalt in <xref:System.IO.StreamReader> ein.  Die erste Zeile des Inhalts wird von `StreamReader` abgerufen und zu `StringBuilder` hinzugefügt.  
  
4.  Führen Sie die Anwendung aus.  Klicken Sie auf **Durchsuchen**, und navigieren Sie zu einem Ordner, der TXT\-Dateien enthält.  Klicken Sie auf **OK**.  
  
     Wählen Sie eine Datei in `ListBox` aus, und klicken Sie anschließend auf die Schaltfläche zum Überprüfen.  In `MessageBox` werden die Dateiinformationen angezeigt.  
  
5.  Halten Sie die Anwendung an.  
  
### So fügen Sie einen Protokolleintrag hinzu  
  
1.  Fügen Sie am Ende des `examineButton_Click`\-Ereignishandlers folgenden Code hinzu:  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     Vom Code wird der Protokolldateipfad festgelegt, damit die Protokolldatei im selben Verzeichnis abgelegt wird wie die ausgewählte Datei.  Für den Text des Protokolleintrags wird das aktuelle Datum und die aktuelle Uhrzeit festgelegt, gefolgt von den Dateiinformationen.  
  
     Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>\-Methode, für die das `append`\-Argument auf `True` festgelegt ist, wird zum Erstellen des Protokolleintrags verwendet.  
  
2.  Führen Sie die Anwendung aus.  Navigieren Sie zu einer Textdatei, und wählen Sie sie in `ListBox` aus. Aktivieren Sie das Kontrollkästchen **Ergebnisse speichern**, und klicken Sie anschließend auf die Schaltfläche zum Überprüfen.  Überprüfen Sie, ob der Protokolleintrag in die `log.txt`\-Datei geschrieben wird.  
  
3.  Halten Sie die Anwendung an.  
  
### So verwenden Sie das aktuelle Verzeichnis  
  
1.  Erstellen Sie einen Ereignishandler für `Form1_Load`, indem Sie auf das Formular doppelklicken.  
  
2.  Fügen Sie dem Ereignishandler folgenden Code hinzu:  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     Mit diesem Code wird für das Standardverzeichnis des Ordnerbrowsers das aktuelle Verzeichnis festgelegt.  
  
3.  Führen Sie die Anwendung aus.  Wenn Sie das erste Mal auf **Durchsuchen** klicken, wird das Dialogfeld **Ordner suchen** mit dem aktuellen Verzeichnis geöffnet.  
  
4.  Halten Sie die Anwendung an.  
  
### So aktivieren Sie selektiv Steuerelemente  
  
1.  Fügen Sie die folgende `SetEnabled`\-Methode hinzu:  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     Die `SetEnabled`\-Methode aktiviert oder deaktiviert Steuerelemente abhängig davon, ob ein Element in `ListBox` ausgewählt wird.  
  
2.  Erstellen Sie einen `SelectedIndexChanged`\-Ereignishandler für `filesListBox`, indem Sie auf das `ListBox`\-Steuerelement auf dem Formular doppelklicken.  
  
3.  Fügen Sie `SetEnabled` im neuen `filesListBox_SelectedIndexChanged`\-Ereignishandler einen Aufruf hinzu.  
  
4.  Fügen Sie `SetEnabled` einen Aufruf am Ende des `browseButton_Click`\-Ereignishandlers hinzu.  
  
5.  Fügen Sie `SetEnabled` einen Aufruf am Ende des `Form1_Load`\-Ereignishandlers hinzu.  
  
6.  Führen Sie die Anwendung aus.  Das Kontrollkästchen **Ergebnisse speichern** und die Schaltfläche zum Überprüfen werden deaktiviert, wenn ein Element nicht im `ListBox` ausgewählt wird.  
  
## Vollständiges Beispiel für My.Computer.FileSystem  
 Nachfolgend ist das vollständige Beispiel angegeben:  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## Vollständiges Beispiel für System.IO  
 Im folgenden entsprechenden Beispiel werden Klassen vom <xref:System.IO>\-Namespace anstelle von `My.Computer.FileSystem`\-Objekten verwendet.  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## Siehe auch  
 <xref:System.IO>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>   
 [Walkthrough: Manipulating Files by Using .NET Framework Methods](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)