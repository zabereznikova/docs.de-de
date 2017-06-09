---
title: "Gewusst wie: &#214;ffnen von Dateien mit der OpenFileDialog-Komponente | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Dateien, Öffnen mit der OpenFileDialog-Komponente"
  - "OpenFile-Methode"
  - "OpenFile-Methode, OpenFileDialog-Komponente"
  - "OpenFileDialog-Komponente, Öffnen von Dateien"
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Gewusst wie: &#214;ffnen von Dateien mit der OpenFileDialog-Komponente
Mit der <xref:System.Windows.Forms.OpenFileDialog>\-Komponente können Benutzer die Ordner ihres Computers bzw. eines beliebigen Computers im Netzwerk durchsuchen und eine oder mehrere Dateien öffnen.  Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück.  
  
 Sobald der Benutzer die Datei ausgewählt hat, die geöffnet werden soll, gibt es zwei Möglichkeiten für das Öffnen der Datei.  Wenn Sie bevorzugt mit Dateistreams arbeiten, können Sie eine Instanz der <xref:System.IO.StreamReader>\-Klasse erstellen.  Alternativ dazu können Sie die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>\-Methode zum Öffnen der ausgewählten Datei verwenden.  
  
 Das erste unten stehende Beispiel enthält <xref:System.Security.Permissions.FileIOPermission> zur Überprüfung der Berechtigungen \(wie im Sicherheitshinweis unten beschrieben\), ermöglicht jedoch den Zugriff auf den Dateinamen.  Diese Vorgehensweise können Sie in der lokalen Zone sowie in der Intranet\- und Internetzone verwenden.  Die zweite Methode führt ebenfalls <xref:System.Security.Permissions.FileIOPermission> zur Überprüfung der Berechtigungen durch, ist jedoch besser für Anwendungen in der Intranet\- oder Internetzone geeignet.  
  
### So öffnen Sie eine Datei mit der OpenFileDialog\-Komponente als Stream  
  
1.  Zeigen Sie das Dialogfeld **Datei öffnen** an, und rufen Sie eine Methode zum Öffnen der vom Benutzer ausgewählten Datei auf.  
  
     Eine Möglichkeit ist die Verwendung der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode zum Anzeigen des Dialogfelds Datei öffnen sowie einer Instanz der <xref:System.IO.StreamReader>\-Klasse zum Öffnen der Datei.  
  
     Im folgenden Beispiel wird vom <xref:System.Windows.Forms.Control.Click>\-Ereignishandler des <xref:System.Windows.Forms.Button>\-Steuerelements eine Instanz der <xref:System.Windows.Forms.OpenFileDialog>\-Komponente geöffnet.  Wenn eine Datei ausgewählt wird und der Benutzer auf **OK** klickt, wird die im Dialogfeld markierte Datei geöffnet.  In diesem Fall wird der Inhalt in einem Meldungsfeld angezeigt, um darüber zu informieren, dass der Dateistream gelesen wurde.  
  
    > [!IMPORTANT]
    >  Zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A>\-Eigenschaft muss die Assembly über eine von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>\-Klasse gewährte Berechtigungsebene verfügen.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen dazu finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement und eine <xref:System.Windows.Forms.OpenFileDialog>\-Komponente verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If OpenFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         Dim sr As New System.IO.StreamReader(OpenFileDialog1.FileName)  
         MessageBox.Show(sr.ReadToEnd)  
         sr.Close()  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          System.IO.StreamReader sr = new   
             System.IO.StreamReader(openFileDialog1.FileName);  
          MessageBox.Show(sr.ReadToEnd());  
          sr.Close();  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             System::IO::StreamReader ^ sr = gcnew  
                System::IO::StreamReader(openFileDialog1->FileName);  
             MessageBox::Show(sr->ReadToEnd());  
             sr->Close();  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Weitere Informationen zum Lesen aus Dateistreams finden Sie unter [FileStream.BeginRead\-Methode](frlrfSystemIOFileStreamClassBeginReadTopic) und [FileStream.Read\-Methode](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx).  
  
### So öffnen Sie eine Datei mit der OpenFileDialog\-Komponente als Datei  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>\-Methode zum Anzeigen des Dialogfelds und die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>\-Methode zum Öffnen der Datei.  
  
     Die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>\-Methode der <xref:System.Windows.Forms.OpenFileDialog>\-Komponente gibt die Bytes zurück, aus denen die Datei besteht.  Diese Bytes bilden einen Stream, aus dem Sie Daten lesen können.  Im nachfolgenden Beispiel wird eine <xref:System.Windows.Forms.OpenFileDialog>\-Komponente mit einem "Cursorfilter" instanziiert. Damit kann der Benutzer nur Dateien mit der Dateinamenerweiterung `.cur` auswählen.  Wenn eine`.cur` \-Datei ausgewählt wird, wird der Cursor in der ausgewählten Form angezeigt.  
  
    > [!IMPORTANT]
    >  Zum Aufrufen der <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>\-Methode benötigt die Assembly eine von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>\-Klasse gewährte Berechtigungsebene.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen dazu finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement verfügt.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' Displays an OpenFileDialog so the user can select a Cursor.  
       Dim openFileDialog1 As New OpenFileDialog()  
       openFileDialog1.Filter = "Cursor Files|*.cur"  
       openFileDialog1.Title = "Select a Cursor File"  
  
       ' Show the Dialog.  
       ' If the user clicked OK in the dialog and   
       ' a .CUR file was selected, open it.  
       If openFileDialog1.ShowDialog() = System.Windows.Forms.DialogResult.OK Then  
         ' Assign the cursor in the Stream to the Form's Cursor property.  
         Me.Cursor = New Cursor(openFileDialog1.OpenFile())  
       End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // Displays an OpenFileDialog so the user can select a Cursor.  
       OpenFileDialog openFileDialog1 = new OpenFileDialog();  
       openFileDialog1.Filter = "Cursor Files|*.cur";  
       openFileDialog1.Title = "Select a Cursor File";  
  
       // Show the Dialog.  
       // If the user clicked OK in the dialog and  
       // a .CUR file was selected, open it.  
        if (openFileDialog1.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
       {  
          // Assign the cursor in the Stream to the Form's Cursor property.  
          this.Cursor = new Cursor(openFileDialog1.OpenFile());  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays an OpenFileDialog so the user can select a Cursor.  
          OpenFileDialog ^ openFileDialog1 = new OpenFileDialog();  
          openFileDialog1->Filter = "Cursor Files|*.cur";  
          openFileDialog1->Title = "Select a Cursor File";  
  
          // Show the Dialog.  
          // If the user clicked OK in the dialog and  
          // a .CUR file was selected, open it.  
          if (openFileDialog1->ShowDialog() == System::Windows::Forms::DialogResult::OK)  
          {  
             // Assign the cursor in the Stream to  
             // the Form's Cursor property.  
             this->Cursor = gcnew  
                System::Windows::Forms::Cursor(  
                openFileDialog1->OpenFile());  
          }  
       }  
  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## Siehe auch  
 <xref:System.Windows.Forms.OpenFileDialog>   
 [OpenFileDialog\-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)