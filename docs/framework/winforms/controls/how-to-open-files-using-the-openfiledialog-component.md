---
title: 'Gewusst wie: Öffnen von Dateien mit der OpenFileDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], opening files
- OpenFile method [Windows Forms], OpenFileDialog component
- files [Windows Forms], opening with OpenFileDialog component
ms.assetid: 9d88367a-cc21-4ffd-be74-89fd63767d35
ms.openlocfilehash: d7e1ebb319576aa7a38d55d8cb9f3652626966b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542274"
---
# <a name="how-to-open-files-using-the-openfiledialog-component"></a>Gewusst wie: Öffnen von Dateien mit der OpenFileDialog-Komponente
Die <xref:System.Windows.Forms.OpenFileDialog> Komponente ermöglicht Benutzern das Durchsuchen Sie die Ordner von ihrem Computer oder einem beliebigen Computer im Netzwerk, und wählen Sie eine oder mehrere Dateien zu öffnen. Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück.  
  
 Sobald der Benutzer die Datei ausgewählt hat, die geöffnet werden soll, gibt es zwei Möglichkeiten zum Öffnen der Datei. Wenn Sie mit Dateistreams arbeiten lieber, erstellen Sie eine Instanz von der <xref:System.IO.StreamReader> Klasse. Alternativ können Sie die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode, um die ausgewählte Datei geöffnet.  
  
 Das erste Beispiel unten umfasst eine <xref:System.Security.Permissions.FileIOPermission> berechtigungsüberprüfung (wie in "Sicherheitshinweis" weiter unten beschrieben), aber ermöglicht Ihnen Zugriff auf den Dateinamen. Diese Vorgehensweise können Sie in den Zonen „Lokaler Computer“, „Intranet“ und „Internet“ befolgen. Auch die zweite Methode ist eine <xref:System.Security.Permissions.FileIOPermission> Überprüfung der Berechtigung, doch eignet sich besser für Anwendungen, in dem Intranet oder Internet Zonen.  
  
### <a name="to-open-a-file-as-a-stream-using-the-openfiledialog-component"></a>So öffnen Sie eine Datei mit der OpenFileDialog-Komponente als Stream  
  
1.  Zeigen Sie das Dialogfeld **Datei öffnen** an, und rufen Sie eine Methode zum Öffnen der vom Benutzer ausgewählten Datei auf.  
  
     Eine Möglichkeit ist die Verwendung der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode zeigt das Dialogfeld Datei öffnen und Verwenden einer Instanz von der <xref:System.IO.StreamReader> Klasse, um die Datei zu öffnen.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler hinzu, öffnen Sie eine Instanz von der <xref:System.Windows.Forms.OpenFileDialog> Komponente. Wenn eine Datei ausgewählt wird und der Benutzer auf **OK** klickt, wird die im Dialogfeld markierte Datei geöffnet. In diesem Fall wird der Inhalt in einem Meldungsfeld angezeigt, um darüber zu informieren, dass der Dateistream gelesen wurde.  
  
    > [!IMPORTANT]
    >  Zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A> -Eigenschaft, die Assembly muss eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     Im Beispiel wird vorausgesetzt, das Formular verfügt über eine <xref:System.Windows.Forms.Button> Steuerelement und ein <xref:System.Windows.Forms.OpenFileDialog> Komponente.  
  
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
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
    > [!NOTE]
    >  Weitere Informationen zum Lesen aus Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginRead%2A> und <xref:System.IO.FileStream.Read%2A>.  
  
### <a name="to-open-a-file-as-a-file-using-the-openfiledialog-component"></a>So öffnen Sie eine Datei mit der OpenFileDialog-Komponente  
  
1.  Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld anzuzeigen und die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode, um die Datei zu öffnen.  
  
     Die <xref:System.Windows.Forms.OpenFileDialog> Komponente <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode gibt die Bytes der Datei zurück. Diese Bytes bilden einen Stream, aus dem Sie Daten lesen können. Im folgenden Beispiel wird ein <xref:System.Windows.Forms.OpenFileDialog> Komponente instanziiert wird, mit einem Filter "Cursor" auf, dadurch kann der Benutzer nur Dateien mit der Dateinamenerweiterung wählen`.cur`. Bei Wahl einer `.cur`-Datei wird der Cursor in der ausgewählten Form angezeigt.  
  
    > [!IMPORTANT]
    >  Aufrufen der <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> -Methode, die Assembly muss eine Berechtigungsebene gewährt durch die <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> Klasse. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     Im Beispiel wird vorausgesetzt, das Formular verfügt über eine <xref:System.Windows.Forms.Button> Steuerelement.  
  
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
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
