---
title: 'Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1be79d52be3b5b84938d8548a8f101e965fa9dbb
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015779"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="02f7d-102">Vorgehensweise: Testen des Lauf Zeit Verhaltens eines UserControl-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="02f7d-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="02f7d-103">Beim Entwickeln eines <xref:System.Windows.Forms.UserControl>muss das Laufzeitverhalten getestet werden.</span><span class="sxs-lookup"><span data-stu-id="02f7d-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="02f7d-104">Sie können ein separates Windows-basiertes Anwendungsprojekt erstellen und das Steuerelement in einem Testformular platzieren, aber dieses Verfahren ist nicht praktisch.</span><span class="sxs-lookup"><span data-stu-id="02f7d-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="02f7d-105">Ein schnelleres und einfacheres Verfahren besteht darin, den von Visual Studio bereitgestellten **UserControl-Test Container** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="02f7d-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="02f7d-106">Dieser Test Container startet direkt aus dem Windows-Steuerelement Bibliothek-Projekt.</span><span class="sxs-lookup"><span data-stu-id="02f7d-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02f7d-107">Damit der Test Container das Laden <xref:System.Windows.Forms.UserControl>kann, muss das Steuerelement über mindestens einen öffentlichen Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="02f7d-108">Ein visuelles C++ Steuerelement kann nicht mit dem **UserControl-Test Container**getestet werden.</span><span class="sxs-lookup"><span data-stu-id="02f7d-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="02f7d-109">Testen des Lauf Zeit Verhaltens eines UserControl-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="02f7d-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="02f7d-110">Erstellen Sie in Visual Studio ein Windows-Steuerelement Bibliothek-Projekt, und nennen Sie es **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="02f7d-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="02f7d-111">Ziehen Sie in der **Windows Forms-Designer**ein <xref:System.Windows.Forms.Label> -Steuerelement aus der **Toolbox** auf die Entwurfs Oberfläche des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="02f7d-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="02f7d-112">Drücken Sie **F5** , um das Projekt zu erstellen und den **UserControl-Test Container**auszuführen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-112">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="02f7d-113">Der Test Container wird mit Ihrem <xref:System.Windows.Forms.UserControl> im **Vorschau** Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02f7d-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="02f7d-114">Wählen Sie <xref:System.Windows.Forms.Control.BackColor%2A> die Eigenschaft aus, <xref:System.Windows.Forms.PropertyGrid> die im Steuerelement rechts neben dem **Vorschaufenster** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="02f7d-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="02f7d-115">Ändern Sie den Wert in **ControlDark**.</span><span class="sxs-lookup"><span data-stu-id="02f7d-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="02f7d-116">Beachten Sie, dass sich das Steuerelement in eine dunklere Farbe ändert.</span><span class="sxs-lookup"><span data-stu-id="02f7d-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="02f7d-117">Ändern Sie andere Eigenschaftswerte, und beobachten Sie die Auswirkung auf das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="02f7d-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="02f7d-118">Aktivieren Sie das Kontrollkästchen **Benutzer Steuerelement andocken** unter dem **Vorschau** Bereich.</span><span class="sxs-lookup"><span data-stu-id="02f7d-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="02f7d-119">Beachten Sie, dass die Größe des Steuer Elements geändert wird, um den Bereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="02f7d-120">Ändern Sie die Größe des Test Containers, und beobachten Sie, dass die Größe des Steuer Elements mit dem Bereich angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="02f7d-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="02f7d-121">Schließen Sie den Test Container.</span><span class="sxs-lookup"><span data-stu-id="02f7d-121">Close the test container.</span></span>

7. <span data-ttu-id="02f7d-122">Fügen Sie dem Projekt **TestContainerExample** ein weiteres Benutzer Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="02f7d-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="02f7d-123">Ziehen Sie in der **Windows Forms-Designer**ein <xref:System.Windows.Forms.Button> -Steuerelement aus der **Toolbox** auf die Entwurfs Oberfläche des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="02f7d-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="02f7d-124">Drücken Sie **F5** , um das Projekt zu erstellen und den Test Container auszuführen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-124">Press **F5** to build the project and run the test container.</span></span>

10. <span data-ttu-id="02f7d-125">Klicken Sie auf das **Benutzer Steuerelement auswählen** <xref:System.Windows.Forms.ComboBox> , um zwischen den beiden Benutzer Steuerelementen zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="02f7d-125">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="02f7d-126">Testen von Benutzer Steuerelementen aus einem anderen Projekt</span><span class="sxs-lookup"><span data-stu-id="02f7d-126">Test user controls from another project</span></span>

<span data-ttu-id="02f7d-127">Sie können Benutzer Steuerelemente aus anderen Projekten im Test Container Ihres aktuellen Projekts testen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="02f7d-128">Erstellen Sie in Visual Studio ein Windows-Steuerelement Bibliothek-Projekt, und nennen Sie es **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="02f7d-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="02f7d-129">Ziehen Sie in der **Windows Forms-Designer**ein <xref:System.Windows.Forms.RadioButton> -Steuerelement aus der **Toolbox** auf die Entwurfs Oberfläche des Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="02f7d-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="02f7d-130">Drücken Sie **F5** , um das Projekt zu erstellen und den Test Container auszuführen.</span><span class="sxs-lookup"><span data-stu-id="02f7d-130">Press **F5** to build the project and run the test container.</span></span> <span data-ttu-id="02f7d-131">Der Test Container wird mit Ihrem <xref:System.Windows.Forms.UserControl> im **Vorschau** Bereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02f7d-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="02f7d-132">Klicken Sie auf die Schaltfläche **Laden** .</span><span class="sxs-lookup"><span data-stu-id="02f7d-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="02f7d-133">Navigieren Sie im Dialogfeld **Öffnen** zu **TestContainerExample**. dll, das Sie im vorherigen Verfahren erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="02f7d-133">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="02f7d-134">Wählen Sie **TestContainerExample**. dll aus, und klicken Sie auf **Öffnen** , um die Benutzer Steuerelemente zu laden.</span><span class="sxs-lookup"><span data-stu-id="02f7d-134">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="02f7d-135">Verwenden **Sie das Benutzer Steuerelement auswählen** <xref:System.Windows.Forms.ComboBox> , um zwischen den beiden Benutzer Steuerelementen aus dem Projekt **TestContainerExample** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="02f7d-135">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="02f7d-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02f7d-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="02f7d-137">Vorgehensweise: Zusammengesetzte Steuerelemente verfassen</span><span class="sxs-lookup"><span data-stu-id="02f7d-137">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="02f7d-138">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="02f7d-138">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="02f7d-139">[Benutzer Steuerelement-Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02f7d-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
