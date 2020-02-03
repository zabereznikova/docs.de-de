---
title: Hinzufügen von Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 560089a23fbcccb0f0d5683a95ad06dd9c59556d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743959"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="0c4f2-102">Gewusst wie: Hinzufügen von Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c4f2-102">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="0c4f2-103">Die meisten Formulare werden durch das Hinzufügen von Steuerelementen zur Oberfläche des Formulars entworfen, um eine Benutzeroberfläche (UI) zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="0c4f2-104">Ein- *Steuer* Element ist eine Komponente auf einem Formular, mit dem Informationen angezeigt oder Benutzereingaben akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="0c4f2-105">Weitere Informationen zu-Steuerelementen finden Sie unter Windows Forms-Steuer [Elemente](index.md).</span><span class="sxs-lookup"><span data-stu-id="0c4f2-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="0c4f2-106">So zeichnen Sie ein Steuerelement in einem Formular</span><span class="sxs-lookup"><span data-stu-id="0c4f2-106">To draw a control on a form</span></span>

1. <span data-ttu-id="0c4f2-107">Öffnen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-107">Open the form.</span></span> <span data-ttu-id="0c4f2-108">Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0c4f2-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="0c4f2-109">Klicken Sie in der **Toolbox**auf das Steuerelement, das Sie dem Formular hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="0c4f2-110">Klicken Sie im Formular auf die Stelle, an der sich die obere linke Ecke des Steuer Elements befinden soll, und ziehen Sie an die Stelle, an der die untere rechte Ecke des Steuer Elements platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="0c4f2-111">Das-Steuerelement wird dem Formular mit der angegebenen Position und Größe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c4f2-112">Für jedes Steuerelement ist eine Standardgröße definiert.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-112">Each control has a default size defined.</span></span> <span data-ttu-id="0c4f2-113">Sie können dem Formular ein Steuerelement in der Standardgröße des Steuer Elements hinzufügen, indem Sie es aus der **Toolbox** in das Formular ziehen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="0c4f2-114">So ziehen Sie ein Steuerelement in ein Formular</span><span class="sxs-lookup"><span data-stu-id="0c4f2-114">To drag a control to a form</span></span>

1. <span data-ttu-id="0c4f2-115">Öffnen Sie das Formular.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-115">Open the form.</span></span> <span data-ttu-id="0c4f2-116">Weitere Informationen finden Sie unter Gewusst [wie: Anzeigen von Windows Forms im Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0c4f2-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="0c4f2-117">Klicken Sie in der **Toolbox**auf das gewünschte Steuerelement, und ziehen Sie es in das Formular.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="0c4f2-118">Das-Steuerelement wird dem Formular an der angegebenen Position in seiner Standardgröße hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c4f2-119">Sie können auf ein Steuerelement in der **Toolbox** doppelklicken, um es der oberen linken Ecke des Formulars in seiner Standardgröße hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="0c4f2-120">Sie können einem Formular auch zur Laufzeit dynamisch Steuerelemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="0c4f2-121">Im folgenden Codebeispiel wird dem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzugefügt, wenn auf ein <xref:System.Windows.Forms.Button> Steuerelement geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c4f2-122">Für das folgende Verfahren ist es erforderlich, dass ein Formular mit einem **Schalt** Flächen-Steuerelement vorhanden ist, `Button1`bereits darauf platziert ist.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="0c4f2-123">So fügen Sie einem Formular ein Steuerelement Programm gesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="0c4f2-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="0c4f2-124">Fügen Sie in der Methode, die das `Click`-Ereignis der Schaltfläche in der-Klasse des Formulars behandelt, Code ähnlich dem folgenden hinzu, um einen Verweis auf die Steuerelement Variable hinzuzufügen, die `Location`des Steuer Elements festzulegen und das-Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

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
    > <span data-ttu-id="0c4f2-125">Sie können auch Code hinzufügen, um andere Eigenschaften des Steuer Elements zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0c4f2-126">Sie können den lokalen Computer über das Netzwerk mit einem Sicherheitsrisiko verfügbar machen, indem Sie auf eine böswillige `UserControl`verweisen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="0c4f2-127">Dies wäre nur ein Problem, wenn eine böswillige Person ein schädliches benutzerdefiniertes Steuerelement erstellt, gefolgt von dem, das Sie versehentlich dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0c4f2-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c4f2-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c4f2-128">See also</span></span>

- [<span data-ttu-id="0c4f2-129">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="0c4f2-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="0c4f2-130">Gewusst wie: Ändern der Größe von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c4f2-130">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="0c4f2-131">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="0c4f2-131">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="0c4f2-132">Steuerelemente für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0c4f2-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
