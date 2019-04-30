---
title: 'Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 788addee7c024577d029626da4aeb86d0ca9076a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941153"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="ac8e0-102">Vorgehensweise: Erben von vorhandenen Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ac8e0-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="ac8e0-103">Wenn Sie die Funktionalität eines vorhandenen Steuerelements erweitern möchten, können Sie ein Steuerelement erstellen, dass durch Vererbung von einem vorhandenen Steuerelement abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="ac8e0-104">Beim Erben von einem vorhandenen Steuerelement erben Sie die gesamte Funktionalität und die visuellen Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="ac8e0-105">Angenommen, Sie ein Steuerelement erstellt haben, die von geerbt <xref:System.Windows.Forms.Button>, das neue Steuerelement sieht und Act, genau wie ein standardmäßiges <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="ac8e0-106">Sie können die Funktionalität Ihres neuen Steuerelements durch Implementieren von benutzerdefinierten Methoden und Eigenschaften erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="ac8e0-107">Bei einigen Steuerelementen können Sie auch die visuelle Darstellung des geerbten Steuerelements ändern, indem Sie überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac8e0-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ac8e0-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ac8e0-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ac8e0-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="ac8e0-111">So erstellen Sie ein geerbtes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ac8e0-111">To create an inherited control</span></span>  
  
1. <span data-ttu-id="ac8e0-112">Erstellen Sie ein neues **Windows Forms-Anwendungsprojekt**.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-112">Create a new **Windows Forms Application** project.</span></span>  
  
2. <span data-ttu-id="ac8e0-113">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="ac8e0-114">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-114">The **Add New Item** dialog box appears.</span></span>  
  
3. <span data-ttu-id="ac8e0-115">Doppelklicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="ac8e0-116">Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-116">A new custom control is added to your project.</span></span>  
  
4. <span data-ttu-id="ac8e0-117">Wenn Sie Visual Basic verwenden, klicken Sie am Anfang des **Projektmappen-Explorers** auf **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="ac8e0-118">Erweitern Sie „CustomControl1.vb“ und öffnen Sie „CustomControl1.Designer.vb“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5. <span data-ttu-id="ac8e0-119">Wenn Sie C# verwenden, öffnen Sie „CustomControl1.cs“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6. <span data-ttu-id="ac8e0-120">Suchen Sie die Klassendeklaration, die von erbt <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7. <span data-ttu-id="ac8e0-121">Ändern Sie die Basisklasse in das Steuerelement, von dem Sie erben möchten.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="ac8e0-122">Wenn Sie erben möchten z. B. <xref:System.Windows.Forms.Button>, ändern Sie die Klassendeklaration in Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ac8e0-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8. <span data-ttu-id="ac8e0-123">Wenn Sie Visual Basic verwenden, speichern und schließen Sie „CustomControl1.Designer.vb“.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="ac8e0-124">Öffnen Sie „CustomControl1.vb“ im Code-Editor.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="ac8e0-125">Implementieren Sie alle benutzerdefinierten Methoden oder Eigenschaften, die in das Steuerelement eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="ac8e0-126">Wenn Sie die grafische Darstellung des Steuerelements ändern möchten, überschreiben die <xref:System.Windows.Forms.Control.OnPaint%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac8e0-127">Überschreiben von <xref:System.Windows.Forms.Control.OnPaint%2A> nicht können Sie die Darstellung aller Steuerelemente ändern.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="ac8e0-128">Diese Steuerelemente, die alle vollständig von Windows gezeichnet werden (z. B. <xref:System.Windows.Forms.TextBox>) niemals aufrufen ihre <xref:System.Windows.Forms.Control.OnPaint%2A> -Methode, und verwenden daher nie verwenden den benutzerdefinierten Code.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="ac8e0-129">Finden Sie in der Hilfedokumentation für das bestimme Steuerelement, das Sie ändern, finden Sie unter möchten den <xref:System.Windows.Forms.Control.OnPaint%2A> Methode verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="ac8e0-130">Eine Liste aller Windows Form-Steuerelemente finden Sie unter [Steuerelemente für Windows Forms](controls-to-use-on-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ac8e0-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="ac8e0-131">Wenn ein Steuerelement keinen <xref:System.Windows.Forms.Control.OnPaint%2A> als Membermethode aufgelistet, Sie können nicht geändert werden seine Darstellung durch diese Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="ac8e0-132">Weitere Informationen über benutzerdefinierte Darstellung finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="ac8e0-132">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>  
  
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
  
11. <span data-ttu-id="ac8e0-133">Speichern und testen Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ac8e0-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac8e0-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac8e0-134">See also</span></span>

- [<span data-ttu-id="ac8e0-135">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="ac8e0-135">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="ac8e0-136">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="ac8e0-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="ac8e0-137">Vorgehensweise: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="ac8e0-137">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="ac8e0-138">Vorgehensweise: Erstellen von Steuerelementen für Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ac8e0-138">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="ac8e0-139">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac8e0-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="ac8e0-140">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac8e0-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="ac8e0-141">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit visuellen ElementC#</span><span class="sxs-lookup"><span data-stu-id="ac8e0-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
