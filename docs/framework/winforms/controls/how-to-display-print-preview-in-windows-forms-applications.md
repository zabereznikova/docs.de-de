---
title: 'Vorgehensweise: Anzeigen der Seitenansicht in Windows Forms-Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154361"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="de99b-102">Vorgehensweise: Anzeigen der Seitenansicht in Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="de99b-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="de99b-103">Sie können die <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement, damit Benutzer ein Dokument anzuzeigen, noch bevor es gedruckt werden.</span><span class="sxs-lookup"><span data-stu-id="de99b-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="de99b-104">Zu diesem Zweck müssen Sie eine Instanz von angeben der <xref:System.Drawing.Printing.PrintDocument> Klasse; Dies ist das Dokument gedruckt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="de99b-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="de99b-105">Weitere Informationen zur Verwendung der Seitenansicht, mit der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: In Windows Forms unter Verwendung der Seitenansicht drucken](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span><span class="sxs-lookup"><span data-stu-id="de99b-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de99b-106">Verwenden der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement zur Laufzeit benötigen Benutzer einen Drucker auf dem Computer installiert werden, entweder lokal oder über ein Netzwerk, da es sich teilweise handelt wie die <xref:System.Windows.Forms.PrintPreviewDialog> Anwendungskomponente bestimmt, wie ein Dokument gedruckt aussehen wird.</span><span class="sxs-lookup"><span data-stu-id="de99b-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="de99b-107">Die <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement verwendet die <xref:System.Drawing.Printing.PrinterSettings> Klasse.</span><span class="sxs-lookup"><span data-stu-id="de99b-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="de99b-108">Darüber hinaus die <xref:System.Windows.Forms.PrintPreviewDialog> -Steuerelement verwendet die <xref:System.Drawing.Printing.PageSettings> -Klasse, wie die <xref:System.Windows.Forms.PrintPreviewDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="de99b-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="de99b-109">Des zu druckenden Dokuments angegeben wird, der <xref:System.Windows.Forms.PrintPreviewDialog> des Steuerelements <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> Eigenschaft bezieht sich auf Instanzen von sowohl die <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings> Klassen und diese werden verwendet, um das Dokument in einem Vorschaufenster zu rendern.</span><span class="sxs-lookup"><span data-stu-id="de99b-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="de99b-110">Zum Anzeigen von Seiten, die über das PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="de99b-110">To view pages using the PrintPreviewDialog control</span></span>  
  
-   <span data-ttu-id="de99b-111">Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.</span><span class="sxs-lookup"><span data-stu-id="de99b-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="de99b-112">Das folgende Codebeispiel zeigt die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignishandler öffnet eine Instanz von der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de99b-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="de99b-113">Der zu druckenden Dokuments wird angegeben, der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="de99b-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="de99b-114">Im folgenden Beispiel wird keine zu druckenden Dokuments angegeben.</span><span class="sxs-lookup"><span data-stu-id="de99b-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="de99b-115">Das Beispiel erfordert, dass das Formular enthält ein <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Drawing.Printing.PrintDocument> Komponente, die mit dem Namen `myDocument`, und ein <xref:System.Windows.Forms.PrintPreviewDialog> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="de99b-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="de99b-116">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="de99b-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="de99b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de99b-117">See also</span></span>

- [<span data-ttu-id="de99b-118">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="de99b-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="de99b-119">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="de99b-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="de99b-120">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de99b-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="de99b-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="de99b-121">Windows Forms</span></span>](../index.md)
