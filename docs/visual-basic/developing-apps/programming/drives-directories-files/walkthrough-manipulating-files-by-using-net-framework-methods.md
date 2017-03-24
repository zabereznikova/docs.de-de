---
title: "Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic) | Microsoft Docs"
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
  - "I/O [Visual Basic], walkthroughs"
  - "text files, writing to"
  - "reading text files"
  - "text, writing to files"
  - "files, searching"
  - "StreamReader class, walkthroughs"
  - "files, accessing"
  - "I/O [Visual Basic], writing text to files"
  - "writing to files, walkthroughs"
  - "StreamWriter class, walkthroughs"
  - "text files, reading"
  - "I/O [Visual Basic], reading text from files"
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Walkthrough: Manipulating Files by Using .NET Framework Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

In dieser exemplarischen Vorgehensweise wird erläutert, wie Sie mithilfe der <xref:System.IO.StreamReader>\-Klasse Dateien öffnen und lesen, mit einer Instanz der <xref:System.IO.StreamReader>\-Klasse in eingelesenen Dateien nach einer Zeichenfolge suchen und mithilfe der <xref:System.IO.StreamWriter>\-Klasse in Dateien schreiben.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Erstellen der Anwendung  
 Starten Sie [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)], und beginnen Sie mit dem Projekt, indem Sie ein Formular erstellen, das der Benutzer zum Schreiben in die vorgesehene Datei verwenden kann.  
  
#### So erstellen Sie das Projekt  
  
1.  Wählen Sie im Menü **Datei** die Option **Neues Projekt** aus.  
  
2.  Klicken Sie im Bereich **Neues Projekt** auf **Windows\-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `MyDiary` ein, und klicken Sie auf **OK**.  
  
     Das Projekt wird von [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs-md.md)] dem **Projektmappen\-Explorer** hinzugefügt, und der **Windows Forms\-Designer** wird geöffnet.  
  
4.  Fügen Sie dem Formular die in der folgenden Tabelle genannten Steuerelemente hinzu, und legen Sie deren Eigenschaften wie beschrieben fest.  
  
||||  
|-|-|-|  
|**Objekt**|**Eigenschaften**|**Wert**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> Eintrag übermitteln|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> Eintrag leeren|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Eintrag`<br /><br /> Bitte geben Sie Text ein.<br /><br /> `False`|  
  
## Schreiben in die Datei  
 Verwenden Sie die <xref:System.IO.StreamWriter>\-Klasse, um die Möglichkeit hinzuzufügen, über die Anwendung in eine Datei zu schreiben.  Mit <xref:System.IO.StreamWriter> werden Zeichen in einer bestimmten Codierung ausgegeben. Die <xref:System.IO.Stream>\-Klasse wird dagegen zur Eingabe und Ausgabe von Bytes verwendet.  Verwenden Sie <xref:System.IO.StreamWriter>, um Zeilen mit Informationen in eine Standardtextdatei zu schreiben.  Weitere Informationen zur <xref:System.IO.StreamWriter>\-Klasse finden Sie unter <xref:System.IO.StreamWriter>.  
  
#### So fügen Sie die Funktionalität für das Schreiben hinzu  
  
1.  Klicken Sie im Menü **Ansicht** auf **Code**, um den Code\-Editor zu öffnen.  
  
2.  Da die Anwendung auf den <xref:System.IO>\-Namespace verweist, fügen Sie die folgenden Anweisungen ganz am Anfang des Codes ein, vor der Klassendeklaration für das Formular, die mit `Public Class Form1` beginnt.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     Vor dem Schreiben in die Datei müssen Sie eine Instanz einer <xref:System.IO.StreamWriter>\-Klasse erstellen.  
  
3.  Klicken Sie im Menü **Ansicht** auf **Designer**, um zum **Windows Forms\-Designer** zurückzuwechseln.  Doppelklicken Sie auf die Schaltfläche `Submit`, um einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die Schaltfläche zu erstellen, und fügen Sie dann den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  Die integrierte Entwicklungsumgebung \(IDE\) von Visual Studio wechselt zum Code\-Editor zurück und positioniert die Einfügemarke im Event\-Handler, in dem der Code hinzugefügt werden soll.  
  
1.  Verwenden Sie zum Schreiben der Datei die <xref:System.IO.StreamWriter.Write%2A>\-Methode der <xref:System.IO.StreamWriter>\-Klasse.  Fügen Sie folgenden Code direkt nach `Dim fw As StreamWriter` ein.  Wenn die Datei nicht gefunden wird, wird keine Ausnahme ausgelöst, sondern die Datei wird erstellt.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  Um sicherzustellen, dass der Benutzer keinen leeren Eintrag übermitteln kann, fügen Sie folgenden Code direkt nach `Dim ReadString As String` ein.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  Da es sich hier um ein Tagebuch handelt, will der Benutzer wahrscheinlich jeden Eintrag mit einem Datum versehen.  Fügen Sie nach `fw = New StreamWriter("C:\MyDiary.txt", True)` folgenden Code ein, um die Variable `Today` auf das aktuelle Datum festzulegen.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  Fügen Sie anschließend Code zum Leeren der <xref:System.Windows.Forms.TextBox> an.  Fügen Sie hierzu dem <xref:System.Windows.Forms.Control.Click>\-Ereignis der Schaltfläche `Clear` folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## Hinzufügen von Anzeigefeatures zum Tagebuch  
 In diesem Abschnitt fügen Sie ein Feature hinzu, mit dem der letzte Eintrag in der `DisplayEntry` <xref:System.Windows.Forms.TextBox> angezeigt wird.  Sie können auch eine <xref:System.Windows.Forms.ComboBox> hinzufügen, die mehrere Einträge anzeigt, und in der der Benutzer einen Eintrag für die Anzeige in der `DisplayEntry` <xref:System.Windows.Forms.TextBox> auswählen kann.  Eine Instanz der <xref:System.IO.StreamReader>\-Klasse liest aus `MyDiary.txt`.  Ebenso wie die <xref:System.IO.StreamWriter>\-Klasse ist <xref:System.IO.StreamReader> für die Verwendung mit Textdateien vorgesehen.  
  
 In diesem Abschnitt der exemplarischen Vorgehensweise fügen Sie dem Formular die in der folgenden Tabelle genannten Steuerelemente hinzu und legen deren Eigenschaften wie beschrieben fest.  
  
|Steuerelement|Eigenschaften|Werte|  
|-------------------|-------------------|-----------|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **Größe**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Anzeige`<br /><br /> Anzeige|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> Einträge abrufen|  
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`PickEntries`<br /><br /> Eintrag auswählen<br /><br /> `False`|  
  
#### So füllen Sie das Kombinationsfeld mit Daten  
  
1.  In der `PickEntries` <xref:System.Windows.Forms.ComboBox> werden die Tage angezeigt, an denen die einzelnen Einträge übermittelt wurden, sodass ein Eintrag mit einem bestimmten Datum ausgewählt werden kann.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die `GetEntries`\-Schaltfläche, und fügen Sie den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  Testen Sie den Code, indem Sie F5 drücken, um die Anwendung zu kompilieren, und klicken Sie dann auf **Einträge abrufen**.  Klicken Sie auf den Abwärtspfeil in der <xref:System.Windows.Forms.ComboBox>, um die Tage mit den einzelnen Einträgen anzuzeigen.  
  
#### So wählen Sie einzelne Einträge aus und zeigen sie an  
  
1.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die `Display`\-Schaltfläche, und fügen Sie den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  Testen Sie den Code, indem Sie F5 drücken, um die Anwendung zu kompilieren, und übermitteln Sie dann einen Eintrag.  Klicken Sie auf **Einträge abrufen**, wählen Sie in der <xref:System.Windows.Forms.ComboBox> einen Eintrag aus, und klicken Sie dann auf **Anzeigen**.  Der Inhalt des ausgewählten Eintrags wird in der `DisplayEntry` <xref:System.Windows.Forms.TextBox> angezeigt.  
  
## Benutzern die Möglichkeit zum Bearbeiten und Löschen von Einträgen geben  
 Sie können zusätzliche Features zum Bearbeiten und Löschen von Einträgen mit einer `EditEntry`\-Schaltfläche und einer `DeleteEntry`\-Schaltfläche integrieren.  Beide Schaltflächen werden erst aktiviert, wenn ein Eintrag angezeigt wird.  
  
 Fügen Sie dem Formular die in der folgenden Tabelle genannten Steuerelemente hinzu, und legen Sie deren Eigenschaften wie beschrieben fest.  
  
|Steuerelement|Eigenschaften|Werte|  
|-------------------|-------------------|-----------|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`DeleteEntry`<br /><br /> Eintrag löschen<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`EditEntry`<br /><br /> Eintrag bearbeiten<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`SubmitEdit`<br /><br /> Änderung übermitteln<br /><br /> `False`|  
  
#### So ermöglichen Sie das Löschen und Bearbeiten von Einträgen  
  
1.  Fügen Sie dem <xref:System.Windows.Forms.Control.Click>\-Ereignis der `Display`\-Schaltfläche nach `DisplayEntry.Text = ReadString` folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die `DeleteEntry`\-Schaltfläche, und fügen Sie den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  Wenn ein Benutzer einen Eintrag anzeigt, wird die `EditEntry`\-Schaltfläche aktiviert.  Fügen Sie dem <xref:System.Windows.Forms.Control.Click>\-Ereignis der `Display`\-Schaltfläche nach `DisplayEntry.Text = ReadString` folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die `EditEntry`\-Schaltfläche, und fügen Sie den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>\-Ereignishandler für die `SubmitEdit`\-Schaltfläche, und fügen Sie den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 Testen Sie den Code, indem Sie F5 drücken, um die Anwendung zu kompilieren.  Klicken Sie auf **Einträge abrufen**, wählen Sie einen Eintrag aus, und klicken Sie dann auf **Anzeigen**.  Der Eintrag wird in der `DisplayEntry` <xref:System.Windows.Forms.TextBox> angezeigt.  Klicken Sie auf **Eintrag bearbeiten**.  Der Eintrag wird in der `Entry` <xref:System.Windows.Forms.TextBox> angezeigt.  Bearbeiten Sie den Eintrag in der `Entry` <xref:System.Windows.Forms.TextBox>, und klicken Sie auf **Bearbeitung senden**.  Öffnen Sie die Datei `MyDiary.txt`, um die Änderung zu bestätigen.  Wählen Sie jetzt einen Eintrag aus, und klicken Sie auf **Eintrag löschen**.  Klicken Sie bei entsprechender Aufforderung durch die <xref:System.Windows.Forms.MessageBox> auf **OK**, um den Löschvorgang zu bestätigen.  Schließen Sie die Anwendung, und öffnen Sie die Datei `MyDiary.txt`, um die Löschung zu bestätigen.  
  
## Siehe auch  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Walkthroughs](../../../../visual-basic/walkthroughs.md)