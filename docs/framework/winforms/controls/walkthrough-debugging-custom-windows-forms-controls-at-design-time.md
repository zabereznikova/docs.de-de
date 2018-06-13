---
title: 'Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: b87c46b2182884f90b427498b9af696d14acac96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542037"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="fd2f7-102">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="fd2f7-103">Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, werden häufig finden Sie es zum Debuggen des Verhaltens zur Entwurfszeit.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="fd2f7-104">Dies gilt vor allem, wenn Sie einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="fd2f7-105">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass akzeptiert Vorteil von Visual Studio zur Entwurfszeit-Funktionen](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="fd2f7-106">Sie können Ihre benutzerdefinierten Steuerelemente, die mit Visual Studio debuggen, wie andere .NET Framework-Klassen Debuggen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="fd2f7-107">Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen möchten, die das benutzerdefinierte Steuerelement Code ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="fd2f7-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="fd2f7-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fd2f7-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="fd2f7-109">Erstellen eines Windows Forms-Projekts zum Hosten des benutzerdefinierten Steuerelements</span><span class="sxs-lookup"><span data-stu-id="fd2f7-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="fd2f7-110">Erstellen eines Projekts für eine Bibliothek</span><span class="sxs-lookup"><span data-stu-id="fd2f7-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="fd2f7-111">Hinzufügen einer Eigenschaft, um das benutzerdefinierte Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fd2f7-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="fd2f7-112">Das benutzerdefinierte Steuerelement hinzufügen dem Formular host</span><span class="sxs-lookup"><span data-stu-id="fd2f7-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="fd2f7-113">Einrichten des Projekts zum Debuggen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="fd2f7-114">Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="fd2f7-115">Wenn Sie fertig sind, müssen Sie einen Überblick über die Aufgaben zum Debuggen der Entwurfszeitverhalten eines benutzerdefinierten Steuerelements erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd2f7-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fd2f7-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fd2f7-118">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="fd2f7-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="fd2f7-119">Creating the Project</span></span>  
 <span data-ttu-id="fd2f7-120">Der erste Schritt besteht darin das Anwendungsprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-120">The first step is to create the application project.</span></span> <span data-ttu-id="fd2f7-121">Verwenden Sie dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="fd2f7-122">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="fd2f7-122">To create the project</span></span>  
  
-   <span data-ttu-id="fd2f7-123">Erstellen Sie ein Windows-Anwendungsprojekt mit dem Namen "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="fd2f7-123">Create a Windows Application project called "DebuggingExample".</span></span> <span data-ttu-id="fd2f7-124">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project (Vorgehensweise: Erstellen eines neuen Windows Forms-Anwendungsprojekts)](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-124">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="fd2f7-125">Erstellen eines Projekts für eine Bibliothek</span><span class="sxs-lookup"><span data-stu-id="fd2f7-125">Creating a Control Library Project</span></span>  
 <span data-ttu-id="fd2f7-126">Der nächste Schritt ist zur-Steuerelementbibliothek-Projekt erstellen und richten Sie das benutzerdefinierte Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-126">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="fd2f7-127">-Steuerelementbibliothek-Projekt erstellen</span><span class="sxs-lookup"><span data-stu-id="fd2f7-127">To create the control library project</span></span>  
  
1.  <span data-ttu-id="fd2f7-128">Hinzufügen einer **Windows-Steuerelementbibliothek** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-128">Add a **Windows Control Library** project to the solution.</span></span>  
  
2.  <span data-ttu-id="fd2f7-129">Fügen Sie einen neuen **UserControl** dem DebugControlLibrary-Projekt.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-129">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="fd2f7-130">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen neuer Projektelemente](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-130">For details, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/library/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span> <span data-ttu-id="fd2f7-131">Benennen Sie die neue Quelldatei Basis von "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="fd2f7-131">Give the new source file a base name of "DebugControl".</span></span>  
  
3.  <span data-ttu-id="fd2f7-132">Mithilfe der **Projektmappen-Explorer**, Standardsteuerelement für das Projekt löschen, indem Sie die Codedatei mit dem Basisnamen der löschen "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="fd2f7-132">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="fd2f7-133">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: entfernen, löschen und Ausschließen von Elementen](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-133">For details, see [NIB:How to: Remove, Delete, and Exclude Items](http://msdn.microsoft.com/library/6dffdc86-29c8-4eff-bcd8-e3a0dd9e9a73).</span></span>  
  
4.  <span data-ttu-id="fd2f7-134">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-134">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="fd2f7-135">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="fd2f7-135">Checkpoint</span></span>  
 <span data-ttu-id="fd2f7-136">Sehen Sie das benutzerdefinierte Steuerelement im an diesem Punkt werden die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-136">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="fd2f7-137">Um den Status zu überprüfen</span><span class="sxs-lookup"><span data-stu-id="fd2f7-137">To check your progress</span></span>  
  
-   <span data-ttu-id="fd2f7-138">Suchen Sie die neue Registerkarte **DebugControlLibrary Komponenten** , und klicken Sie hier, um ihn auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-138">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="fd2f7-139">Wenn sie geöffnet wird, sehen Sie das Steuerelement als aufgeführt **DebugControl** mit dem Standardsymbol daneben.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-139">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="fd2f7-140">Hinzufügen einer Eigenschaft, um das benutzerdefinierte Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fd2f7-140">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="fd2f7-141">Um zu zeigen, dass Ihr Code des benutzerdefinierten Steuerelements zur Entwurfszeit ausgeführt wird, Sie fügen eine Eigenschaft hinzu und legen Sie einen Haltepunkt im Code, der die Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-141">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="fd2f7-142">Das benutzerdefinierte Steuerelement eine Eigenschaft hinzu</span><span class="sxs-lookup"><span data-stu-id="fd2f7-142">To add a property to your custom control</span></span>  
  
1.  <span data-ttu-id="fd2f7-143">Open **DebugControl** in der **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-143">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="fd2f7-144">Fügen Sie der Klassendefinition den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fd2f7-144">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2.  <span data-ttu-id="fd2f7-145">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-145">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="fd2f7-146">Das benutzerdefinierte Steuerelement hinzufügen dem Formular Host</span><span class="sxs-lookup"><span data-stu-id="fd2f7-146">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="fd2f7-147">Um das Entwurfszeitverhalten des benutzerdefinierten Steuerelements zu debuggen, geben Sie eine Instanz der Klasse des benutzerdefinierten Steuerelements auf einem Hostformular an.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-147">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="fd2f7-148">Das benutzerdefinierte Steuerelement dem Formular Host hinzufügen</span><span class="sxs-lookup"><span data-stu-id="fd2f7-148">To add your custom control to the host form</span></span>  
  
1.  <span data-ttu-id="fd2f7-149">Öffnen Sie im Projekt "DebuggingExample" Form1 in der **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-149">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="fd2f7-150">In der **Toolbox**öffnen die **DebugControlLibrary Komponenten** Registerkarte, und ziehen Sie eine **DebugControl** Instanz auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-150">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3.  <span data-ttu-id="fd2f7-151">Suchen der `DemoString` benutzerdefinierte Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-151">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="fd2f7-152">Beachten Sie, dass Sie den Wert ändern können, wie Sie eine andere Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-152">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="fd2f7-153">Beachten Sie außerdem, dass bei der `DemoString` Eigenschaft aktiviert ist, die Eigenschaft Beschreibungszeichenfolge angezeigt wird, am unteren Rand der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-153">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="fd2f7-154">Einrichten des Projekts zum Debuggen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-154">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="fd2f7-155">Um das benutzerdefinierte Steuerelement Entwurfszeitverhalten zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die das benutzerdefinierte Steuerelement Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-155">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="fd2f7-156">So richten Sie das Projekt zum Debuggen zur Entwurfszeit ein</span><span class="sxs-lookup"><span data-stu-id="fd2f7-156">To set up the project for design-time debugging</span></span>  
  
1.  <span data-ttu-id="fd2f7-157">Mit der rechten Maustaste auf die **DebugControlLibrary** -Projekt in der **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-157">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="fd2f7-158">In der **DebugControlLibrary** Eigenschaftenblatt, wählen die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-158">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="fd2f7-159">In der **Startaktion** Abschnitt **externes Programm starten**.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-159">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="fd2f7-160">Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![von VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche, um für die Visual Studio-IDE zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-160">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="fd2f7-161">Der Name der ausführbaren Datei ist **devenv.exe**, und wenn Sie am Standardspeicherort installiert haben, lautet %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-161">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3.  <span data-ttu-id="fd2f7-162">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-162">Click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="fd2f7-163">Mit der rechten Maustaste die **DebugControlLibrary** Projekt, und wählen Sie **als Startprojekt festlegen** um diese Konfiguration für Remotedebugging zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-163">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="fd2f7-164">Debuggen des benutzerdefinierten Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-164">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="fd2f7-165">Jetzt können Sie Ihr benutzerdefinierte Steuerelement zu debuggen, wie er im Entwurfsmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-165">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="fd2f7-166">Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt werden, und verwenden Sie es zum Laden der Projektmappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="fd2f7-166">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="fd2f7-167">Beim Öffnen Sie Form1 in der **Forms-Designer**, eine Instanz eines benutzerdefinierten Steuerelements erstellt und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-167">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="fd2f7-168">So debuggen Sie das benutzerdefinierte Steuerelement zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="fd2f7-168">To debug your custom control at design time</span></span>  
  
1.  <span data-ttu-id="fd2f7-169">Öffnen der **DebugControl** -Quelldatei in die **Code-Editor** und fügen Sie einen Haltepunkt auf der `Set` Accessor, der die `DemoString` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-169">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2.  <span data-ttu-id="fd2f7-170">Drücken Sie F5, um die Debugsitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-170">Press F5 to start the debugging session.</span></span> <span data-ttu-id="fd2f7-171">Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-171">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="fd2f7-172">Sie können zwischen den Instanzen auf zwei Arten unterschieden:</span><span class="sxs-lookup"><span data-stu-id="fd2f7-172">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="fd2f7-173">Die debugging-Instanz hat das Wort **ausführen** in der Titelleiste</span><span class="sxs-lookup"><span data-stu-id="fd2f7-173">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="fd2f7-174">Die debugging-Instanz hat die **starten** Schaltfläche auf seine **Debuggen** Symbolleiste deaktiviert</span><span class="sxs-lookup"><span data-stu-id="fd2f7-174">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="fd2f7-175">Der Haltepunkt wird in der debugging-Instanz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-175">Your breakpoint is set in the debugging instance.</span></span>  
  
3.  <span data-ttu-id="fd2f7-176">Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="fd2f7-176">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="fd2f7-177">Sie können auswählen, um die Projektmappe leicht zu finden **zuletzt geöffnete Projekte** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-177">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="fd2f7-178">Die Projektmappendatei "DebuggingExample.sln" werden die zuletzt verwendeten Datei aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-178">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4.  <span data-ttu-id="fd2f7-179">Öffnen Sie Form1 in der **Forms-Designer** , und wählen Sie die **DebugControl** Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-179">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5.  <span data-ttu-id="fd2f7-180">Ändern Sie den Wert, der die `DemoString` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-180">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="fd2f7-181">Beachten Sie, dass wenn Sie die Änderung zu bestätigen, das Debuggen Instanz von Visual Studio den Fokus erhält, und die Ausführung am Haltepunkt hält.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-181">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="fd2f7-182">Können Sie Schritt für Schritt durch den Eigenschaftenaccessor ebenso wie die anderen Code würde.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-182">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6.  <span data-ttu-id="fd2f7-183">Wenn Sie mit der Debugsitzung fertig sind, können Sie beenden, schließen die gehostete Instanz von Visual Studio oder durch Klicken auf die **Beenden des Debuggens** Schaltfläche in der debugging-Instanz.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-183">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd2f7-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fd2f7-184">Next Steps</span></span>  
 <span data-ttu-id="fd2f7-185">Nun, dass Sie der benutzerdefinierten Steuerelemente zur Entwurfszeit Debuggen können, gibt es viele Möglichkeiten für die Erweiterung des Steuerelements Interaktion mit der Visual Studio-IDE.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-185">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="fd2f7-186">Können Sie die <xref:System.ComponentModel.Component.DesignMode%2A> Eigenschaft von der <xref:System.ComponentModel.Component> Klasse zum Schreiben von Code, der nur zur Entwurfszeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-186">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="fd2f7-187">Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-187">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="fd2f7-188">Es sind mehrere Attribute können Sie auf die Eigenschaften des Steuerelements zum Bearbeiten des benutzerdefinierten Steuerelements Interaktion mit dem Designer anwenden.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-188">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="fd2f7-189">Sie finden diese Attribute in der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-189">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="fd2f7-190">Sie können einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement schreiben.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-190">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="fd2f7-191">Dies bietet Ihnen die vollständige Kontrolle über die entwurfsumgebung, die über die erweiterbare Designer-Infrastruktur, die von Visual Studio verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="fd2f7-191">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="fd2f7-192">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen einer Windows Forms-Steuerelement, dass akzeptiert Vorteil von Visual Studio zur Entwurfszeit-Funktionen](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="fd2f7-192">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2f7-193">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd2f7-193">See Also</span></span>  
 [<span data-ttu-id="fd2f7-194">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt</span><span class="sxs-lookup"><span data-stu-id="fd2f7-194">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 [<span data-ttu-id="fd2f7-195">Vorgehensweise: Zugriff auf Entwurfszeitdienste</span><span class="sxs-lookup"><span data-stu-id="fd2f7-195">How to: Access Design-Time Services</span></span>](http://msdn.microsoft.com/library/c186c4b6-076c-438d-9ed3-f13da29c8c1f)  
 [<span data-ttu-id="fd2f7-196">Vorgehensweise: Zugriff auf Entwurfszeitunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fd2f7-196">How to: Access Design-Time Support in Windows Forms</span></span>](http://msdn.microsoft.com/library/a84f8579-1f47-41b9-ba37-69030b0aff09)
