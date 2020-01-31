---
title: 'Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: 32de7f7e38195271e179d4fae3884b7a39f37c45
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868082"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a>Gewusst wie: Speichern von Dateien mit der SaveFileDialog-Komponente

Die <xref:System.Windows.Forms.SaveFileDialog> Komponente ermöglicht es Benutzern, das Dateisystem zu durchsuchen und die zu speichernden Dateien auszuwählen. Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück. Sie müssen jedoch den Code schreiben, mit dem die Dateien letztendlich auf den Datenträger geschrieben werden.

### <a name="to-save-a-file-using-the-savefiledialog-component"></a>So speichern Sie eine Datei mit der SaveFileDialog-Komponente

- Zeigen Sie das Dialogfeld **Datei öffnen** an, und rufen Sie eine Methode zum Öffnen der vom Benutzer ausgewählten Datei auf.

  Verwenden Sie die <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>-Methode der <xref:System.Windows.Forms.SaveFileDialog> Komponente, um die Datei zu speichern. Diese Methode bietet Ihnen ein <xref:System.IO.Stream> Objekt, in das geschrieben werden kann.

  Im folgenden Beispiel wird die <xref:System.Windows.Forms.DialogResult>-Eigenschaft verwendet, um den Namen der Datei zu erhalten, und die <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A>-Methode, um die Datei zu speichern. Mit der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>-Methode erhalten Sie einen Stream, in den die Datei geschrieben werden soll.

  Im folgenden Beispiel gibt es ein <xref:System.Windows.Forms.Button>-Steuerelement, dem ein Bild zugewiesen ist. Wenn Sie auf die Schaltfläche klicken, wird eine <xref:System.Windows.Forms.SaveFileDialog> Komponente mit einem Filter instanziiert, der Dateien vom Typ. gif,. JPEG und BMP zulässt. Wenn eine Datei diesen Typs im Dialogfeld „Datei speichern“ ausgewählt wird, wird das Bild der Schaltfläche gespeichert.

  > [!IMPORTANT]
  > Um die <xref:System.Windows.Forms.FileDialog.FileName%2A>-Eigenschaft zu erhalten oder festzulegen, erfordert die Assembly eine Berechtigungsebene, die von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>-Klasse erteilt wird. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../misc/code-access-security-basics.md).

  Im Beispiel wird davon ausgegangen, dass das Formular über ein <xref:System.Windows.Forms.Button>-Steuerelement verfügt, dessen <xref:System.Windows.Forms.ButtonBase.Image%2A>-Eigenschaft auf eine Datei vom Typ. gif, JPEG oder BMP festgelegt ist.

  > [!NOTE]
  > Die <xref:System.Windows.Forms.FileDialog.FilterIndex%2A>-Eigenschaft der <xref:System.Windows.Forms.FileDialog> Klasse (die aufgrund der Vererbung Teil der <xref:System.Windows.Forms.SaveFileDialog>-Klasse ist) verwendet einen 1-basierten Index. Dies ist von Bedeutung, wenn Sie Code zum Speichern von Daten in einem bestimmten Format schreiben (z. B. Speichern einer Datei im Nur-Text-Format statt im Binärformat). Diese Eigenschaft ist im nachfolgenden Beispiel enthalten.

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
              safe_cast\<System::IO::FileStream*>(
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

  (Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  Weitere Informationen zum Schreiben von Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginWrite%2A> und <xref:System.IO.FileStream.Write%2A>.

  > [!NOTE]
  > Bestimmte Steuerelemente, wie z. b. das <xref:System.Windows.Forms.RichTextBox>-Steuerelement, können Dateien speichern.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog-Komponente](savefiledialog-component-windows-forms.md)
