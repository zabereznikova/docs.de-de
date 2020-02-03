---
title: Anzeigen der Seitenansicht in Windows Forms-apps
titleSuffix: ''
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
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745573"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="2bf4c-102">Gewusst wie: Anzeigen der Seitenansicht in Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="2bf4c-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="2bf4c-103">Sie können das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verwenden, um Benutzern das Anzeigen eines Dokuments zu ermöglichen, das häufig vor dem Drucken angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="2bf4c-104">Zu diesem Zweck müssen Sie eine Instanz der <xref:System.Drawing.Printing.PrintDocument>-Klasse angeben. Dies ist das Dokument, das gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="2bf4c-105">Weitere Informationen zum Verwenden der Druckvorschau mit der <xref:System.Drawing.Printing.PrintDocument>-Komponente finden Sie unter Gewusst [wie: Drucken in Windows Forms mithilfe](../advanced/how-to-print-in-windows-forms-using-print-preview.md)der Seitenansicht.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bf4c-106">Um das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement zur Laufzeit zu verwenden, muss auf dem Computer entweder lokal oder über ein Netzwerk ein Drucker installiert sein, da dies dazu führt, dass die <xref:System.Windows.Forms.PrintPreviewDialog> Komponente bestimmt, wie ein Dokument gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="2bf4c-107">Das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verwendet die <xref:System.Drawing.Printing.PrinterSettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="2bf4c-108">Außerdem verwendet das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement die <xref:System.Drawing.Printing.PageSettings>-Klasse, ebenso wie die <xref:System.Windows.Forms.PrintPreviewDialog>-Komponente.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="2bf4c-109">Das in der <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>-Eigenschaft des <xref:System.Windows.Forms.PrintPreviewDialog>-Steuer Elements angegebene Druck Dokument bezieht sich auf Instanzen der Klassen <xref:System.Drawing.Printing.PrinterSettings> und <xref:System.Drawing.Printing.PageSettings>. Diese werden verwendet, um das Dokument im Vorschaufenster zu Rendering.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="2bf4c-110">So zeigen Sie Seiten mit dem PrintPreviewDialog-Steuerelement an</span><span class="sxs-lookup"><span data-stu-id="2bf4c-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="2bf4c-111">Verwenden Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> -Methode, um das Dialogfeld anzuzeigen, und geben Sie das zu verwendende <xref:System.Drawing.Printing.PrintDocument> an.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="2bf4c-112">Im folgenden Codebeispiel öffnet der <xref:System.Windows.Forms.Control.Click>-Ereignishandler des <xref:System.Windows.Forms.Button>-Steuer Elements eine Instanz des <xref:System.Windows.Forms.PrintPreviewDialog>-Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="2bf4c-113">Das Druck Dokument wird in der <xref:System.Windows.Forms.PrintDialog.Document%2A>-Eigenschaft angegeben.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="2bf4c-114">Im folgenden Beispiel wird kein Druck Dokument angegeben.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="2bf4c-115">Für das Beispiel ist es erforderlich, dass das Formular über ein <xref:System.Windows.Forms.Button>-Steuerelement, eine <xref:System.Drawing.Printing.PrintDocument> Komponente namens `myDocument`und ein <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement verfügt.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="2bf4c-116">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="2bf4c-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2bf4c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bf4c-117">See also</span></span>

- [<span data-ttu-id="2bf4c-118">PrintDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="2bf4c-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="2bf4c-119">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2bf4c-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="2bf4c-120">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bf4c-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="2bf4c-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2bf4c-121">Windows Forms</span></span>](../index.md)
