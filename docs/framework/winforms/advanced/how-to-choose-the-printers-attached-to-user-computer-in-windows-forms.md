---
title: 'Vorgehensweise: Auswählen der Drucker, die an den Computer eines Benutzers angeschlossen sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
ms.openlocfilehash: 7fc2427468540ac0a1480f6140cbb34c3a0f1ab3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746512"
---
# <a name="how-to-choose-the-printers-attached-to-a-users-computer-in-windows-forms"></a><span data-ttu-id="860d5-102">Gewusst wie: Auswählen der einem Benutzercomputer zugewiesenen Drucker in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="860d5-102">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>
<span data-ttu-id="860d5-103">Häufig möchten Benutzer einen anderen Drucker als den Standarddrucker zum Drucken auswählen.</span><span class="sxs-lookup"><span data-stu-id="860d5-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="860d5-104">Sie können es Benutzern ermöglichen, mithilfe der <xref:System.Windows.Forms.PrintDialog> -Komponente einen Drucker unter den Druckern auszuwählen, die derzeit installiert sind.</span><span class="sxs-lookup"><span data-stu-id="860d5-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="860d5-105">Über die Komponente <xref:System.Windows.Forms.PrintDialog> wird das <xref:System.Windows.Forms.DialogResult> der Komponente <xref:System.Windows.Forms.PrintDialog> aufgezeichnet und für die Auswahl des Druckers verwendet.</span><span class="sxs-lookup"><span data-stu-id="860d5-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="860d5-106">In der folgenden Prozedur wird eine Textdatei ausgewählt, die auf dem Standarddrucker gedruckt werden soll.</span><span class="sxs-lookup"><span data-stu-id="860d5-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="860d5-107">Die <xref:System.Windows.Forms.PrintDialog> -Klasse wird dann instanziiert.</span><span class="sxs-lookup"><span data-stu-id="860d5-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="860d5-108">So wählen Sie einen Drucker aus und drucken eine Datei</span><span class="sxs-lookup"><span data-stu-id="860d5-108">To choose a printer and then print a file</span></span>  
  
1. <span data-ttu-id="860d5-109">Wählen Sie den Drucker aus, der mithilfe der <xref:System.Windows.Forms.PrintDialog> Komponente verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="860d5-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="860d5-110">Im folgenden Codebeispiel werden zwei Ereignisse behandelt.</span><span class="sxs-lookup"><span data-stu-id="860d5-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="860d5-111">Im ersten, dem <xref:System.Windows.Forms.Control.Click>-Ereignis eines <xref:System.Windows.Forms.Button>-Steuer Elements, wird die <xref:System.Windows.Forms.PrintDialog>-Klasse instanziiert, und der vom Benutzer ausgewählte Drucker wird in der <xref:System.Windows.Forms.DialogResult>-Eigenschaft aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="860d5-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="860d5-112">Im zweiten Ereignis, dem <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignis der <xref:System.Drawing.Printing.PrintDocument> Komponente, wird ein Beispiel Dokument an den angegebenen Drucker ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="860d5-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
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
  
     <span data-ttu-id="860d5-113">(Visualisierung C# und Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="860d5-113">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="860d5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="860d5-114">See also</span></span>

- [<span data-ttu-id="860d5-115">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="860d5-115">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
