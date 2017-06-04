---
title: "Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente | Microsoft Docs"
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
  - "Dateien, Speichern"
  - "OpenFile-Methode, Speichern von Dateien mit der SaveFileDialog-Komponente"
  - "SaveFileDialog-Komponente, Speichern von Dateien"
  - "Speichern von Dateien"
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente
Mit der <xref:System.Windows.Forms.SaveFileDialog>\-Komponente können Benutzer das Dateisystem durchsuchen und Dateien auswählen, die gespeichert werden sollen.  Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück.  Sie müssen jedoch den Code schreiben, mit dem die Dateien letztendlich auf den Datenträger geschrieben werden.  
  
### So speichern Sie eine Datei mit der SaveFileDialog\-Komponente  
  
-   Zeigen Sie das Dialogfeld **Datei speichern** an, und rufen Sie eine Methode zum Speichern der vom Benutzer ausgewählten Datei auf.  
  
     Verwenden Sie die <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>\-Methode der <xref:System.Windows.Forms.SaveFileDialog>\-Komponente zum Speichern der Datei.  Durch diese Methode erhalten Sie ein <xref:System.IO.Stream>\-Objekt, in das Sie schreiben können.  
  
     Im folgenden Beispiel wird die <xref:System.Windows.Forms.DialogResult>\-Eigenschaft zum Erfassen des Dateinamens und die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>\-Methode zum Speichern der Datei verwendet.  Durch die <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>\-Methode erhalten Sie einen Stream, in den die Datei geschrieben werden kann.  
  
     Das nachfolgende Beispiel enthält ein <xref:System.Windows.Forms.Button>\-Steuerelement, dem ein Bild zugewiesen wurde.  Wenn Sie auf die Schaltfläche klicken, wird eine <xref:System.Windows.Forms.SaveFileDialog>\-Komponente mit einem Filter instanziiert, der nur Dateien vom Typ GIF, JPEG und BMP zulässt.  Wenn eine Datei diesen Typs im Dialogfeld **Datei speichern** ausgewählt wird, wird das Bild der Schaltfläche gespeichert.  
  
    > [!IMPORTANT]
    >  Zum Abrufen oder Festlegen der <xref:System.Windows.Forms.FileDialog.FileName%2A>\-Eigenschaft muss die Assembly über eine von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>\-Klasse gewährte Berechtigungsebene verfügen.  Bei Ausführung in einer teilweise vertrauenswürdigen Umgebung kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.  Weitere Informationen dazu finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).  
  
     In diesem Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>\-Steuerelement verfügt, für dessen <xref:System.Windows.Forms.ButtonBase.Image%2A>\-Eigenschaft der Dateityp GIF, JPEG oder BMP festgelegt wurde.  
  
    > [!NOTE]
    >  Die <xref:System.Windows.Forms.FileDialog.FilterIndex%2A>\-Eigenschaft der <xref:System.Windows.Forms.FileDialog>\-Klasse \(die aufgrund von Vererbung Teil der <xref:System.Windows.Forms.SaveFileDialog>\-Klasse ist\) verwendet einen mit Eins beginnenden Index.  Dies ist von Bedeutung, wenn Sie Code zum Speichern von Daten in einem bestimmten Format schreiben \(z. B. Speichern einer Datei im Nur\-Text\-Format statt im Binärformat.  Diese Eigenschaft ist im nachfolgenden Beispiel enthalten.  
  
    ```vb  
    Private Sub Button2_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button2.Click  
       ' Displays a SaveFileDialog so the user can save the Image  
       ' assigned to Button2.  
       Dim saveFileDialog1 As New SaveFileDialog()  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"  
       saveFileDialog1.Title = "Save an Image File"  
       saveFileDialog1.ShowDialog()  
  
       ' If the file name is not an empty string open it for saving.  
       If saveFileDialog1.FileName <> "" Then  
          ' Saves the Image via a FileStream created by the OpenFile method.  
          Dim fs As System.IO.FileStream = Ctype _  
             (saveFileDialog1.OpenFile(), System.IO.FileStream)  
          ' Saves the Image in the appropriate ImageFormat based upon the  
          ' file type selected in the dialog box.  
          ' NOTE that the FilterIndex property is one-based.  
          Select Case saveFileDialog1.FilterIndex  
             Case 1  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Jpeg)  
  
             Case 2  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Bmp)  
  
             Case 3  
                Me.button2.Image.Save(fs, _  
                   System.Drawing.Imaging.ImageFormat.Gif)  
           End Select  
  
           fs.Close()  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button2_Click(object sender, System.EventArgs e)  
    {  
       // Displays a SaveFileDialog so the user can save the Image  
       // assigned to Button2.  
       SaveFileDialog saveFileDialog1 = new SaveFileDialog();  
       saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
       saveFileDialog1.Title = "Save an Image File";  
       saveFileDialog1.ShowDialog();  
  
       // If the file name is not an empty string open it for saving.  
       if(saveFileDialog1.FileName != "")  
       {  
          // Saves the Image via a FileStream created by the OpenFile method.  
          System.IO.FileStream fs =   
             (System.IO.FileStream)saveFileDialog1.OpenFile();  
          // Saves the Image in the appropriate ImageFormat based upon the  
          // File type selected in the dialog box.  
          // NOTE that the FilterIndex property is one-based.  
          switch(saveFileDialog1.FilterIndex)  
          {  
             case 1 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Jpeg);  
             break;  
  
             case 2 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Bmp);  
             break;  
  
             case 3 :   
             this.button2.Image.Save(fs,   
                System.Drawing.Imaging.ImageFormat.Gif);  
             break;  
          }  
  
       fs.Close();  
       }  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void button2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Displays a SaveFileDialog so the user can save the Image  
          // assigned to Button2.  
          SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();  
          saveFileDialog1->Filter =   
             "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";  
          saveFileDialog1->Title = "Save an Image File";  
          saveFileDialog1->ShowDialog();  
          // If the file name is not an empty string, open it for saving.  
          if(saveFileDialog1->FileName != "")  
          {  
             // Saves the Image through a FileStream created by  
             // the OpenFile method.  
             System::IO::FileStream ^ fs =   
                safe_cast<System::IO::FileStream*>(  
                saveFileDialog1->OpenFile());  
             // Saves the Image in the appropriate ImageFormat based on  
             // the file type selected in the dialog box.  
             // Note that the FilterIndex property is one based.  
             switch(saveFileDialog1->FilterIndex)  
             {  
                case 1 :  
                   this->button2->Image->Save(fs,  
                      System::Drawing::Imaging::ImageFormat::Jpeg);  
                   break;  
                case 2 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Bmp);  
                   break;  
                case 3 :  
                   this->button2->Image->Save(fs,   
                      System::Drawing::Imaging::ImageFormat::Gif);  
                   break;  
             }  
          fs->Close();  
          }  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Fügen Sie den folgenden Code im Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.button2.Click += new System.EventHandler(this.button2_Click);  
  
    ```  
  
    ```cpp  
    this->button2->Click += gcnew  
       System::EventHandler(this, &Form1::button2_Click);  
    ```  
  
     Weitere Informationen zum Schreiben von Dateistreams finden Sie unter [FileStream.BeginWrite\-Methode](frlrfSystemIOFileStreamClassBeginWriteTopic) und [FileStream.Write\-Methode](https://msdn.microsoft.com/en-us/library/system.io.filestream.write.aspx).  
  
    > [!NOTE]
    >  Einige Steuerelemente, z. B. das <xref:System.Windows.Forms.RichTextBox>\-Steuerelement, können Dateien speichern.  Weitere Informationen finden Sie im Artikel der MSDN Online Library [Essential Code for Windows Forms Dialog Boxes](http://go.microsoft.com/fwlink/?LinkID=102575) im Abschnitt "SaveFileDialog Component".  
  
## Siehe auch  
 <xref:System.Windows.Forms.SaveFileDialog>   
 [SaveFileDialog\-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)