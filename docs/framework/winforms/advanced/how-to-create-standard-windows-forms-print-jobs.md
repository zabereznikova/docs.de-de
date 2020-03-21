---
title: Erstellen von Standarddruckaufträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182566"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="9098c-102">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9098c-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="9098c-103">Die Grundlage für das Drucken <xref:System.Drawing.Printing.PrintDocument> in Windows Forms <xref:System.Drawing.Printing.PrintDocument.PrintPage> ist die Komponente – genauer gesagt das Ereignis.</span><span class="sxs-lookup"><span data-stu-id="9098c-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="9098c-104">Durch Das Schreiben <xref:System.Drawing.Printing.PrintDocument.PrintPage> von Code für das Ereignis können Sie angeben, was gedruckt und gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9098c-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="9098c-105">So erstellen Sie einen Druckauftrag</span><span class="sxs-lookup"><span data-stu-id="9098c-105">To create a print job</span></span>  
  
1. <span data-ttu-id="9098c-106">Fügen <xref:System.Drawing.Printing.PrintDocument> Sie dem Formular eine Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="9098c-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="9098c-107">Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="9098c-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="9098c-108">Sie müssen Ihre eigene Drucklogik codieren.</span><span class="sxs-lookup"><span data-stu-id="9098c-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="9098c-109">Darüber hinaus müssen Sie das zu druckende Material angeben.</span><span class="sxs-lookup"><span data-stu-id="9098c-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="9098c-110">Im folgenden Codebeispiel wird im <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler eine Beispielgrafik in Form eines roten Rechtecks erstellt, die als zu druckendes Material fungiert.</span><span class="sxs-lookup"><span data-stu-id="9098c-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="9098c-111">(Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9098c-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="9098c-112">Sie können auch Code für <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> die und Ereignisse schreiben, z. B. eine ganze Zahl, die die Gesamtzahl der zu druckenden Seiten darstellt, die beim Drucken jeder Seite dekrementiert wird.</span><span class="sxs-lookup"><span data-stu-id="9098c-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9098c-113">Sie können <xref:System.Windows.Forms.PrintDialog> dem Formular eine Komponente hinzufügen, um ihren Benutzern eine saubere und effiziente Benutzeroberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9098c-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="9098c-114">Durch <xref:System.Windows.Forms.PrintDialog.Document%2A> Festlegen der <xref:System.Windows.Forms.PrintDialog> Eigenschaft der Komponente können Sie Eigenschaften festlegen, die sich auf das Druckdokument beziehen, mit dem Sie im Formular arbeiten.</span><span class="sxs-lookup"><span data-stu-id="9098c-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="9098c-115">Weitere Informationen zur <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="9098c-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="9098c-116">Weitere Informationen zu den Besonderheiten von Windows Forms-Druckaufträgen, z. B. zum programmgesteuerten Erstellen eines Druckauftrags, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="9098c-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9098c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9098c-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="9098c-118">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9098c-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
