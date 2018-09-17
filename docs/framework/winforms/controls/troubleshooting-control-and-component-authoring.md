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
ms.openlocfilehash: caad6a76b52a970e133425c484602deb8801d252
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45692822"
---
# <a name="troubleshooting-control-and-component-authoring"></a><span data-ttu-id="87613-102">Problembehandlung beim Erstellen von Komponenten und Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="87613-102">Troubleshooting Control and Component Authoring</span></span>
<span data-ttu-id="87613-103">Dieses Thema listet die folgenden allgemeinen Probleme auf, die beim Entwickeln von Komponenten und Steuerelementen auftreten.</span><span class="sxs-lookup"><span data-stu-id="87613-103">This topic lists the following common problems that arise when developing components and controls.</span></span> <span data-ttu-id="87613-104">Weitere Informationen finden Sie unter [Programmieren mit Komponenten](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span><span class="sxs-lookup"><span data-stu-id="87613-104">For more information, see [Programming with Components](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
-   <span data-ttu-id="87613-105">Steuerelement kann nicht zur Toolbox hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="87613-105">Cannot Add Control to Toolbox</span></span>  
  
-   <span data-ttu-id="87613-106">Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden</span><span class="sxs-lookup"><span data-stu-id="87613-106">Cannot Debug the Windows Forms User Control or Component</span></span>  
  
-   <span data-ttu-id="87613-107">Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst</span><span class="sxs-lookup"><span data-stu-id="87613-107">Event Is Raised Twice in Inherited Control or Component</span></span>  
  
-   <span data-ttu-id="87613-108">Entwurfszeitfehler: „Failed to Create Component '*Component Name*'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)</span><span class="sxs-lookup"><span data-stu-id="87613-108">Design-Time Error: "Failed to Create Component '*Component Name*'"</span></span>  
  
-   <span data-ttu-id="87613-109">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="87613-109">STAThreadAttribute</span></span>  
  
-   <span data-ttu-id="87613-110">Symbol „Komponente“ wird nicht in der Toolbox angezeigt</span><span class="sxs-lookup"><span data-stu-id="87613-110">Component Icon Does Not Appear in Toolbox</span></span>  
  
## <a name="cannot-add-control-to-toolbox"></a><span data-ttu-id="87613-111">Steuerelement kann nicht zur Toolbox hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="87613-111">Cannot Add Control to Toolbox</span></span>  
 <span data-ttu-id="87613-112">Wenn Sie ein benutzerdefiniertes Steuerelement, das Sie in einem anderen Projekt erstellt haben, oder ein Drittanbieter-Steuerelement zur **Toolbox** hinzufügen möchten, müssen Sie dies manuell vornehmen.</span><span class="sxs-lookup"><span data-stu-id="87613-112">If you want to add a custom control that you created in another project or a third-party control to the **Toolbox**, you must do so manually.</span></span> <span data-ttu-id="87613-113">Wenn das aktuelle Projekt ein Steuerelement oder eine Komponente enthält, sollte es automatisch in der **Toolbox** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87613-113">If the current project contains your control or component, it should appear in the **Toolbox** automatically.</span></span> <span data-ttu-id="87613-114">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="87613-114">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
#### <a name="to-add-a-control-to-the-toolbox"></a><span data-ttu-id="87613-115">So fügen Sie der Toolbox ein Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="87613-115">To add a control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="87613-116">Klicken Sie mit der rechten Maustaste auf **Toolbox**, und wählen Sie im Kontextmenü **Elemente auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="87613-116">Right-click the **Toolbox** and from the shortcut menu, select **Choose Items**.</span></span>  
  
2.  <span data-ttu-id="87613-117">Fügen Sie im Dialogfeld **Toolboxelemente auswählen** die Komponente hinzu:</span><span class="sxs-lookup"><span data-stu-id="87613-117">In the **Choose Toolbox Items** dialog box, add the component:</span></span>  
  
    -   <span data-ttu-id="87613-118">Wenn Sie eine .NET Framework-Komponente oder ein -Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **.NET Framework-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="87613-118">If you want to add a .NET Framework component or control, click the **.NET Framework Components** tab.</span></span>  
  
         <span data-ttu-id="87613-119">– oder –</span><span class="sxs-lookup"><span data-stu-id="87613-119">– or –</span></span>  
  
    -   <span data-ttu-id="87613-120">Wenn Sie eine COM-Komponente oder ein ActiveX-Steuerelement hinzufügen möchten, klicken Sie auf die Registerkarte **COM-Steuerelemente**.</span><span class="sxs-lookup"><span data-stu-id="87613-120">If you want to add a COM component or ActiveX control, click the **COM Components** tab.</span></span>  
  
3.  <span data-ttu-id="87613-121">Wenn das Steuerelement im Dialogfeld aufgelistet ist, bestätigen Sie die Auswahl, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87613-121">If your control is listed in the dialog box, confirm it is selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="87613-122">Das Steuerelement wird zur **Toolbox** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87613-122">The control is added to the **Toolbox**.</span></span>  
  
4.  <span data-ttu-id="87613-123">Wenn Ihr Steuerelement nicht im Dialogfeld aufgelistet ist, führen Sie folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="87613-123">If your control is not listed in the dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="87613-124">Klicken Sie auf die Schaltfläche **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="87613-124">Click the **Browse** button.</span></span>  
  
    2.  <span data-ttu-id="87613-125">Navigieren Sie zum Ordner mit der DLL-Datei, die Ihr Steuerelement enthält.</span><span class="sxs-lookup"><span data-stu-id="87613-125">Browse to the folder that contains the .dll file that contains your control.</span></span>  
  
    3.  <span data-ttu-id="87613-126">Wählen Sie die DLL-Datei aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="87613-126">Select the .dll file and click **Open**.</span></span>  
  
         <span data-ttu-id="87613-127">Das Steuerelement wird im Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87613-127">Your control appears in the dialog box.</span></span>  
  
    4.  <span data-ttu-id="87613-128">Bestätigen Sie die Auswahl des Steuerelements, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="87613-128">Confirm that your control is selected, and then click **OK**.</span></span>  
  
         <span data-ttu-id="87613-129">Ihr Steuerelement wird zur **Toolbox** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87613-129">Your control is added to the **Toolbox**.</span></span>  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a><span data-ttu-id="87613-130">Windows Forms-Benutzersteuerelement oder Komponente kann nicht debuggt werden</span><span class="sxs-lookup"><span data-stu-id="87613-130">Cannot Debug the Windows Forms User Control or Component</span></span>  
 <span data-ttu-id="87613-131">Wenn das Steuerelement abgeleitet der <xref:System.Windows.Forms.UserControl> -Klasse, Sie können das Verhalten der Laufzeit mit dem Testcontainer debuggen.</span><span class="sxs-lookup"><span data-stu-id="87613-131">If your control derives from the <xref:System.Windows.Forms.UserControl> class, you can debug its run-time behavior with the test container.</span></span> <span data-ttu-id="87613-132">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="87613-132">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="87613-133">Andere benutzerdefinierte Steuerelemente und Komponenten sind keine eigenständigen Projekte.</span><span class="sxs-lookup"><span data-stu-id="87613-133">Other custom controls and components are not stand-alone projects.</span></span> <span data-ttu-id="87613-134">Sie müssen von einer Anwendung wie einem Windows Forms-Projekt gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="87613-134">They must be hosted by an application such as a Windows Forms project.</span></span> <span data-ttu-id="87613-135">Zum Debuggen eines Steuerelements oder einer Komponente müssen Sie sie zu einem Windows Forms-Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="87613-135">To debug a control or component, you must add it to a Windows Forms project.</span></span>  
  
#### <a name="to-debug-a-control-or-component"></a><span data-ttu-id="87613-136">So debuggen Sie ein Steuerelement oder eine Komponente</span><span class="sxs-lookup"><span data-stu-id="87613-136">To debug a control or component</span></span>  
  
1.  <span data-ttu-id="87613-137">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**, um eine Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87613-137">From the **Build** menu, click **Build Solution** to build your solution.</span></span>  
  
2.  <span data-ttu-id="87613-138">Wählen Sie im Menü **Datei** **Hinzufügen** und dann **Neues Projekt** aus, um ein Testprojekt zu Ihrer Anwendung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="87613-138">From the **File** menu, choose **Add**, and then **New Project** to add a test project to your application.</span></span>  
  
3.  <span data-ttu-id="87613-139">Wählen Sie im Dialogfeld **Neues Projekt hinzufügen** für den Projekttyp **Windows-Anwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="87613-139">In the **Add New Project** dialog box choose **Windows Application** for the type of project.</span></span>  
  
4.  <span data-ttu-id="87613-140">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für das neue Projekt.</span><span class="sxs-lookup"><span data-stu-id="87613-140">In **Solution Explorer**, right-click the **References** node for the new project.</span></span> <span data-ttu-id="87613-141">Klicken Sie im Kontextmenü auf **Verweis hinzufügen**, um einen Verweis auf das Projekt mit dem Steuerelement oder der Komponente hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="87613-141">On the shortcut menu, click **Add Reference** to add a reference to the project containing the control or component.</span></span>  
  
5.  <span data-ttu-id="87613-142">Erstellen Sie eine Instanz des Steuerelements oder der Komponente im Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="87613-142">Create an instance of your control or component in the test project.</span></span> <span data-ttu-id="87613-143">Wenn sich Ihre Komponente in der **Toolbox** befindet, können Sie sie auf die Oberfläche des Designers ziehen, oder die Instanz programmgesteuert erstellen, wie im folgenden Codebeispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87613-143">If your component is in the **Toolbox**, you can drag it to your designer surface, or you can create the instance programmatically, as shown in the following code example.</span></span>  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     <span data-ttu-id="87613-144">Sie können jetzt das Steuerelement oder die Komponente wie gewohnt debuggen.</span><span class="sxs-lookup"><span data-stu-id="87613-144">You can now debug your control or component as usual.</span></span>  
  
 <span data-ttu-id="87613-145">Weitere Informationen zum Debuggen finden Sie unter [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) und [Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="87613-145">For more information about debugging, see [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) and [Walkthrough: Debugging Custom Windows Forms Controls at Design Time](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).</span></span>  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a><span data-ttu-id="87613-146">Ereignis wird im geerbten Steuerelement oder der Komponente zweimal ausgelöst</span><span class="sxs-lookup"><span data-stu-id="87613-146">Event Is Raised Twice in Inherited Control or Component</span></span>  
 <span data-ttu-id="87613-147">Dies liegt wahrscheinlich an einer doppelten `Handles`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="87613-147">This is likely due to a duplicated `Handles` clause.</span></span> <span data-ttu-id="87613-148">Weitere Informationen finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="87613-148">For more information, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a><span data-ttu-id="87613-149">Entwurfszeitfehler: „Failed to Create Component 'Component Name'“ („Fehler beim Erstellen der Komponente ‚Komponentenname‘“)</span><span class="sxs-lookup"><span data-stu-id="87613-149">Design-Time Error: "Failed to Create Component 'Component Name'"</span></span>  
 <span data-ttu-id="87613-150">Die Komponente oder das Steuerelement müssen einen Standardkonstruktor ohne Parameter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="87613-150">Your component or control must provide a default constructor with no parameters.</span></span> <span data-ttu-id="87613-151">Wenn die Entwurfsumgebung eine Instanz der Komponente oder des Steuerelements erstellt, versucht sie nicht, Parameter auf Konstruktorüberladungen bereitzustellen, die Parameter annehmen.</span><span class="sxs-lookup"><span data-stu-id="87613-151">When the design environment creates an instance of your component or control, it does not attempt to provide any parameters to constructor overloads that take parameters.</span></span>  
  
## <a name="stathreadattribute"></a><span data-ttu-id="87613-152">STAThreadAttribute</span><span class="sxs-lookup"><span data-stu-id="87613-152">STAThreadAttribute</span></span>  
 <span data-ttu-id="87613-153">Die <xref:System.STAThreadAttribute> informiert der common Language Runtime (CLR), Windows Forms das Singlethread-Apartment-Modell verwendet.</span><span class="sxs-lookup"><span data-stu-id="87613-153">The <xref:System.STAThreadAttribute> informs the common language runtime (CLR) that Windows Forms uses the single-threaded apartment model.</span></span> <span data-ttu-id="87613-154">Möglicherweise kommt es zu unbeabsichtigtem Verhalten, wenn Sie dieses Attribut nicht auf die `Main`-Methode Ihrer Windows Forms Anwendung anwenden.</span><span class="sxs-lookup"><span data-stu-id="87613-154">You may notice unintended behavior if you do not apply this attribute to your Windows Forms application's `Main` method.</span></span> <span data-ttu-id="87613-155">Z. B. Hintergrundbilder möglicherweise nicht angezeigt, für Steuerelemente wie <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="87613-155">For example, background images may not appear for controls like <xref:System.Windows.Forms.ListView>.</span></span> <span data-ttu-id="87613-156">Einige Steuerelemente benötigen dieses Attribut möglicherweise für korrektes AutoComplete- und Drag & Drop-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="87613-156">Some controls may also require this attribute for correct AutoComplete and drag-and-drop behavior.</span></span>  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a><span data-ttu-id="87613-157">Symbol „Komponente“ wird nicht in der Toolbox angezeigt</span><span class="sxs-lookup"><span data-stu-id="87613-157">Component Icon Does Not Appear in Toolbox</span></span>  
 <span data-ttu-id="87613-158">Bei Verwendung von <xref:System.Drawing.ToolboxBitmapAttribute> um ein Symbol mit der benutzerdefinierten Komponente zu verknüpfen, wird die Bitmap nicht in der Toolbox für automatisch generierte Komponenten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87613-158">When you use <xref:System.Drawing.ToolboxBitmapAttribute> to associate an icon with your custom component, the bitmap does not appear in the Toolbox for autogenerated components.</span></span> <span data-ttu-id="87613-159">Laden Sie das Steuerelement mithilfe des Dialogfelds **Toolboxelemente auswählen** neu, um die Bitmap anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="87613-159">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="87613-160">Weitere Informationen finden Sie unter [Vorgehensweise: Bereitstellen einer Toolboxbitmap für ein Steuerelement](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).</span><span class="sxs-lookup"><span data-stu-id="87613-160">For more information, see [How to: Provide a Toolbox Bitmap for a Control](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87613-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87613-161">See Also</span></span>  
 [<span data-ttu-id="87613-162">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="87613-162">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="87613-163">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="87613-163">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="87613-164">Gewusst wie: Testen des Laufzeitverhaltens eines UserControl</span><span class="sxs-lookup"><span data-stu-id="87613-164">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [<span data-ttu-id="87613-165">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="87613-165">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="87613-166">Komponentenerstellung</span><span class="sxs-lookup"><span data-stu-id="87613-166">Component Authoring</span></span>](https://msdn.microsoft.com/library/4a5a5e49-0378-4a31-83bc-24da0f1a727d)  
 [<span data-ttu-id="87613-167">Problembehandlung bei der Entwurfszeitentwicklung</span><span class="sxs-lookup"><span data-stu-id="87613-167">Troubleshooting Design-Time Development</span></span>](https://msdn.microsoft.com/library/e048d08e-fa7c-4be8-b238-4abaa199a0a6)  
 [<span data-ttu-id="87613-168">Programmieren mit Komponenten</span><span class="sxs-lookup"><span data-stu-id="87613-168">Programming with Components</span></span>](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)
