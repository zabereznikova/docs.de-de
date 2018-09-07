---
title: 'Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 1b803a93f865eaa4db6751187213c4bb01d2a5ee
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44065200"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="92c0e-102">Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92c0e-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="92c0e-103">Die meisten Formulare werden durch Hinzufügen der Steuerelemente auf die Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren.</span><span class="sxs-lookup"><span data-stu-id="92c0e-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="92c0e-104">Ein *Steuerelement* ist eine Komponente in einem Formular zum Anzeigen von Informationen oder Benutzereingaben akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="92c0e-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="92c0e-105">Weitere Informationen zu Steuerelementen, finden Sie unter [Windows Forms-Steuerelemente](../../../../docs/framework/winforms/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="92c0e-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92c0e-106">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="92c0e-107">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="92c0e-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="92c0e-108">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="92c0e-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="92c0e-109">Zum Zeichnen eines Steuerelements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="92c0e-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="92c0e-110">Öffnen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="92c0e-110">Open the form.</span></span> <span data-ttu-id="92c0e-111">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="92c0e-111">For more information, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="92c0e-112">In der **Toolbox**, klicken Sie auf das Steuerelement zum Formular hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="92c0e-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="92c0e-113">Klicken Sie auf dem Formular klicken Sie auf der linken oberen Ecke des Steuerelements abgelegt werden sollen, und ziehen Sie in der unteren rechten Ecke des Steuerelements abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="92c0e-114">Das Steuerelement wird zum Formular mit der angegebenen Position und Größe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="92c0e-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c0e-115">Jedes Steuerelement verfügt über eine Standardgröße definiert.</span><span class="sxs-lookup"><span data-stu-id="92c0e-115">Each control has a default size defined.</span></span> <span data-ttu-id="92c0e-116">Sie können ein Steuerelement zum Formular in Standardgröße des Steuerelements hinzufügen, durch Ziehen aus dem **Toolbox** auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="92c0e-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="92c0e-117">Ziehen Sie ein Steuerelement zu einem Formular</span><span class="sxs-lookup"><span data-stu-id="92c0e-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="92c0e-118">Öffnen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="92c0e-118">Open the form.</span></span> <span data-ttu-id="92c0e-119">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Windows Forms im Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="92c0e-119">For more information, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="92c0e-120">In der **Toolbox**, klicken Sie auf das Steuerelement, Sie möchten, und ziehen Sie es in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="92c0e-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="92c0e-121">Das Steuerelement wird dem Formular an der angegebenen Position in der Standardgröße hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="92c0e-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c0e-122">Sie können ein Steuerelement in Doppelklicken Sie auf die **Toolbox** der oberen linken Ecke des Formulars in der Standardgröße hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="92c0e-123">Sie können auch Steuerelemente dynamisch zu einem Formular zur Laufzeit hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="92c0e-124">Das folgende Codebeispiel zeigt eine <xref:System.Windows.Forms.TextBox> Steuerelement wird dem Formular hinzugefügt werden bei einer <xref:System.Windows.Forms.Button> -Steuerelement geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="92c0e-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92c0e-125">Das folgende Verfahren erfordert das Vorhandensein eines Formulars mit einem **Schaltfläche** Steuerelement `Button1`, bereits platziert ist.</span><span class="sxs-lookup"><span data-stu-id="92c0e-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="92c0e-126">So ein Formular ein Steuerelement programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="92c0e-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="92c0e-127">In der Methode, die der Schaltfläche verarbeitet `Click` Ereignissatz innerhalb der Formularklasse Code einfügen, die etwa wie folgt einen Verweis auf die Steuerelementvariable Hinzufügen des Steuerelements `Location`, und fügen Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="92c0e-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="92c0e-128">Sie können auch Code zum Initialisieren der anderen Eigenschaften des Steuerelements hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="92c0e-129">Sie können den lokalen Computer ein Sicherheitsrisiko dar, über das Netzwerk verfügbar zu machen, durch Verweisen auf ein böswilliger `UserControl`.</span><span class="sxs-lookup"><span data-stu-id="92c0e-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="92c0e-130">Dies wäre nur ein Problem, wenn ein böswilliger Benutzer erstellt ein schädliches benutzerdefiniertes Steuerelement, indem Sie versehentlich zu Ihrem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="92c0e-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c0e-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92c0e-131">See Also</span></span>  
 [<span data-ttu-id="92c0e-132">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="92c0e-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="92c0e-133">Anordnen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92c0e-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="92c0e-134">Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92c0e-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="92c0e-135">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="92c0e-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="92c0e-136">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="92c0e-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
