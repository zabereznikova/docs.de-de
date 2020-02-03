---
title: Anzeigen von Fehler Symbolen für die Formular Validierung mit der ErrorProvider-Komponente
ms.date: 03/30/2017
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
ms.openlocfilehash: a1e346e332db489351f59c9a0c03ae731baf3dc3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745909"
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="5db0b-102">Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5db0b-102">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="5db0b-103">Sie können eine Windows Forms <xref:System.Windows.Forms.ErrorProvider> Komponente verwenden, um ein Fehler Symbol anzuzeigen, wenn der Benutzer ungültige Daten eingibt.</span><span class="sxs-lookup"><span data-stu-id="5db0b-103">You can use a Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to display an error icon when the user enters invalid data.</span></span> <span data-ttu-id="5db0b-104">Sie müssen über mindestens zwei Steuerelemente auf dem Formular verfügen, um zwischen Ihnen zu Tabstopps und somit den Validierungscode aufrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="5db0b-104">You must have at least two controls on the form in order to tab between them and thereby invoke the validation code.</span></span>  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a><span data-ttu-id="5db0b-105">So zeigen Sie ein Fehler Symbol an, wenn der Wert eines Steuer Elements ungültig ist</span><span class="sxs-lookup"><span data-stu-id="5db0b-105">To display an error icon when a control's value is invalid</span></span>  
  
1. <span data-ttu-id="5db0b-106">Fügen Sie zwei Steuerelemente – z. b. Textfelder – zu einem Windows Form hinzu.</span><span class="sxs-lookup"><span data-stu-id="5db0b-106">Add two controls — for example, text boxes — to a Windows Form.</span></span>  
  
2. <span data-ttu-id="5db0b-107">Fügen Sie dem Formular eine <xref:System.Windows.Forms.ErrorProvider> Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="5db0b-107">Add an <xref:System.Windows.Forms.ErrorProvider> component to the form.</span></span>  
  
3. <span data-ttu-id="5db0b-108">Wählen Sie das erste Steuerelement aus, und fügen Sie seinem <xref:System.Windows.Forms.Control.Validating>-Ereignishandler Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="5db0b-108">Select the first control and add code to its <xref:System.Windows.Forms.Control.Validating> event handler.</span></span> <span data-ttu-id="5db0b-109">Damit dieser Code ordnungsgemäß ausgeführt werden kann, muss die Prozedur mit dem Ereignis verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="5db0b-109">In order for this code to run properly, the procedure must be connected to the event.</span></span> <span data-ttu-id="5db0b-110">Weitere Informationen finden Sie unter Gewusst [wie: Erstellen von Ereignis Handlern zur Laufzeit für Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5db0b-110">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="5db0b-111">Der folgende Code testet die Gültigkeit der Daten, die der Benutzer eingegeben hat. Wenn die Daten ungültig sind, wird die <xref:System.Windows.Forms.ErrorProvider.SetError%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="5db0b-111">The following code tests the validity of the data the user has entered; if the data is invalid, the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method is called.</span></span> <span data-ttu-id="5db0b-112">Das erste Argument der <xref:System.Windows.Forms.ErrorProvider.SetError%2A>-Methode gibt an, welches Steuerelement neben dem-Symbol angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5db0b-112">The first argument of the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method specifies which control to display the icon next to.</span></span> <span data-ttu-id="5db0b-113">Das zweite Argument ist der anzuzeigende Fehlertext.</span><span class="sxs-lookup"><span data-stu-id="5db0b-113">The second argument is the error text to display.</span></span>  
  
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
  
     <span data-ttu-id="5db0b-114">(Visualisierung C#, Visualisierung C++) Fügen Sie den folgenden Code in den Konstruktor des Formulars ein, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5db0b-114">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4. <span data-ttu-id="5db0b-115">Führen Sie das Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="5db0b-115">Run the project.</span></span> <span data-ttu-id="5db0b-116">Geben Sie ungültige (in diesem Beispiel nicht numerische) Daten in das erste Steuerelement ein, und drücken Sie dann die Tab-Taste.</span><span class="sxs-lookup"><span data-stu-id="5db0b-116">Type invalid (in this example, non-numeric) data into the first control, and then tab to the second.</span></span> <span data-ttu-id="5db0b-117">Wenn das Fehler Symbol angezeigt wird, zeigen Sie mit dem Mauszeiger darauf, um den Fehlertext anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5db0b-117">When the error icon is displayed, point at it with the mouse pointer to see the error text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db0b-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5db0b-118">See also</span></span>

- <xref:System.Windows.Forms.ErrorProvider.SetError%2A>
- [<span data-ttu-id="5db0b-119">Übersicht über die ErrorProvider-Komponente</span><span class="sxs-lookup"><span data-stu-id="5db0b-119">ErrorProvider Component Overview</span></span>](errorprovider-component-overview-windows-forms.md)
- [<span data-ttu-id="5db0b-120">Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5db0b-120">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](view-errors-within-a-dataset-with-wf-errorprovider-component.md)
