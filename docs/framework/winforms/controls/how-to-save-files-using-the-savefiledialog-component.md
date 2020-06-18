---
title: 'Vorgehensweise: Speichern von Dateien mit der SaveFileDialog-Komponente'
description: Erfahren Sie, wie Sie die SaveFileDialog-Komponente verwenden, um das Dateisystem zu durchsuchen und die zu speichernden Dateien auszuwählen.
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
ms.openlocfilehash: cd773c3d4aa2b907eb09dd87c3fdbe138bf533bb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904402"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="ceb42-103">Vorgehensweise: Speichern von Dateien mit der SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="ceb42-103">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="ceb42-104">Die <xref:System.Windows.Forms.SaveFileDialog> -Komponente ermöglicht es Benutzern, das Dateisystem zu durchsuchen und die zu speichernden Dateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ceb42-104">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="ceb42-105">Das Dialogfeld gibt den Pfad und den Namen der ausgewählten Datei zurück.</span><span class="sxs-lookup"><span data-stu-id="ceb42-105">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="ceb42-106">Sie müssen jedoch den Code schreiben, mit dem die Dateien letztendlich auf den Datenträger geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ceb42-106">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="ceb42-107">So speichern Sie eine Datei mit der SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="ceb42-107">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="ceb42-108">Zeigen Sie das Dialogfeld **Datei öffnen** an, und rufen Sie eine Methode zum Öffnen der vom Benutzer ausgewählten Datei auf.</span><span class="sxs-lookup"><span data-stu-id="ceb42-108">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="ceb42-109">Verwenden <xref:System.Windows.Forms.SaveFileDialog> Sie die-Methode der-Komponente <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> , um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ceb42-109">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="ceb42-110">Diese Methode gibt Ihnen ein- <xref:System.IO.Stream> Objekt, in das geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ceb42-110">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="ceb42-111">Im folgenden Beispiel wird die <xref:System.Windows.Forms.DialogResult> -Eigenschaft verwendet, um den Namen der Datei zu erhalten, und die- <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> Methode, um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ceb42-111">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="ceb42-112">Die- <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode gibt Ihnen einen Stream, in den die Datei geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ceb42-112">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="ceb42-113">Im folgenden Beispiel ist ein <xref:System.Windows.Forms.Button> Steuerelement mit einem zugeordneten Bild vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ceb42-113">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="ceb42-114">Wenn Sie auf die Schaltfläche klicken, <xref:System.Windows.Forms.SaveFileDialog> wird eine Komponente mit einem Filter instanziiert, der Dateien vom Typ. gif,. JPEG und BMP zulässt.</span><span class="sxs-lookup"><span data-stu-id="ceb42-114">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="ceb42-115">Wenn eine Datei diesen Typs im Dialogfeld „Datei speichern“ ausgewählt wird, wird das Bild der Schaltfläche gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ceb42-115">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ceb42-116">Um die Eigenschaft zu erhalten oder festzulegen <xref:System.Windows.Forms.FileDialog.FileName%2A> , erfordert die Assembly eine von der-Klasse gewährte Berechtigungsebene <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ceb42-116">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="ceb42-117">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="ceb42-117">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="ceb42-118">Weitere Informationen finden Sie unter [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="ceb42-118">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="ceb42-119">Im Beispiel wird davon ausgegangen, dass das Formular über ein-Steuerelement verfügt, <xref:System.Windows.Forms.Button> dessen- <xref:System.Windows.Forms.ButtonBase.Image%2A> Eigenschaft auf eine Datei vom Typ. gif,. JPEG oder. BMP festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ceb42-119">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ceb42-120">Die <xref:System.Windows.Forms.FileDialog> -Eigenschaft der-Klasse <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> (die aufgrund der Vererbung Teil der- <xref:System.Windows.Forms.SaveFileDialog> Klasse ist) verwendet einen 1-basierten Index.</span><span class="sxs-lookup"><span data-stu-id="ceb42-120">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="ceb42-121">Dies ist von Bedeutung, wenn Sie Code zum Speichern von Daten in einem bestimmten Format schreiben (z. B. Speichern einer Datei im Nur-Text-Format statt im Binärformat).</span><span class="sxs-lookup"><span data-stu-id="ceb42-121">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="ceb42-122">Diese Eigenschaft ist im nachfolgenden Beispiel enthalten.</span><span class="sxs-lookup"><span data-stu-id="ceb42-122">This property is featured in the example below.</span></span>

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

  <span data-ttu-id="ceb42-123">(Visual c# und Visual C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ceb42-123">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="ceb42-124">Weitere Informationen zum Schreiben von Dateistreams finden Sie unter <xref:System.IO.FileStream.BeginWrite%2A> und <xref:System.IO.FileStream.Write%2A> .</span><span class="sxs-lookup"><span data-stu-id="ceb42-124">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ceb42-125">Bestimmte Steuerelemente, z. b. das- <xref:System.Windows.Forms.RichTextBox> Steuerelement, können Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="ceb42-125">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span>

## <a name="see-also"></a><span data-ttu-id="ceb42-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ceb42-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="ceb42-127">SaveFileDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="ceb42-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
