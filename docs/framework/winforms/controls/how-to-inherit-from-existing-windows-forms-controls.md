---
title: Erben von vorhandenen Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: b0e0053816efde349c7e4d13d03bef5f8801c667
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849379"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="3286d-102">Gewusst wie: Erben von vorhandenen Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3286d-102">How to: Inherit from Existing Windows Forms Controls</span></span>

<span data-ttu-id="3286d-103">Wenn Sie die Funktionalität eines vorhandenen Steuerelements erweitern möchten, können Sie ein Steuerelement erstellen, dass durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="3286d-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="3286d-104">Beim Erben von einem vorhandenen Steuerelement erben Sie die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="3286d-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="3286d-105">Wenn Sie z. B. ein Steuerelement <xref:System.Windows.Forms.Button>erstellen, das von geerbt wurde, <xref:System.Windows.Forms.Button> würde das neue Steuerelement genau wie ein Standardsteuerelement aussehen und sich verhalten.</span><span class="sxs-lookup"><span data-stu-id="3286d-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="3286d-106">Sie können die Funktionalität Ihres neuen Steuerelements durch Implementieren von benutzerdefinierten Methoden und Eigenschaften erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="3286d-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="3286d-107">In einigen Steuerelementen können Sie auch die visuelle Darstellung des <xref:System.Windows.Forms.Control.OnPaint%2A> geerbten Steuerelements ändern, indem Sie seine Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3286d-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

## <a name="to-create-an-inherited-control"></a><span data-ttu-id="3286d-108">So erstellen Sie ein geerbtes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3286d-108">To create an inherited control</span></span>

1. <span data-ttu-id="3286d-109">Erstellen Sie in Visual Studio ein neues **Windows Forms Application-Projekt.**</span><span class="sxs-lookup"><span data-stu-id="3286d-109">In Visual Studio, create a new **Windows Forms Application** project.</span></span>

1. <span data-ttu-id="3286d-110">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3286d-110">From the **Project** menu, choose **Add New Item**.</span></span>

    <span data-ttu-id="3286d-111">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3286d-111">The **Add New Item** dialog box appears.</span></span>

1. <span data-ttu-id="3286d-112">Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.</span><span class="sxs-lookup"><span data-stu-id="3286d-112">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>

    <span data-ttu-id="3286d-113">Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3286d-113">A new custom control is added to your project.</span></span>

1. <span data-ttu-id="3286d-114">Wenn Sie verwenden:</span><span class="sxs-lookup"><span data-stu-id="3286d-114">If you're using:</span></span>

    - <span data-ttu-id="3286d-115">Visual Basic, oben im **Projektmappen-Explorer**, klicken Sie auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3286d-115">Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="3286d-116">Erweitern Sie „CustomControl1.vb“ und öffnen Sie „CustomControl1.Designer.vb“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="3286d-116">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>
    - <span data-ttu-id="3286d-117">Öffnen Sie CustomControl1.cs im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="3286d-117">C#, open CustomControl1.cs in the Code Editor.</span></span>

1. <span data-ttu-id="3286d-118">Suchen Sie die Klassendeklaration, die von erbt. <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="3286d-118">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>

1. <span data-ttu-id="3286d-119">Ändern Sie die Basisklasse in das Steuerelement, von dem Sie erben möchten.</span><span class="sxs-lookup"><span data-stu-id="3286d-119">Change the base class to the control that you want to inherit from.</span></span>

     <span data-ttu-id="3286d-120">Wenn Sie z. B. von <xref:System.Windows.Forms.Button>erben möchten, ändern Sie die Klassendeklaration wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3286d-120">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>

    ```vb
    Partial Class CustomControl1
        Inherits System.Windows.Forms.Button
    ```

    ```csharp
    public partial class CustomControl1 : System.Windows.Forms.Button
    ```

1. <span data-ttu-id="3286d-121">Wenn Sie Visual Basic verwenden, speichern und schließen Sie „CustomControl1.Designer.vb“.</span><span class="sxs-lookup"><span data-stu-id="3286d-121">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="3286d-122">Öffnen Sie „CustomControl1.vb“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="3286d-122">Open CustomControl1.vb in the Code Editor.</span></span>

1. <span data-ttu-id="3286d-123">Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3286d-123">Implement any custom methods or properties that your control will incorporate.</span></span>

1. <span data-ttu-id="3286d-124">Wenn Sie die grafische Darstellung des Steuerelements <xref:System.Windows.Forms.Control.OnPaint%2A> ändern möchten, überschreiben Sie die Methode.</span><span class="sxs-lookup"><span data-stu-id="3286d-124">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3286d-125">Durch <xref:System.Windows.Forms.Control.OnPaint%2A> das Überschreiben können Sie die Darstellung aller Steuerelemente nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3286d-125">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="3286d-126">Die Steuerelemente, die alle ihre Malerei von <xref:System.Windows.Forms.TextBox>Windows (zum Beispiel) gemacht haben, rufen niemals ihre <xref:System.Windows.Forms.Control.OnPaint%2A> Methode auf und werden daher niemals den benutzerdefinierten Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="3286d-126">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="3286d-127">In der Hilfedokumentation finden Sie das jeweilige Steuerelement, <xref:System.Windows.Forms.Control.OnPaint%2A> das Sie ändern möchten, um festzustellen, ob die Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3286d-127">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="3286d-128">Eine Liste aller Windows Form-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3286d-128">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="3286d-129">Wenn ein Steuerelement <xref:System.Windows.Forms.Control.OnPaint%2A> nicht als Membermethode aufgeführt ist, können Sie seine Darstellung nicht ändern, indem Sie diese Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="3286d-129">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="3286d-130">Weitere Informationen über benutzerdefinierte Darstellung finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="3286d-130">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

    ```vb
    Protected Overrides Sub OnPaint(ByVal e As _
       System.Windows.Forms.PaintEventArgs)
       MyBase.OnPaint(e)
       ' Insert code to do custom painting.
       ' If you want to completely change the appearance of your control,
       ' do not call MyBase.OnPaint(e).
    End Sub
    ```

    ```csharp
    protected override void OnPaint(PaintEventArgs pe)
    {
       base.OnPaint(pe);
       // Insert code to do custom painting.
       // If you want to completely change the appearance of your control,
       // do not call base.OnPaint(pe).
    }
    ```

1. <span data-ttu-id="3286d-131">Speichern und testen Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="3286d-131">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="3286d-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3286d-132">See also</span></span>

- [<span data-ttu-id="3286d-133">Arten von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="3286d-133">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="3286d-134">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="3286d-134">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="3286d-135">Gewusst wie: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="3286d-135">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="3286d-136">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3286d-136">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="3286d-137">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3286d-137">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="3286d-138">Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3286d-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
