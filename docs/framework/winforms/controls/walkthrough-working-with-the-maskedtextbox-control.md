---
title: 'Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: db32b3ec88a07747ea3e286af9f04edce3f1ba3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182059"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="23539-102">Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="23539-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="23539-103">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="23539-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="23539-104">Initialisieren <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="23539-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="23539-105">Verwenden <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> des Ereignishandlers, um den Benutzer zu warnen, wenn ein Zeichen nicht mit der Maske übereinstimmt</span><span class="sxs-lookup"><span data-stu-id="23539-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="23539-106">Zuweisen eines Typs <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> zur Eigenschaft <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> und Verwenden des Ereignishandlers zum Warnen des Benutzers, wenn der Wert, den er zu übertragen versucht, für den Typ ungültig ist</span><span class="sxs-lookup"><span data-stu-id="23539-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="23539-107">Erstellen des Projekts und Hinzufügen eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="23539-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="23539-108">So fügen Sie dem Formular ein MaskedTextBox-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="23539-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="23539-109">Öffnen Sie das Formular, in <xref:System.Windows.Forms.MaskedTextBox> dem Sie das Steuerelement platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="23539-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="23539-110">Ziehen <xref:System.Windows.Forms.MaskedTextBox> Sie ein Steuerelement aus der **Toolbox** in das Formular.</span><span class="sxs-lookup"><span data-stu-id="23539-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="23539-111">Klicken Sie mit der rechten Maustaste auf das Steuerelement, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="23539-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="23539-112">Wählen Sie im **Eigenschaftenfenster** die **Mask-Eigenschaft** aus, und klicken Sie auf die Schaltfläche **...** (Auslassungspunkte) neben dem Eigenschaftsnamen.</span><span class="sxs-lookup"><span data-stu-id="23539-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="23539-113">Wählen Sie im Dialogfeld **Eingabemaske** die **Kurzdatumsmaske** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="23539-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="23539-114">Legen Sie im <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> **Eigenschaftenfenster** die Eigenschaft auf fest. `true`</span><span class="sxs-lookup"><span data-stu-id="23539-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="23539-115">Diese Eigenschaft bewirkt, dass jedes Mal, wenn der Benutzer versucht, ein Zeichen einzugeben, das gegen die Maskendefinition verstößt, ein kurzer Signalton ertönt.</span><span class="sxs-lookup"><span data-stu-id="23539-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="23539-116">Eine Zusammenfassung der Zeichen, die von der Mask-Eigenschaft <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> unterstützt werden, finden Sie im Abschnitt "Bemerkungen" der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="23539-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="23539-117">Warnung des Benutzers vor Eingabefehlern</span><span class="sxs-lookup"><span data-stu-id="23539-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="23539-118">Hinzufügen einer Sprechblasenspitze für abgelehnte Maskeneingabe</span><span class="sxs-lookup"><span data-stu-id="23539-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="23539-119">Kehren Sie zur Toolbox <xref:System.Windows.Forms.ToolTip> **zurück,** und fügen Sie dem Formular eine hinzu.</span><span class="sxs-lookup"><span data-stu-id="23539-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="23539-120">Erstellen Sie einen <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> Ereignishandler für <xref:System.Windows.Forms.ToolTip> das Ereignis, das den Zeitpunkt auslöst, an dem ein Eingabefehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="23539-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="23539-121">Die Ballonspitze bleibt fünf Sekunden lang sichtbar, oder bis der Benutzer darauf klickt.</span><span class="sxs-lookup"><span data-stu-id="23539-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="23539-122">Warnung des Benutzers auf einen ungültigen Typ</span><span class="sxs-lookup"><span data-stu-id="23539-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="23539-123">Hinzufügen einer Sprechblasenspitze für ungültige Datentypen</span><span class="sxs-lookup"><span data-stu-id="23539-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="23539-124">Weisen Sie im <xref:System.Windows.Forms.Form.Load> Ereignishandler des <xref:System.Type> Formulars <xref:System.DateTime> der <xref:System.Windows.Forms.MaskedTextBox> Eigenschaft des <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> Steuerelements ein Objekt zu, das den Typ darstellt:</span><span class="sxs-lookup"><span data-stu-id="23539-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="23539-125">Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>-Ereignis hinzu:</span><span class="sxs-lookup"><span data-stu-id="23539-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23539-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23539-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="23539-127">MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="23539-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
