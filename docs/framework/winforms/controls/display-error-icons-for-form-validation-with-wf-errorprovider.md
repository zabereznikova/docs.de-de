---
title: 'Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms'
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
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 08e0ac04f2d34f7b6e1cc85d77f863c8ef3f7961
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="c2fed-102">Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2fed-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="c2fed-103">Sie können eine Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente ein Fehlersymbol angezeigt wird, wenn der Benutzer ungültige Daten eingibt.</span><span class="sxs-lookup"><span data-stu-id="c2fed-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="c2fed-104">Sie müssen mindestens zwei Steuerelemente im Formular aus, um zwischen ihnen Registerkarte und somit Aufrufen des Validierungscodes verfügen.</span><span class="sxs-lookup"><span data-stu-id="c2fed-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="c2fed-105">Um ein Fehlersymbol angezeigt wird, wenn der Wert eines Steuerelements ungültig ist</span><span class="sxs-lookup"><span data-stu-id="c2fed-105">To display an error icon when a control's value is invalid</span></span>  
  
1.  <span data-ttu-id="c2fed-106">Hinzufügen von zwei Steuerelementen – z. B. Textfelder – zu einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="c2fed-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2.  <span data-ttu-id="c2fed-107">Hinzufügen einer <xref:System.Windows.Forms.ErrorProvider> -Komponente zum Formular.</span><span class="sxs-lookup"><span data-stu-id="c2fed-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3.  <span data-ttu-id="c2fed-108">Wählen Sie das erste Steuerelement, und fügen Sie Code, dessen <xref:System.Windows.Forms.Control.Validating> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c2fed-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="c2fed-109">Damit kann für diesen Code ordnungsgemäß ausgeführt muss die Prozedur an das Ereignis bestehen.</span><span class="sxs-lookup"><span data-stu-id="c2fed-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="c2fed-110">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Ereignishandlern an Zeit für Windows Forms führen](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c2fed-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="c2fed-111">Der folgende Code überprüft die Gültigkeit der Daten, die der Benutzer eingegeben hat. Wenn die Daten ungültig sind, werden die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c2fed-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="c2fed-112">Das erste Argument der <xref:System.Windows.Forms.ErrorProvider.SetError%2A> Methode gibt an, welches Steuerelement neben das Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2fed-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="c2fed-113">Das zweite Argument ist der anzuzeigende Fehlertext.</span><span class="sxs-lookup"><span data-stu-id="c2fed-113">The second argument is the error text to display.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     <span data-ttu-id="c2fed-114">(Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie den folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="c2fed-114">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  <span data-ttu-id="c2fed-115">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="c2fed-115">Run the project.</span></span> <span data-ttu-id="c2fed-116">Geben Sie in das erste Steuerelement, und klicken Sie dann Tab, um die zweite (in diesem Beispiel nicht numerisch) ungültige Daten.</span><span class="sxs-lookup"><span data-stu-id="c2fed-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="c2fed-117">Wenn das Symbol "Fehler" angezeigt wird, stellen Sie den Mauszeiger an den Fehlertext finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="c2fed-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fed-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2fed-118">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [<span data-ttu-id="c2fed-119">Übersicht über die ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="c2fed-119">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="c2fed-120">Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c2fed-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
