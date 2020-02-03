---
title: Standard Druckaufträge erstellen
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741518"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="bb439-102">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb439-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="bb439-103">Die Grundlage für das Drucken in Windows Forms ist die <xref:System.Drawing.Printing.PrintDocument> Komponente – genauer gesagt das <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bb439-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="bb439-104">Durch das Schreiben von Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignisses können Sie angeben, was gedruckt werden soll und wie es gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb439-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="bb439-105">So erstellen Sie einen Druckauftrag</span><span class="sxs-lookup"><span data-stu-id="bb439-105">To create a print job</span></span>  
  
1. <span data-ttu-id="bb439-106">Fügen Sie dem Formular eine <xref:System.Drawing.Printing.PrintDocument> Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb439-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="bb439-107">Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="bb439-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="bb439-108">Sie müssen ihre eigene Druck Logik programmieren.</span><span class="sxs-lookup"><span data-stu-id="bb439-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="bb439-109">Außerdem müssen Sie das Material angeben, das gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bb439-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="bb439-110">Im folgenden Codebeispiel wird eine Beispiel Grafik in der Form eines roten Rechtecks im <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignishandler erstellt, der als Material zum Drucken fungiert.</span><span class="sxs-lookup"><span data-stu-id="bb439-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="bb439-111">(Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="bb439-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="bb439-112">Möglicherweise möchten Sie auch Code für die <xref:System.Drawing.Printing.PrintDocument.BeginPrint>-und <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignisse schreiben, z. b. eine ganze Zahl, die die Gesamtzahl der zu druckenden Seiten darstellt, die bei jeder Seite gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="bb439-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="bb439-113">Sie können dem Formular eine <xref:System.Windows.Forms.PrintDialog> Komponente hinzufügen, um Ihren Benutzern eine saubere und effiziente Benutzeroberfläche bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb439-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="bb439-114">Wenn Sie die <xref:System.Windows.Forms.PrintDialog.Document%2A>-Eigenschaft der <xref:System.Windows.Forms.PrintDialog> Komponente festlegen, können Sie Eigenschaften festlegen, die sich auf das Druck Dokument beziehen, mit dem Sie in Ihrem Formular arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bb439-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="bb439-115">Weitere Informationen zur <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bb439-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="bb439-116">Weitere Informationen zu den Besonderheiten Windows Forms Druckaufträgen, einschließlich der programmgesteuerten Erstellung eines Druckauftrags, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="bb439-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb439-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb439-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="bb439-118">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb439-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
