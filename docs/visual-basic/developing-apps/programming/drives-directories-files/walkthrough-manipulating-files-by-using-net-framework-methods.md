---
title: Bearbeiten von Dateien mit .NET Framework-Methoden (Visual Basic) | Microsoft-Dokumentation
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
- I/O [Visual Basic], walkthroughs
- text files, writing to
- reading text files
- text, writing to files
- files, searching
- StreamReader class, walkthroughs
- files, accessing
- I/O [Visual Basic], writing text to files
- writing to files, walkthroughs
- StreamWriter class, walkthroughs
- text files, reading
- I/O [Visual Basic], reading text from files
ms.assetid: 7d2109eb-f98a-4389-b43d-30f384aaa7d5
caps.latest.revision: 18
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
ms.openlocfilehash: e8bf73f32dba51455542778ed91ef3bfd2898754
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-manipulating-files-by-using-net-framework-methods-visual-basic"></a>Exemplarische Vorgehensweise: Bearbeiten von Dateien mit .NET Framework-Methoden (Visual Basic)
In dieser exemplarischen Vorgehensweise wird gezeigt, wie man eine Datei mithilfe der Klasse <xref:System.IO.StreamReader> öffnet und liest, wie man überprüft, ob auf eine Datei zugegriffen wird, wie man innerhalb einer Datei, die mit einer Instanz der Klasse <xref:System.IO.StreamReader> gelesen wird, nach einer Zeichenfolge sucht, und wie man mithilfe der Klasse <xref:System.IO.StreamWriter> in eine Datei schreibt.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-application"></a>Erstellen der Anwendung  
 Starten Sie [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] und beginnen Sie das Projekt durch Erstellen eines Formulars, mit dem ein Benutzer in die festgelegte Datei schreiben kann.  
  
#### <a name="to-create-the-project"></a>So erstellen Sie das Projekt  
  
1.  Wählen Sie im Menü **Datei** die Option **Neues Projekt** aus.  
  
2.  Klicken Sie im Bereich **Neues Projekt** auf **Windows-Anwendung**.  
  
3.  Geben Sie im Feld **Name** die Bezeichnung `MyDiary` ein, und klicken Sie auf **OK**.  
  
     [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] fügt das Projekt in den **Projektmappen-Explorer** ein. Der **Windows Forms-Designer** wird geöffnet.  
  
4.  Fügen Sie die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.  
  
|**Objekt**|**Eigenschaften**|**Wert**|  
|---|---|---|   
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Submit`<br /><br /> **Eintrag eintragen**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Clear`<br /><br /> **Eintrag löschen**|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Text**<br /><br /> **Multiline**|`Entry`<br /><br /> **Bitte machen Sie eine Eingabe.**<br /><br /> `False`|  
  
## <a name="writing-to-the-file"></a>In eine Datei schreiben  
 Verwenden Sie die Klasse <xref:System.IO.StreamWriter>, um die Möglichkeit hinzuzufügen, über die Anwendung in eine Datei zu schreiben. <xref:System.IO.StreamWriter> ist für die Ausgabe von Zeichen in eine bestimmte Codierung vorgesehen, wohingegen die Klasse <xref:System.IO.Stream> für die Byte- Ein- und Ausgabe vorgesehen ist. Verwenden Sie <xref:System.IO.StreamWriter> zum Schreiben von Informationszeilen in eine Standardtextdatei. Weitere Informationen zur Klasse <xref:System.IO.StreamWriter> finden Sie unter <xref:System.IO.StreamWriter>.  
  
#### <a name="to-add-writing-functionality"></a>Funktionen zum Schreiben hinzufügen  
  
1.  Wählen Sie im Menü **Ansicht** **Code** aus, um den Code-Editor zu öffnen.  
  
2.  Da die Anwendung auf den Namespace <xref:System.IO> verweist, fügen Sie die folgenden Anweisungen ganz am Anfang Ihres Code hinzu, vor der Klassendeklaration für das Formular, die `Public Class Form1` startet.  
  
     [!code-vb[VbVbcnMyFileSystem#35](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_1.vb)]  
  
     Bevor Sie in eine Datei schreiben können, müssen Sie eine Instanz der Klasse <xref:System.IO.StreamWriter> erstellen.  
  
3.  Wählen Sie im Menü **Ansicht** **Designer** aus, um zum **Windows Forms-Designer** zurückzukehren. Doppelklicken Sie auf die Schaltfläche `Submit`, um einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche zu erstellen, und fügen Sie anschließend den folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_2.vb)]  
  
> [!NOTE]
>  Die Integrated Development Environment (Integrierte Entwicklungsumgebung, IDE) von Visual Studio kehrt zum Code-Editor zurück und platziert die Einfügemarke an der Stelle im Ereignishandler, an der Sie Code hinzufügen sollen.  
  
1.  Verwenden Sie zum Schreibe in die Datei die <xref:System.IO.StreamWriter.Write%2A>-Methode der <xref:System.IO.StreamWriter>-Klasse. Fügen Sie direkt hinter `Dim fw As StreamWriter` folgenden Code ein. Sie müssen sich keine Gedanken darüber machen, dass eine Ausnahme ausgelöst wird, wenn die Datei nicht gefunden wird, da diese erstellt wird, wenn sie noch nicht vorhanden ist.  
  
     [!code-vb[VbVbcnMyFileSystem#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_3.vb)]  
  
2.  Stellen Sie sicher, dass der Benutzer keine leeren Einträge eintragen kann, indem Sie direkt hinter `Dim ReadString As String` folgenden Code einfügen.  
  
     [!code-vb[VbVbcnMyFileSystem#38](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_4.vb)]  
  
3.  Da es sich hier um einen Kalender handelt, möchte der Benutzer vermutlich jedem Eintrag ein Datum zuweisen. Fügen Sie folgenden Code nach `fw = New StreamWriter("C:\MyDiary.txt", True)` ein, um die Variable `Today` auf das aktuelle Datum einzustellen.  
  
     [!code-vb[VbVbcnMyFileSystem#39](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_5.vb)]  
  
4.  Fügen Sie abschließend Code hinzu, um den Inhalt von <xref:System.Windows.Forms.TextBox> zu löschen. Fügen Sie folgenden Code zum Ereignis <xref:System.Windows.Forms.Control.Click> der Schaltfläche `Clear` hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#40](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_6.vb)]  
  
## <a name="adding-display-features-to-the-diary"></a>Hinzufügen von Anzeigefunktionen zum Kalender  
 In diesem Abschnitt fügen Sie eine Funktion hinzu, mit der der letzte Eintrag in `DisplayEntry`<xref:System.Windows.Forms.TextBox> angezeigt wird. Sie können auch <xref:System.Windows.Forms.ComboBox> hinzufügen, wodurch verschiedene Einträge angezeigt werden, aus denen ein Benutzer einen Eintrag auswählen kann, der in `DisplayEntry`<xref:System.Windows.Forms.TextBox> angezeigt wird. Eine Instanz der Klasse <xref:System.IO.StreamReader> liest aus `MyDiary.txt`. Genau wie die Klasse <xref:System.IO.StreamWriter> ist <xref:System.IO.StreamReader> für die Verwendung mit Textdateien vorgesehen.  
  
 Fügen Sie in diesem Abschnitt der exemplarischen Vorgehensweise die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.  
  
|Steuerelement|Eigenschaften|Werte|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.TextBox>|**Name**<br /><br /> **Visible**<br /><br /> **Size**<br /><br /> **Multiline**|`DisplayEntry`<br /><br /> `False`<br /><br /> `120,60`<br /><br /> `True`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`Display`<br /><br /> **Display**|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**|`GetEntries`<br /><br /> **Get Entries** (Einträge abrufen)|  
|<xref:System.Windows.Forms.ComboBox>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`PickEntries`<br /><br /> **Select an Entry** (Eintrag auswählen)<br /><br /> `False`|  
  
#### <a name="to-populate-the-combo-box"></a>Auffüllen des Kombinationsfelds  
  
1.  Das Kombinationsfeld `PickEntries`<xref:System.Windows.Forms.ComboBox> wird zum Anzeigen von Daten verwendet, an denen ein Benutzer einen Eintrag gemacht hat. Dadurch kann der Benutzer einen Eintrag von einem bestimmten Datum auswählen. Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche `GetEntries`, und fügen Sie folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#41](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_7.vb)]  
  
2.  Drücken Sie zum Testen des Codes F5, um die Anwendung zu kompilieren, und klicken Sie dann auf **Get Entries** (Einträge abrufen). Klicken Sie auf den Dropdownpfeil in <xref:System.Windows.Forms.ComboBox>, um die Daten der Einträge anzuzeigen.  
  
#### <a name="to-choose-and-display-individual-entries"></a>Auswählen und Anzeigen einzelner Einträge  
  
1.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche `Display`, und fügen Sie folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#42](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_8.vb)]  
  
2.  Drücken Sie zum Testen des Codes F5, um die Anwendung zu kompilieren, und machen Sie dann einen Eintrag. Klicken Sie auf **Get Entries** (Einträge abrufen), wählen Sie einen Eintrag aus <xref:System.Windows.Forms.ComboBox> aus, und klicken Sie anschließend auf **Anzeige**. Der Inhalt des ausgewählten Eintrags wird in `DisplayEntry`<xref:System.Windows.Forms.TextBox> angezeigt.  
  
## <a name="enabling-users-to-delete-or-modify-entries"></a>Benutzern das Löschen oder Ändern von Einträgen erlauben  
 Abschließend können Sie verschiedene Funktionen mit aufnehmen, die es Benutzern erlauben, einen Eintrag mithilfe der Schaltflächen `DeleteEntry` und `EditEntry` zu ändern oder zu löschen. Beide Schaltflächen sind deaktiviert bis ein Eintrag angezeigt wird.  
  
 Fügen Sie die Steuerelemente aus der folgenden Tabelle zum Formular hinzu, und legen Sie die entsprechenden Werte für die Eigenschaften fest.  
  
|Steuerelement|Eigenschaften|Werte|  
|-------------|----------------|------------|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`DeleteEntry`<br /><br /> **Eintrag löschen**<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`EditEntry`<br /><br /> **Edit Entry** (Eintrag bearbeiten)<br /><br /> `False`|  
|<xref:System.Windows.Forms.Button>|**Name**<br /><br /> **Text**<br /><br /> **Aktiviert**|`SubmitEdit`<br /><br /> **Submit Edit** (Änderung eintragen)<br /><br /> `False`|  
  
#### <a name="to-enable-deletion-and-modification-of-entries"></a>Löschen und Ändern von Eintragen aktivieren  
  
1.  Fügen Sie folgenden Code zum Ereignis <xref:System.Windows.Forms.Control.Click> der Schaltfläche `Display` hinter `DisplayEntry.Text = ReadString` hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#43](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_9.vb)]  
  
2.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche `DeleteEntry`, und fügen Sie folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#44](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_10.vb)]  
  
3.  Wenn ein Benutzer einen Eintrag anzeigt, wird die Schaltfläche `EditEntry` aktiviert. Fügen Sie folgenden Code zum Ereignis <xref:System.Windows.Forms.Control.Click> der Schaltfläche `Display` nach `DisplayEntry.Text = ReadString` hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#45](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_11.vb)]  
  
4.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche `EditEntry`, und fügen Sie folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#46](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_12.vb)]  
  
5.  Erstellen Sie einen <xref:System.Windows.Forms.Control.Click>-Ereignishandler für die Schaltfläche `SubmitEdit`, und fügen Sie folgenden Code hinzu.  
  
     [!code-vb[VbVbcnMyFileSystem#47](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-by-using-net-framework-methods_13.vb)]  
  
 Drücken Sie zum Testen des Codes F5, um die Anwendung zu kompilieren. Klicken Sie auf **Get Entries** (Einträge abrufen), wählen Sie einen Eintrag aus, und klicken Sie anschließend auf **Anzeige**. Der Eintrag wird in `DisplayEntry`<xref:System.Windows.Forms.TextBox> angezeigt. Klicken Sie auf **Edit Entry** (Eintrag bearbeiten). Der Eintrag wird in `Entry`<xref:System.Windows.Forms.TextBox> angezeigt. Bearbeiten Sie den Eintrag in `Entry`<xref:System.Windows.Forms.TextBox>, und klicken Sie auf **Submit Edit** (Änderung eintragen). Öffnen Sie die `MyDiary.txt`-Datei, um Ihre Korrekturen zu bestätigen. Wählen Sie jetzt einen Eintrag aus, und klicken Sie auf **Eintrag löschen**. Klicken Sie auf **OK**, wenn <xref:System.Windows.Forms.MessageBox> eine Bestätigung anfordert. Schließen Sie die Anwendung und öffnen Sie `MyDiary.txt`, um den Löschvorgang zu bestätigen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.StreamWriter>   
 [Exemplarische Vorgehensweisen](../../../../visual-basic/walkthroughs.md)

