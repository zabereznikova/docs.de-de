---
title: 'Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms'
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
ms.openlocfilehash: 18078c5e6bf518487707a8dc5639b3d6aa8a5783
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723341"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="ce9b3-102">Vorgehensweise: Erstellen von Druckaufträgen in Standard-Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce9b3-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="ce9b3-103">Die Grundlage für das Drucken in Windows Forms ist die <xref:System.Drawing.Printing.PrintDocument> Komponente – genauer gesagt die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="ce9b3-104">Durch das Schreiben von Code zum Behandeln der <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis können Sie angeben, was gedruckt und wie es gedruckt.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="ce9b3-105">Um einen Druckauftrag zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="ce9b3-106">Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="ce9b3-107">Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="ce9b3-108">Sie müssen Ihre eigene Logik zum Drucken zu codieren.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="ce9b3-109">Darüber hinaus müssen Sie sich an das Material, das gedruckt werden.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="ce9b3-110">Im folgenden Codebeispiel wird eine Beispielgrafik in der Form eines roten Rechtecks in erstellt die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler als Material zu druckenden fungieren.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="ce9b3-111">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="ce9b3-112">Sie sollten auch zum Schreiben von Code für die <xref:System.Drawing.Printing.PrintDocument.BeginPrint> und <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignisse, die durch eine ganze Zahl, der die Gesamtzahl der Seiten darstellt, drucken, die abgezogen wird bei jeder gedruckten Seite.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce9b3-113">Sie können Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> Ihrem Formular eine saubere und effizienten Benutzeroberfläche (UI) für Ihre Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="ce9b3-114">Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft der <xref:System.Windows.Forms.PrintDialog> Komponente ermöglicht, die Sie zum Festlegen von Eigenschaften, die im Zusammenhang mit dem Drucken dokumentieren Sie arbeiten mit in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="ce9b3-115">Weitere Informationen zu den <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ce9b3-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="ce9b3-116">Weitere Informationen zu den Besonderheiten von Windows Forms Druckaufträge, wie Sie einen Druckauftrag programmgesteuert erstellen finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="ce9b3-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9b3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce9b3-117">See also</span></span>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="ce9b3-118">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce9b3-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
