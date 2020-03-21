---
title: Vollständige Druckaufträge
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182600"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="1145c-102">Gewusst wie: Fertigstellen von Druckaufträgen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1145c-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="1145c-103">Häufig bieten Textverarbeitungsaufträge und andere Anwendungen, die das Drucken beinhalten, die Möglichkeit, Benutzern eine Meldung anzuzeigen, dass ein Druckauftrag abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1145c-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="1145c-104">Sie können diese Funktionalität in Ihren <xref:System.Drawing.Printing.PrintDocument.EndPrint> Windows Forms <xref:System.Drawing.Printing.PrintDocument> bereitstellen, indem Sie das Ereignis der Komponente behandeln.</span><span class="sxs-lookup"><span data-stu-id="1145c-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="1145c-105">Das folgende Verfahren erfordert, dass Sie eine <xref:System.Drawing.Printing.PrintDocument> Windows-basierte Anwendung mit einer Komponente erstellt haben, die die Standardmethode zum Aktivieren des Druckens aus einer Windows-basierten Anwendung darstellt.</span><span class="sxs-lookup"><span data-stu-id="1145c-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="1145c-106">Weitere Informationen zum Drucken aus <xref:System.Drawing.Printing.PrintDocument> Windows Forms mithilfe der Komponente finden Sie unter [Gewusst wie: Erstellen von Standard-Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="1145c-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="1145c-107">So schließen Sie einen Druckauftrag ab</span><span class="sxs-lookup"><span data-stu-id="1145c-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="1145c-108">Legen <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> Sie die <xref:System.Drawing.Printing.PrintDocument> Eigenschaft der Komponente fest.</span><span class="sxs-lookup"><span data-stu-id="1145c-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="1145c-109">Erstellen Sie Code zur Behandlung des <xref:System.Drawing.Printing.PrintDocument.EndPrint> -Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="1145c-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="1145c-110">Im folgenden Codebeispiel wird ein Meldungsfeld angezeigt, das angibt, dass das Dokument den Druckvorgang beendet hat.</span><span class="sxs-lookup"><span data-stu-id="1145c-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="1145c-111">(Visual C- und Visual C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="1145c-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1145c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1145c-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="1145c-113">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1145c-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
