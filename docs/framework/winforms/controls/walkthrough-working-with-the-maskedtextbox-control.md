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
ms.openlocfilehash: bcca6c5f5481d351a39a4e71532cc0f006075128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538440"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="050f1-102">Exemplarische Vorgehensweise: Arbeiten mit dem MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="050f1-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="050f1-103">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="050f1-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="050f1-104">Initialisieren der <xref:System.Windows.Forms.MaskedTextBox> Steuerelement</span><span class="sxs-lookup"><span data-stu-id="050f1-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="050f1-105">Mithilfe der <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> -Ereignishandler, um den Benutzer zu warnen, wenn ein Zeichen nicht der Maske entspricht</span><span class="sxs-lookup"><span data-stu-id="050f1-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="050f1-106">Zuweisen eines Typs für die <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> -Eigenschaft und die Verwendung der <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> -Ereignishandler, um den Benutzer zu warnen, wenn sie versuchen, einen commit für Wert für den Typ ungültig ist</span><span class="sxs-lookup"><span data-stu-id="050f1-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="050f1-107">Erstellen des Projekts und Hinzufügen eines Steuerelements</span><span class="sxs-lookup"><span data-stu-id="050f1-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="050f1-108">MaskedTextBox-Steuerelement zum Formular hinzufügen</span><span class="sxs-lookup"><span data-stu-id="050f1-108">To add a MaskedTextBox control to your form</span></span>  
  
1.  <span data-ttu-id="050f1-109">Öffnen Sie das Formular, das auf dem sollen die <xref:System.Windows.Forms.MaskedTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="050f1-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2.  <span data-ttu-id="050f1-110">Ziehen Sie eine <xref:System.Windows.Forms.MaskedTextBox> -Steuerelement aus der **Toolbox** in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="050f1-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3.  <span data-ttu-id="050f1-111">Mit der rechten Maustaste in des Steuerelements, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="050f1-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="050f1-112">In der **Eigenschaften** wählen die **Maske** -Eigenschaft, und klicken Sie auf der **...**  (Schaltfläche) neben dem Eigenschaftennamen.</span><span class="sxs-lookup"><span data-stu-id="050f1-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4.  <span data-ttu-id="050f1-113">In der **Eingabeformat** wählen Sie im Dialogfeld die **kurzes Datum** verborgen sind, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="050f1-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5.  <span data-ttu-id="050f1-114">In der **Eigenschaften** Fenster Satz der <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="050f1-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="050f1-115">Diese Eigenschaft bewirkt, dass einen kurze Signalton ausgegeben, jedes Mal, wenn der Benutzer versucht, ein Eingabezeichen, das die Maskendefinition verletzt.</span><span class="sxs-lookup"><span data-stu-id="050f1-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="050f1-116">Eine Zusammenfassung der Zeichen, die die Mask-Eigenschaft unterstützt, finden Sie im Abschnitt "Hinweise" der <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="050f1-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="050f1-117">Benachrichtigt den Benutzer zur Eingabe von Fehlern</span><span class="sxs-lookup"><span data-stu-id="050f1-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="050f1-118">Fügen Sie eine SprechblasenInfo für abgelehnte Maskeneingabe hinzu</span><span class="sxs-lookup"><span data-stu-id="050f1-118">Add a balloon tip for rejected mask input</span></span>  
  
1.  <span data-ttu-id="050f1-119">Zurück zu den **Toolbox** und Hinzufügen einer <xref:System.Windows.Forms.ToolTip> in Ihr Formular.</span><span class="sxs-lookup"><span data-stu-id="050f1-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2.  <span data-ttu-id="050f1-120">Erstellen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> Ereignis, das löst die <xref:System.Windows.Forms.ToolTip> tritt ein Eingabefehler.</span><span class="sxs-lookup"><span data-stu-id="050f1-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="050f1-121">Die SprechblasenInfo bleibt sichtbar, fünf Sekunden lang oder bis der Benutzer darauf klickt.</span><span class="sxs-lookup"><span data-stu-id="050f1-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
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
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="050f1-122">Warnen des Benutzers auf einen Typ, der ungültig ist</span><span class="sxs-lookup"><span data-stu-id="050f1-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="050f1-123">Fügen Sie eine SprechblasenInfo für ungültige Datentypen</span><span class="sxs-lookup"><span data-stu-id="050f1-123">Add a balloon tip for invalid data types</span></span>  
  
1.  <span data-ttu-id="050f1-124">In Ihrem Formulars <xref:System.Windows.Forms.Form.Load> Ereignishandler, d. h. weisen eine <xref:System.Type> Objekt darstellt der <xref:System.DateTime> Geben Sie auf der <xref:System.Windows.Forms.MaskedTextBox> des Steuerelements <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="050f1-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
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
  
2.  <span data-ttu-id="050f1-125">Fügen Sie einen Ereignishandler für das <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>-Ereignis hinzu:</span><span class="sxs-lookup"><span data-stu-id="050f1-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="050f1-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="050f1-126">See Also</span></span>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [<span data-ttu-id="050f1-127">MaskedTextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="050f1-127">MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
