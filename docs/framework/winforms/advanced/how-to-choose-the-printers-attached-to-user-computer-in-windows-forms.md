---
title: 'Vorgehensweise: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: e81ef8b563afff6dd57a9fbb7674d17c0eb80916
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053074"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="453aa-102">Vorgehensweise: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="453aa-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="453aa-103">Häufig möchten Benutzer einen anderen Drucker als den Standarddrucker zum Drucken auswählen.</span><span class="sxs-lookup"><span data-stu-id="453aa-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="453aa-104">Sie können es Benutzern ermöglichen, mithilfe der <xref:System.Windows.Forms.PrintDialog> -Komponente einen Drucker unter den Druckern auszuwählen, die derzeit installiert sind.</span><span class="sxs-lookup"><span data-stu-id="453aa-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="453aa-105">Über die Komponente <xref:System.Windows.Forms.PrintDialog> wird das <xref:System.Windows.Forms.DialogResult> der Komponente <xref:System.Windows.Forms.PrintDialog> aufgezeichnet und für die Auswahl des Druckers verwendet.</span><span class="sxs-lookup"><span data-stu-id="453aa-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="453aa-106">In der folgenden Prozedur wird eine Textdatei ausgewählt, die auf dem Standarddrucker gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="453aa-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="453aa-107">Die <xref:System.Windows.Forms.PrintDialog> -Klasse wird dann instanziiert.</span><span class="sxs-lookup"><span data-stu-id="453aa-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="453aa-108">So wählen Sie einen Drucker aus und drucken eine Datei</span><span class="sxs-lookup"><span data-stu-id="453aa-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="453aa-109">Wählen Sie den Drucker, verwendet werden soll, mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="453aa-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="453aa-110">Im folgenden Codebeispiel werden zwei Ereignisse behandelt.</span><span class="sxs-lookup"><span data-stu-id="453aa-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="453aa-111">Im ersten eine <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> Ereignis die <xref:System.Windows.Forms.PrintDialog> Klasse instanziiert wird, und der vom Benutzer ausgewählte Drucker wird erfasst, der <xref:System.Windows.Forms.DialogResult> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="453aa-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="453aa-112">Im zweiten Ereignis das <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis die <xref:System.Drawing.Printing.PrintDocument> Komponente, wird ein Beispieldokument mit dem angegebenen Drucker gedruckt.</span><span class="sxs-lookup"><span data-stu-id="453aa-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="453aa-113">(Visual C# und visuelle C++) Platzieren Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="453aa-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="453aa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="453aa-114">See also</span></span>

- [<span data-ttu-id="453aa-115">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="453aa-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
