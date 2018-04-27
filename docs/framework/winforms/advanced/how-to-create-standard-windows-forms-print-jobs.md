---
title: 'Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0090748ebdc52217176021c877949e62687e8a55
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="6b268-102">Gewusst wie: Erstellen von standardmäßigen Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b268-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="6b268-103">Die Grundlage für das Drucken in Windows Forms ist die <xref:System.Drawing.Printing.PrintDocument> Komponente – genauer gesagt, die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6b268-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="6b268-104">Durch das Schreiben von Code zum Behandeln der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignis können Sie angeben, was gedruckt und wie es gedruckt.</span><span class="sxs-lookup"><span data-stu-id="6b268-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="6b268-105">So erstellen einen Druckauftrag</span><span class="sxs-lookup"><span data-stu-id="6b268-105">To create a print job</span></span>  
  
1.  <span data-ttu-id="6b268-106">Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> -Komponente in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="6b268-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="6b268-107">Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="6b268-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="6b268-108">Sie müssen Ihre eigene Logik zum Drucken zu codieren.</span><span class="sxs-lookup"><span data-stu-id="6b268-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="6b268-109">Darüber hinaus müssen Sie das Material zu druckende angegeben.</span><span class="sxs-lookup"><span data-stu-id="6b268-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="6b268-110">Im folgenden Codebeispiel wird eine Beispielgrafik in der Form eines roten Rechtecks erstellt, der <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignishandler fungieren als Material, das gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6b268-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
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
  
     <span data-ttu-id="6b268-111">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="6b268-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
     <span data-ttu-id="6b268-112">Sie sollten auch zum Schreiben von Code für die <xref:System.Drawing.Printing.PrintDocument.BeginPrint> und <xref:System.Drawing.Printing.PrintDocument.EndPrint> Ereignisse, die eine ganze Zahl, die die Gesamtanzahl der Seiten darstellt, drucken, das jede Seite gedruckt wird wieder um eins erniedrigt ist.</span><span class="sxs-lookup"><span data-stu-id="6b268-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6b268-113">Sie können Hinzufügen einer <xref:System.Windows.Forms.PrintDialog> -Komponente zum Formular an eine übersichtliche und effiziente Benutzeroberfläche (UI) für Ihre Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="6b268-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="6b268-114">Festlegen der <xref:System.Windows.Forms.PrintDialog.Document%2A> Eigenschaft von der <xref:System.Windows.Forms.PrintDialog> Komponente ermöglicht, die Sie zum Festlegen von Eigenschaften, die im Zusammenhang mit dem Druckserver dokumentieren Sie arbeiten mit auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="6b268-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="6b268-115">Weitere Informationen zu den <xref:System.Windows.Forms.PrintDialog> Komponente finden Sie unter [PrintDialog-Komponente](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6b268-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="6b268-116">Weitere Informationen zu den Besonderheiten von Windows Forms-Druckaufträge, einschließlich der Erstellung ein Druckauftrags programmgesteuert erstellen, finden Sie unter <xref:System.Drawing.Printing.PrintPageEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="6b268-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b268-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b268-117">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="6b268-118">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6b268-118">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
