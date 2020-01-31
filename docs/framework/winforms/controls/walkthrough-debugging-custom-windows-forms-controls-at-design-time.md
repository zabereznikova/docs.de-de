---
title: Debuggen benutzerdefinierter Steuerelemente zur Entwurfszeit
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740188"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="a5be6-102">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="a5be6-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="a5be6-103">Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, ist es häufig erforderlich, das Entwurfszeit Verhalten zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="a5be6-104">Dies trifft vor allem dann zu, wenn Sie einen benutzerdefinierten Designer für Ihr benutzerdefiniertes Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="a5be6-105">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md)nutzt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="a5be6-106">Sie können Ihre benutzerdefinierten Steuerelemente mithilfe von Visual Studio debuggen, genauso wie Sie alle anderen .NET Framework Klassen debuggen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="a5be6-107">Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen, in der der Code des benutzerdefinierten Steuer Elements ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5be6-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="a5be6-108">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="a5be6-108">Create the project</span></span>

<span data-ttu-id="a5be6-109">Im ersten Schritt erstellen Sie das Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-109">The first step is to create the application project.</span></span> <span data-ttu-id="a5be6-110">Sie verwenden dieses Projekt, um die Anwendung zu erstellen, die das benutzerdefinierte Steuerelement hostet.</span><span class="sxs-lookup"><span data-stu-id="a5be6-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="a5be6-111">Erstellen Sie in Visual Studio ein Windows-Anwendungsprojekt, und nennen Sie es **DebuggingExample**.</span><span class="sxs-lookup"><span data-stu-id="a5be6-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="a5be6-112">Erstellen des Steuerelement Bibliothek-Projekts</span><span class="sxs-lookup"><span data-stu-id="a5be6-112">Create the control library project</span></span>

1. <span data-ttu-id="a5be6-113">Fügen Sie der Projekt Mappe ein **Windows-Steuerelement Bibliothek** -Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="a5be6-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="a5be6-114">Fügen Sie dem Projekt "Debug Controller" ein neues **UserControl** -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="a5be6-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="a5be6-115">Nennen Sie es "Debug **Control**".</span><span class="sxs-lookup"><span data-stu-id="a5be6-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="a5be6-116">Löschen Sie in **Projektmappen-Explorer**das Standard Steuerelement des Projekts, indem Sie die Codedatei mit dem Basisnamen UserControl1 löschen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="a5be6-117">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="a5be6-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="a5be6-118">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="a5be6-118">Checkpoint</span></span>

<span data-ttu-id="a5be6-119">An diesem Punkt können Sie Ihr benutzerdefiniertes Steuerelement in der **Toolbox**sehen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="a5be6-120">Um den Fortschritt zu überprüfen, suchen Sie die neue Registerkarte **DebugControlLibrary Components** , und klicken Sie, um Sie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="a5be6-121">Beim Öffnen wird das Steuerelement als "Debug **Control** " mit dem Standard Symbol neben diesem angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="a5be6-122">Hinzufügen einer Eigenschaft zu einem benutzerdefinierten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a5be6-122">Add a property to your custom control</span></span>

<span data-ttu-id="a5be6-123">Um zu veranschaulichen, dass der Code des benutzerdefinierten Steuer Elements zur Entwurfszeit ausgeführt wird, fügen Sie eine Eigenschaft hinzu, und legen Sie einen Breakpoint im Code fest, der die Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="a5be6-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="a5be6-124">Öffnen Sie **DebugControl** im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="a5be6-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="a5be6-125">Fügen Sie der Klassendefinition folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="a5be6-125">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="a5be6-126">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="a5be6-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="a5be6-127">Hinzufügen des benutzerdefinierten Steuer Elements zum Host Formular</span><span class="sxs-lookup"><span data-stu-id="a5be6-127">Add your custom control to the host form</span></span>

<span data-ttu-id="a5be6-128">Um das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements zu debuggen, platzieren Sie eine Instanz der benutzerdefinierten Steuerelement Klasse auf einem Host Formular.</span><span class="sxs-lookup"><span data-stu-id="a5be6-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="a5be6-129">Öffnen Sie im Projekt "DebuggingExample" Form1 im **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="a5be6-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="a5be6-130">Öffnen Sie in der **Toolbox**die Registerkarte **DebugControlLibrary Components** , und ziehen Sie eine **DebugControl** -Instanz auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="a5be6-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="a5be6-131">Suchen Sie im **Eigenschaften** Fenster die Eigenschaft `DemoString` Benutzer definiert.</span><span class="sxs-lookup"><span data-stu-id="a5be6-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="a5be6-132">Beachten Sie, dass Sie den Wert wie jede andere Eigenschaft ändern können.</span><span class="sxs-lookup"><span data-stu-id="a5be6-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="a5be6-133">Beachten Sie auch, dass die Beschreibungs Zeichenfolge der Eigenschaft im unteren Bereich des Fensters **Eigenschaften** angezeigt wird, wenn die `DemoString`-Eigenschaft ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="a5be6-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="a5be6-134">Einrichten des Projekts für das Debuggen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="a5be6-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="a5be6-135">Um das Entwurfszeit Verhalten des benutzerdefinierten Steuer Elements zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die den Code des benutzerdefinierten Steuer Elements ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="a5be6-136">Klicken Sie mit **Projektmappen-Explorer** der rechten Maustaste auf das Projekt Projekt Debug **Controller** , und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="a5be6-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="a5be6-137">Wählen **Sie im Eigenschaften** Blatt **DebugControlLibrary die Registerkarte Debuggen** aus.</span><span class="sxs-lookup"><span data-stu-id="a5be6-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="a5be6-138">Wählen Sie im Abschnitt **Start Aktion** die Option **externes Programm starten**aus.</span><span class="sxs-lookup"><span data-stu-id="a5be6-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="a5be6-139">Sie Debuggen eine separate Instanz von Visual Studio, und klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (![der Schaltfläche mit den Auslassungs Punkten (...) in der Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)), um nach der Visual Studio-IDE zu suchen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="a5be6-140">Der Name der ausführbaren Datei lautet " **devenv. exe".** Wenn Sie am Standard Speicherort installiert haben, lautet der Pfad *% Program Files (x86)% \ Microsoft Visual studio\2019\\\<Edition > \Common7\IDE*.</span><span class="sxs-lookup"><span data-stu-id="a5be6-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="a5be6-141">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="a5be6-142">Klicken Sie mit der rechten Maustaste auf das Projekt **DebugControlLibrary** , und wählen Sie **als Startprojekt festlegen** , um diese Debugkonfiguration zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5be6-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="a5be6-143">Debuggen des benutzerdefinierten Steuer Elements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="a5be6-143">Debug your custom control at design time</span></span>

<span data-ttu-id="a5be6-144">Nun können Sie das benutzerdefinierte Steuerelement Debuggen, während es im Entwurfs Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5be6-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="a5be6-145">Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt, und Sie verwenden Sie zum Laden der Projekt Mappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="a5be6-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="a5be6-146">Wenn Sie Form1 im Forms- **Designer**öffnen, wird eine Instanz des benutzerdefinierten Steuer Elements erstellt, und die Ausführung wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="a5be6-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="a5be6-147">Öffnen Sie die **DebugControl** -Quelldatei im **Code-Editor** , und platzieren Sie einen Haltepunkt für den `Set`-Accessor der `DemoString`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a5be6-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="a5be6-148">Drücken Sie **F5** , um die Debugsitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="a5be6-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="a5be6-149">Es wird eine neue Instanz von Visual Studio erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="a5be6-150">Es gibt zwei Möglichkeiten, um zwischen den Instanzen zu unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="a5be6-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="a5be6-151">In der debugginginstanz wird das Wort in der Titelleiste **ausgeführt** .</span><span class="sxs-lookup"><span data-stu-id="a5be6-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="a5be6-152">Die debugginginstanz hat die Schaltfläche **Start** auf der debugsymbolleiste</span><span class="sxs-lookup"><span data-stu-id="a5be6-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="a5be6-153">Der Breakpoint wird in der debugginginstanz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="a5be6-154">Öffnen Sie in der neuen Instanz von Visual Studio die Projekt Mappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="a5be6-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="a5be6-155">Sie können die Lösung problemlos finden, indem Sie im Menü **Datei** die Option **zuletzt verwendete Projekte** auswählen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="a5be6-156">Die Projektmappendatei "DebuggingExample. sln" wird als zuletzt verwendete Datei aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="a5be6-157">Öffnen Sie Form1 im **Forms-Designer** , und wählen Sie das Steuerelement Debug **Control** aus.</span><span class="sxs-lookup"><span data-stu-id="a5be6-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="a5be6-158">Ändern Sie den Wert der `DemoString` -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a5be6-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="a5be6-159">Wenn Sie die Änderung ausführen, erhält die debugginginstanz von Visual Studio den Fokus, und die Ausführung wird am Haltepunkt angehalten.</span><span class="sxs-lookup"><span data-stu-id="a5be6-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="a5be6-160">Sie können den Eigenschafts Accessor genau so wie jeden anderen Code in Einzelschritten durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a5be6-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="a5be6-161">Zum Beenden des Debuggens beenden Sie die gehostete Instanz von Visual Studio, oder wählen Sie in der debugginstanz die Schaltfläche **Debugging beenden**</span><span class="sxs-lookup"><span data-stu-id="a5be6-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a5be6-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a5be6-162">Next steps</span></span>

<span data-ttu-id="a5be6-163">Nachdem Sie Ihre benutzerdefinierten Steuerelemente zur Entwurfszeit debuggen können, gibt es viele Möglichkeiten, die Interaktion Ihres Steuer Elements mit der Visual Studio-IDE zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="a5be6-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="a5be6-164">Sie können die <xref:System.ComponentModel.Component.DesignMode%2A>-Eigenschaft der <xref:System.ComponentModel.Component>-Klasse verwenden, um Code zu schreiben, der nur zur Entwurfszeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a5be6-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="a5be6-165">Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="a5be6-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="a5be6-166">Es gibt mehrere Attribute, die Sie auf die Eigenschaften des Steuer Elements anwenden können, um die Interaktion des benutzerdefinierten Steuer Elements mit dem Designer zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a5be6-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="a5be6-167">Diese Attribute finden Sie im <xref:System.ComponentModel?displayProperty=nameWithType>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a5be6-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="a5be6-168">Sie können einen benutzerdefinierten Designer für Ihr benutzerdefiniertes Steuerelement schreiben.</span><span class="sxs-lookup"><span data-stu-id="a5be6-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="a5be6-169">Dadurch erhalten Sie die komplette Kontrolle über die Entwurfs Möglichkeiten mithilfe der erweiterbaren Designer Infrastruktur, die von Visual Studio verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="a5be6-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="a5be6-170">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen](creating-a-wf-control-design-time-features.md)nutzt.</span><span class="sxs-lookup"><span data-stu-id="a5be6-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a5be6-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5be6-171">See also</span></span>

- [<span data-ttu-id="a5be6-172">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktion nutzt</span><span class="sxs-lookup"><span data-stu-id="a5be6-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
