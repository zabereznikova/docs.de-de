---
title: 'Gewusst wie: Testen des Laufzeitverhaltens eines UserControl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9ccf386acd50338f1743bbf8f6be38b3267a7103
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="9801a-102">Gewusst wie: Testen des Laufzeitverhaltens eines UserControl</span><span class="sxs-lookup"><span data-stu-id="9801a-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="9801a-103">Bei der Entwicklung einer <xref:System.Windows.Forms.UserControl>, müssen Sie dessen Laufzeitverhalten zu testen.</span><span class="sxs-lookup"><span data-stu-id="9801a-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="9801a-104">Sie können eine separate Windows-basiertes Anwendungsprojekt erstellen und platzieren Sie das Steuerelement auf einen Testformular, aber dieses Verfahren ist.</span><span class="sxs-lookup"><span data-stu-id="9801a-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="9801a-105">Eine Möglichkeit schnellere und einfachere, ist die Verwendung der **UserControl-Testcontainer** von Visual Studio bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9801a-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="9801a-106">Dieser Testcontainer wird direkt aus Ihrem Windows-Steuerelementbibliothek-Projekt gestartet.</span><span class="sxs-lookup"><span data-stu-id="9801a-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9801a-107">Für den Testcontainer laden Ihre <xref:System.Windows.Forms.UserControl>, das Steuerelement muss über mindestens einen öffentlichen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="9801a-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9801a-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="9801a-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9801a-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9801a-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9801a-110">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="9801a-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9801a-111">Ein Visual C++-Steuerelement kann nicht getestet werden, mithilfe der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="9801a-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="9801a-112">Zum Testen des Laufzeitverhaltens eines UserControl</span><span class="sxs-lookup"><span data-stu-id="9801a-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="9801a-113">Erstellen Sie eine Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="9801a-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="9801a-114">Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="9801a-114">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="9801a-115">In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="9801a-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="9801a-116">Drücken Sie F5, um das Projekt erstellen und Ausführen der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="9801a-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="9801a-117">Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in der **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="9801a-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="9801a-118">Wählen Sie die <xref:System.Windows.Forms.Control.BackColor%2A> angezeigten Eigenschaft der <xref:System.Windows.Forms.PropertyGrid> Steuerelement rechts neben der **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="9801a-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="9801a-119">Ändern Sie dessen Wert in `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="9801a-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="9801a-120">Beachten Sie, dass das Steuerelement in einer dunkleren Farbe ändert.</span><span class="sxs-lookup"><span data-stu-id="9801a-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="9801a-121">Wiederholen Sie den anderen Eigenschaftswerte ändern, und beobachten Sie die Auswirkung auf das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="9801a-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="9801a-122">Klicken Sie auf die **Fill-Benutzersteuerelement andocken** Kontrollkästchen unten die **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="9801a-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="9801a-123">Beachten Sie, dass das Steuerelement skaliert wird, um den Bereich zu füllen.</span><span class="sxs-lookup"><span data-stu-id="9801a-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="9801a-124">Die Größe des Testcontainers und beachten Sie, dass das Steuerelement mit dem Bereich angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="9801a-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="9801a-125">Schließen Sie den Testcontainer an.</span><span class="sxs-lookup"><span data-stu-id="9801a-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="9801a-126">Fügen Sie ein anderes Benutzersteuerelement, das **TestContainerExample** Projekt.</span><span class="sxs-lookup"><span data-stu-id="9801a-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="9801a-127">Einzelheiten finden Sie in [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="9801a-127">For details, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
8.  <span data-ttu-id="9801a-128">In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="9801a-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="9801a-129">Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus.</span><span class="sxs-lookup"><span data-stu-id="9801a-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="9801a-130">Klicken Sie auf die **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> Wechsel zwischen den beiden Benutzersteuerelemente.</span><span class="sxs-lookup"><span data-stu-id="9801a-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="9801a-131">Benutzersteuerelemente aus einem anderen Projekt testen</span><span class="sxs-lookup"><span data-stu-id="9801a-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="9801a-132">Sie können die Benutzersteuerelemente als andere Projekte in Ihrem aktuellen Projekt Testcontainer testen.</span><span class="sxs-lookup"><span data-stu-id="9801a-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="9801a-133">So testen Sie Benutzersteuerelemente aus einem anderen Projekt</span><span class="sxs-lookup"><span data-stu-id="9801a-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="9801a-134">Erstellen Sie eine Windows-Steuerelementbibliothek-Projekt namens **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="9801a-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="9801a-135">Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="9801a-135">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="9801a-136">In der **Windows Forms-Designer**, ziehen Sie eine <xref:System.Windows.Forms.RadioButton> -Steuerelement aus der **Toolbox** auf das Steuerelement-Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="9801a-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="9801a-137">Drücken Sie F5, um das Projekt erstellen, und führen Sie den Testcontainer aus.</span><span class="sxs-lookup"><span data-stu-id="9801a-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="9801a-138">Der Testcontainer wird mit Ihrem <xref:System.Windows.Forms.UserControl> in der **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="9801a-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="9801a-139">Klicken Sie auf die **laden** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="9801a-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="9801a-140">In der **öffnen** Dialogfeld Feld, navigieren Sie zu **TestContainerExample**.dll, die Sie im vorherigen Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="9801a-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="9801a-141">Wählen Sie **TestContainerExample**DLL-Datei, und klicken Sie auf die **öffnen** Schaltfläche, um die Benutzersteuerelemente zu laden.</span><span class="sxs-lookup"><span data-stu-id="9801a-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="9801a-142">Verwenden der **Benutzersteuerelement auswählen** <xref:System.Windows.Forms.ComboBox> So wechseln Sie zwischen die beiden Benutzersteuerelemente aus der **TestContainerExample** Projekt.</span><span class="sxs-lookup"><span data-stu-id="9801a-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9801a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9801a-143">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="9801a-144">Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="9801a-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="9801a-145">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9801a-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="9801a-146">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="9801a-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="9801a-147">Benutzersteuerelement-Designer</span><span class="sxs-lookup"><span data-stu-id="9801a-147">User Control Designer</span></span>](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
