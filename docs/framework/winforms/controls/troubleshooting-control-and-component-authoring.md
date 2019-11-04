---
title: Problembehandlung beim Erstellen von Komponenten und Steuerelementen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 9ee9df41e6f0a4e37164760a2e40740e31530121
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459076"
---
# <a name="troubleshoot-control-and-component-authoring"></a><span data-ttu-id="89da5-102">Problembehandlung beim Erstellen von Steuerelementen und Komponenten</span><span class="sxs-lookup"><span data-stu-id="89da5-102">Troubleshoot Control and Component Authoring</span></span>

<span data-ttu-id="89da5-103">In diesem Thema werden die folgenden allgemeinen Probleme aufgelistet, die beim Entwickeln von Komponenten und Steuerelementen auftreten:</span><span class="sxs-lookup"><span data-stu-id="89da5-103">This topic lists the following common problems that arise when developing components and controls:</span></span>

- <span data-ttu-id="89da5-104">Steuerelement kann nicht zur Toolbox hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="89da5-104">Cannot Add Control to Toolbox</span></span>

- <span data-ttu-id="89da5-105">Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden</span><span class="sxs-lookup"><span data-stu-id="89da5-105">Cannot Debug the Windows Forms User Control or Component</span></span>

- <span data-ttu-id="89da5-106">Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst</span><span class="sxs-lookup"><span data-stu-id="89da5-106">Event Is Raised Twice in Inherited Control or Component</span></span>

- <span data-ttu-id="89da5-107">Entwurfszeitfehler: „Failed to Create Component '*Component Name*'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)</span><span class="sxs-lookup"><span data-stu-id="89da5-107">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>

- <span data-ttu-id="89da5-108">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="89da5-108">STAThreadAttribute</span></span>

- <span data-ttu-id="89da5-109">Symbol „Komponente“ wird nicht in der Toolbox angezeigt</span><span class="sxs-lookup"><span data-stu-id="89da5-109">Component Icon Does Not Appear in Toolbox</span></span>

## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="89da5-110">Steuerelement kann nicht zur Toolbox hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="89da5-110">Cannot Add Control to Toolbox</span></span>

<span data-ttu-id="89da5-111">Wenn Sie ein benutzerdefiniertes Steuerelement, das Sie in einem anderen Projekt erstellt haben, oder ein Drittanbieter-Steuerelement zur **Toolbox** hinzufügen möchten, müssen Sie dies manuell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="89da5-111">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="89da5-112">Wenn das aktuelle Projekt ein Steuerelement oder eine Komponente enthält, sollte es automatisch in der **Toolbox** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="89da5-112">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="89da5-113">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="89da5-113">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="89da5-114">So fügen Sie der Toolbox ein Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="89da5-114">To add a control to the Toolbox</span></span>

1. <span data-ttu-id="89da5-115">Klicken Sie mit der rechten Maustaste auf **Toolbox**, und wählen Sie im Kontextmenü **Elemente auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="89da5-115">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>

2. <span data-ttu-id="89da5-116">Fügen Sie im Dialogfeld **Toolboxelemente auswählen** die Komponente hinzu:</span><span class="sxs-lookup"><span data-stu-id="89da5-116">In the **Choose Toolbox Items** dialog box, add the component:</span></span>

    - <span data-ttu-id="89da5-117">Wenn Sie eine .NET Framework-Komponente oder ein -Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **.NET Framework-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="89da5-117">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>

         <span data-ttu-id="89da5-118">– oder –</span><span class="sxs-lookup"><span data-stu-id="89da5-118">– or –</span></span>

    - <span data-ttu-id="89da5-119">Wenn Sie eine COM-Komponente oder ein ActiveX-Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **COM-Steuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="89da5-119">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>

3. <span data-ttu-id="89da5-120">Wenn das Steuerelement im Dialogfeld aufgelistet ist, bestätigen Sie die Auswahl, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="89da5-120">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>

     <span data-ttu-id="89da5-121">Das Steuerelement wird zur **Toolbox** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="89da5-121">The control is added to the **Toolbox**.</span></span>

4. <span data-ttu-id="89da5-122">Wenn Ihr Steuerelement nicht im Dialogfeld aufgelistet ist, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="89da5-122">If your control is not listed in the dialog box, do the following:</span></span>

    1. <span data-ttu-id="89da5-123">Klicken Sie auf die Schaltfläche **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="89da5-123">Click the **Browse** button.</span></span>

    2. <span data-ttu-id="89da5-124">Navigieren Sie zum Ordner mit der DLL-Datei, die Ihr Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="89da5-124">Browse to the folder that contains the .dll file that contains your control.</span></span>

    3. <span data-ttu-id="89da5-125">Wählen Sie die DLL-Datei aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="89da5-125">Select the .dll file and click **Open**.</span></span>

         <span data-ttu-id="89da5-126">Das Steuerelement wird im Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89da5-126">Your control appears in the dialog box.</span></span>

    4. <span data-ttu-id="89da5-127">Bestätigen Sie die Auswahl des Steuerelements, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="89da5-127">Confirm that your control is selected, and then click **OK**.</span></span>

         <span data-ttu-id="89da5-128">Ihr Steuerelement wird zur **Toolbox** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="89da5-128">Your control is added to the **Toolbox**.</span></span>

## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="89da5-129">Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden</span><span class="sxs-lookup"><span data-stu-id="89da5-129">Cannot Debug the Windows Forms User Control or Component</span></span>

<span data-ttu-id="89da5-130">Wenn das Steuerelement von der <xref:System.Windows.Forms.UserControl>-Klasse abgeleitet ist, können Sie das Laufzeitverhalten mit dem Test Container Debuggen.</span><span class="sxs-lookup"><span data-stu-id="89da5-130">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="89da5-131">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="89da5-131">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="89da5-132">Andere benutzerdefinierte Steuerelemente und Komponenten sind keine eigenständigen Projekte.</span><span class="sxs-lookup"><span data-stu-id="89da5-132">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="89da5-133">Sie müssen von einer Anwendung wie einem Windows Forms-Projekt gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="89da5-133">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="89da5-134">Zum Debuggen eines Steuerelements oder einer Komponente müssen Sie sie zu einem Windows Forms-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89da5-134">To debug a control or component, you must add it to a Windows Forms project.</span></span>

### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="89da5-135">So debuggen Sie ein Steuerelement oder eine Komponente</span><span class="sxs-lookup"><span data-stu-id="89da5-135">To debug a control or component</span></span>

1. <span data-ttu-id="89da5-136">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um eine Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89da5-136">From the **Build** menu, click **Build Solution** to build your solution.</span></span>

2. <span data-ttu-id="89da5-137">Wählen Sie im Menü **Datei** **Hinzufügen** und dann **Neues Projekt** aus, um ein Testprojekt zu Ihrer Anwendung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="89da5-137">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>

3. <span data-ttu-id="89da5-138">Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** für den Projekttyp **Windows-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="89da5-138">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>

4. <span data-ttu-id="89da5-139">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für das neue Projekt.</span><span class="sxs-lookup"><span data-stu-id="89da5-139">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="89da5-140">Klicken Sie im Kontextmenü auf **Verweis hinzufügen**, um einen Verweis auf das Projekt mit dem Steuerelement oder der Komponente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="89da5-140">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>

5. <span data-ttu-id="89da5-141">Erstellen Sie eine Instanz des Steuerelements oder der Komponente im Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="89da5-141">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="89da5-142">Wenn sich Ihre Komponente in der **Toolbox** befindet, können Sie sie auf die Oberfläche des Designers ziehen, oder die Instanz programmgesteuert erstellen, wie im folgenden Codebeispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="89da5-142">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>

    ```vb
    Dim Component1 As New MyNeatComponent()
    ```

    ```csharp
    MyNeatComponent Component1 = new MyNeatComponent();
    ```

   <span data-ttu-id="89da5-143">Sie können jetzt das Steuerelement oder die Komponente wie gewohnt debuggen.</span><span class="sxs-lookup"><span data-stu-id="89da5-143">You can now debug your control or component as usual.</span></span>

<span data-ttu-id="89da5-144">Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour) und [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="89da5-144">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugger-feature-tour) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>

## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="89da5-145">Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst</span><span class="sxs-lookup"><span data-stu-id="89da5-145">Event Is Raised Twice in Inherited Control or Component</span></span>

<span data-ttu-id="89da5-146">Dies liegt wahrscheinlich an einer doppelten `Handles`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="89da5-146">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="89da5-147">Weitere Informationen finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="89da5-147">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="89da5-148">Entwurfszeitfehler: „Failed to Create Component 'Component Name'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)</span><span class="sxs-lookup"><span data-stu-id="89da5-148">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>

<span data-ttu-id="89da5-149">Die Komponente oder das Steuerelement muss einen Parameter losen Konstruktor ohne Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="89da5-149">Your component or control must provide a parameterless constructor with no parameters.</span></span> <span data-ttu-id="89da5-150">Wenn die Entwurfsumgebung eine Instanz der Komponente oder des Steuerelements erstellt, versucht sie nicht, Parameter auf Konstruktorüberladungen bereitzustellen, die Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="89da5-150">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>

## <a name="stathreadattribute"></a><span data-ttu-id="89da5-151">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="89da5-151">STAThreadAttribute</span></span>

<span data-ttu-id="89da5-152">Der <xref:System.STAThreadAttribute> informiert den Common Language Runtime (CLR), dass Windows Forms das Single Thread-Apartment Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="89da5-152">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="89da5-153">Möglicherweise kommt es zu unbeabsichtigtem Verhalten, wenn Sie dieses Attribut nicht auf die `Main`-Methode Ihrer Windows Forms Anwendung anwenden.</span><span class="sxs-lookup"><span data-stu-id="89da5-153">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="89da5-154">Beispielsweise können Hintergrundbilder für Steuerelemente wie <xref:System.Windows.Forms.ListView>nicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="89da5-154">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="89da5-155">Einige Steuerelemente benötigen dieses Attribut möglicherweise für korrektes AutoComplete- und Drag & Drop-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="89da5-155">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>

## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="89da5-156">Symbol „Komponente“ wird nicht in der Toolbox angezeigt</span><span class="sxs-lookup"><span data-stu-id="89da5-156">Component Icon Does Not Appear in Toolbox</span></span>

<span data-ttu-id="89da5-157">Wenn Sie <xref:System.Drawing.ToolboxBitmapAttribute> verwenden, um der benutzerdefinierten Komponente ein Symbol zuzuordnen, wird die Bitmap für automatisch generierte Komponenten nicht in der Toolbox angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89da5-157">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="89da5-158">Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89da5-158">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="89da5-159">Weitere Informationen finden Sie unter [Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span><span class="sxs-lookup"><span data-stu-id="89da5-159">For more information, see [How to: Provide a Toolbox Bitmap for a Control](how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="89da5-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89da5-160">See also</span></span>

- [<span data-ttu-id="89da5-161">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="89da5-161">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="89da5-162">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="89da5-162">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [<span data-ttu-id="89da5-163">Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl</span><span class="sxs-lookup"><span data-stu-id="89da5-163">How to: Test the Run-Time Behavior of a UserControl</span></span>](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [<span data-ttu-id="89da5-164">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="89da5-164">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
