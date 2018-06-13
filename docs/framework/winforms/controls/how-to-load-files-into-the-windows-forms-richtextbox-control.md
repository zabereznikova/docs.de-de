---
title: 'Gewusst wie: Laden von Dateien in das RichTextBox-Steuerelement von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying files
- examples [Windows Forms], text boxes
- .rtf files [Windows Forms], opening in RichTextBox control
- RTF files [Windows Forms], opening in RichTextBox control
- text files [Windows Forms], displaying in RichTextBox control
- .rtf files [Windows Forms], displaying in RichTextBox control
- RichTextBox control [Windows Forms], opening files
- RTF files [Windows Forms], displaying in RichTextBox control
ms.assetid: c03451be-f285-4428-a71a-c41e002cc919
ms.openlocfilehash: 4d43536cab7806b8cf2de3d63b2d9f7f10024c71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534452"
---
# <a name="how-to-load-files-into-the-windows-forms-richtextbox-control"></a><span data-ttu-id="4f123-102">Gewusst wie: Laden von Dateien in das RichTextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f123-102">How to: Load Files into the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="4f123-103">Das <xref:System.Windows.Forms.RichTextBox> -Steuerelement von Windows Forms kann eine Nur-Text-, Unicode-Nur-Text- oder Rich-Text-Format-Datei (RTF) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4f123-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can display a plain-text, Unicode plain-text, or Rich-Text-Format (RTF) file.</span></span> <span data-ttu-id="4f123-104">Rufen Sie dazu die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> -Methode auf.</span><span class="sxs-lookup"><span data-stu-id="4f123-104">To do so, call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method.</span></span> <span data-ttu-id="4f123-105">Sie können die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> -Methode auch zum Laden von Daten aus einem Stream verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f123-105">You can also use the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method to load data from a stream.</span></span> <span data-ttu-id="4f123-106">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span><span class="sxs-lookup"><span data-stu-id="4f123-106">For more information, see <xref:System.Windows.Forms.RichTextBox.LoadFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-load-a-file-into-the-richtextbox-control"></a><span data-ttu-id="4f123-107">So laden Sie eine Datei in das RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4f123-107">To load a file into the RichTextBox control</span></span>  
  
1.  <span data-ttu-id="4f123-108">Bestimmen Sie den Pfad der Datei, die geöffnet werden soll, mithilfe der <xref:System.Windows.Forms.OpenFileDialog> -Komponente.</span><span class="sxs-lookup"><span data-stu-id="4f123-108">Determine the path of the file to be opened using the <xref:System.Windows.Forms.OpenFileDialog> component.</span></span> <span data-ttu-id="4f123-109">Eine Übersicht finden Sie unter [Übersicht über die OpenFileDialog-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4f123-109">For an overview, see [OpenFileDialog Component Overview](../../../../docs/framework/winforms/controls/openfiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="4f123-110">Rufen Sie die <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> -Methode des <xref:System.Windows.Forms.RichTextBox> -Steuerelements auf und geben Sie dabei die zu ladende Datei und optional einen Dateityp an.</span><span class="sxs-lookup"><span data-stu-id="4f123-110">Call the <xref:System.Windows.Forms.RichTextBox.LoadFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to load and optionally a file type.</span></span> <span data-ttu-id="4f123-111">Im folgenden Beispiel stammt die zu ladende Datei aus der <xref:System.Windows.Forms.OpenFileDialog> -Eigenschaft der <xref:System.Windows.Forms.FileDialog.FileName%2A> Komponente.</span><span class="sxs-lookup"><span data-stu-id="4f123-111">In the example below, the file to load is taken from the <xref:System.Windows.Forms.OpenFileDialog> component's <xref:System.Windows.Forms.FileDialog.FileName%2A> property.</span></span> <span data-ttu-id="4f123-112">Wenn Sie die Methode mit einem Dateinamen als einziges Argument aufrufen, wird RTF als Dateityp angenommen.</span><span class="sxs-lookup"><span data-stu-id="4f123-112">If you call the method with a file name as its only argument, the file type will be assumed to be RTF.</span></span> <span data-ttu-id="4f123-113">Rufen Sie zum Angeben eines anderen Dateityps die Methode mit dem Wert der <xref:System.Windows.Forms.RichTextBoxStreamType> -Enumeration als zweites Argument auf.</span><span class="sxs-lookup"><span data-stu-id="4f123-113">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="4f123-114">Im folgenden Beispiel wird die <xref:System.Windows.Forms.OpenFileDialog> -Komponente angezeigt, wenn auf eine Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="4f123-114">In the example below, the <xref:System.Windows.Forms.OpenFileDialog> component is shown when a button is clicked.</span></span> <span data-ttu-id="4f123-115">Die ausgewählte Datei wird anschließend geöffnet und im <xref:System.Windows.Forms.RichTextBox> -Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f123-115">The file selected is then opened and displayed in the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4f123-116">In diesem Beispiel wird angenommen, dass eine Form eine Schaltfläche`btnOpenFile`enthält.</span><span class="sxs-lookup"><span data-stu-id="4f123-116">This example assumes a form has a button,`btnOpenFile`.</span></span>  
  
    ```vb  
    Private Sub btnOpenFile_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles btnOpenFile.Click  
         If OpenFileDialog1.ShowDialog() = DialogResult.OK Then  
           RichTextBox1.LoadFile(OpenFileDialog1.FileName, _  
              RichTextBoxStreamType.RichText)  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    private void btnOpenFile_Click(object sender, System.EventArgs e)  
    {  
       if(openFileDialog1.ShowDialog() == DialogResult.OK)  
       {  
         richTextBox1.LoadFile(openFileDialog1.FileName, RichTextBoxStreamType.RichText);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void btnOpenFile_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          if(openFileDialog1->ShowDialog() == DialogResult::OK)  
          {  
             richTextBox1->LoadFile(openFileDialog1->FileName,  
                RichTextBoxStreamType::RichText);  
          }  
       }  
    ```  
  
     <span data-ttu-id="4f123-117">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4f123-117">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.btnOpenFile.Click += new System.EventHandler(this. btnOpenFile_Click);  
    ```  
  
    ```cpp  
    this->btnOpenFile->Click += gcnew   
       System::EventHandler(this, &Form1::btnOpenFile_Click);  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4f123-118">Die Assembly benötigt zum Ausführen dieses Prozesses möglicherweise eine von der <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType>-Klasse gewährte Berechtigungsebene.</span><span class="sxs-lookup"><span data-stu-id="4f123-118">To run this process, your assembly may require a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="4f123-119">Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang aufgrund fehlender Berechtigungen eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="4f123-119">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="4f123-120">Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../../docs/framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="4f123-120">For more information, see [Code Access Security Basics](../../../../docs/framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f123-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f123-121">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox.LoadFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="4f123-122">RichTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="4f123-122">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="4f123-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="4f123-123">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
