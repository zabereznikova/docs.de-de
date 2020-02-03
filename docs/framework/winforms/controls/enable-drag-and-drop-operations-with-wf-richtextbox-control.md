---
title: Aktivieren von Drag & Drop-Vorgängen mit dem RichTextBox-Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 3c17560dee012912aea2938654f1dc4dc56e0725
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745821"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="2b520-102">Gewusst wie: Aktivieren von Drag & Drop-Operationen mithilfe des RichTextBox-Steuerelements von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b520-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="2b520-103">Drag &amp; Drop-Vorgänge mit dem Windows Forms-Steuerelement <xref:System.Windows.Forms.RichTextBox> erfolgen durch Verarbeitung der Ereignisse <xref:System.Windows.Forms.RichTextBox.DragEnter> und <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="2b520-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="2b520-104">Durch das <xref:System.Windows.Forms.RichTextBox> -Steuerelement werden Drag &amp; Drop-Vorgänge daher sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="2b520-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="2b520-105">Aktivieren von Drag-Vorgängen in einem RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2b520-105">To enable drag operations in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="2b520-106">Legen Sie die <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> -Eigenschaft des <xref:System.Windows.Forms.RichTextBox> -Steuerelements auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="2b520-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2. <span data-ttu-id="2b520-107">Erstellen Sie Code für den Ereignishandler des <xref:System.Windows.Forms.RichTextBox.DragEnter> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="2b520-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="2b520-108">Verwenden Sie eine `if` -Anweisung, um sicherzustellen, dass die gezogenen Daten einem passenden Typ angehören (in diesem Fall Text).</span><span class="sxs-lookup"><span data-stu-id="2b520-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="2b520-109">Die <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> -Eigenschaft kann auf jeden beliebigen Wert der <xref:System.Windows.Forms.DragDropEffects> -Enumeration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2b520-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="2b520-110">(Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2b520-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. <span data-ttu-id="2b520-111">Erstellen Sie Code zur Behandlung des <xref:System.Windows.Forms.RichTextBox.DragDrop> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="2b520-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="2b520-112">Verwenden Sie die <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> -Methode, um die gezogenen Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2b520-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="2b520-113">Im Beispiel unten legt der Code die <xref:System.Windows.Forms.RichTextBox.Text%2A> -Eigenschaft des <xref:System.Windows.Forms.RichTextBox> -Steuerelements auf die gezogenen Daten fest.</span><span class="sxs-lookup"><span data-stu-id="2b520-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="2b520-114">Wenn sich bereits Text im <xref:System.Windows.Forms.RichTextBox> -Steuerelement befindet, wird der gezogene Text an der Einfügemarke eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2b520-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="2b520-115">(Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2b520-115">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="2b520-116">Testen der Drag & Drop-Funktionalität in der Anwendung</span><span class="sxs-lookup"><span data-stu-id="2b520-116">To test the drag-and-drop functionality in your application</span></span>  
  
1. <span data-ttu-id="2b520-117">Speichern und erstellen Sie Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2b520-117">Save and build your application.</span></span> <span data-ttu-id="2b520-118">Führen Sie WordPad aus, während die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b520-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="2b520-119">WordPad ist ein Text-Editor von Windows, der Drag & Drop-Vorgänge ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2b520-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="2b520-120">Sie können auf WordPad zugreifen, indem Sie auf die Schaltfläche **Start** klicken, den Befehl **Ausführen**auswählen und anschließend `WordPad` in das Textfeld des Dialogfelds **Ausführen** eingeben. Abschließend klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b520-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="2b520-121">Wenn WordPad geöffnet ist, geben Sie eine Textzeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="2b520-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="2b520-122">Markieren Sie den Text mit der Maus, und ziehen Sie den markierten Text dann auf das <xref:System.Windows.Forms.RichTextBox> -Steuerelement in der Windows-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2b520-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="2b520-123">Beachten Sie, dass wenn sich die Maus über dem <xref:System.Windows.Forms.RichTextBox> -Steuerelement befindet (und damit folglich das <xref:System.Windows.Forms.RichTextBox.DragEnter> -Ereignis ausgelöst wird), sich der Mauszeiger ändert und Sie den ausgewählten Text auf dem <xref:System.Windows.Forms.RichTextBox> -Steuerelement ablegen können.</span><span class="sxs-lookup"><span data-stu-id="2b520-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="2b520-124">Wenn Sie die Maustaste loslassen, wird der ausgewählte Text abgelegt (das heißt, das <xref:System.Windows.Forms.RichTextBox.DragDrop> -Ereignis wird ausgelöst) und in das <xref:System.Windows.Forms.RichTextBox> -Steuerelement eingefügt.</span><span class="sxs-lookup"><span data-stu-id="2b520-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b520-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b520-125">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="2b520-126">Gewusst wie: Ausführen von Drag & Drop-Operationen zwischen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2b520-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [<span data-ttu-id="2b520-127">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2b520-127">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="2b520-128">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b520-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
