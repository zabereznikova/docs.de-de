---
title: 'Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#'
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c1d9be77550b1255a24120c68f20d25640e0ebdf
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460630"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="7356c-102">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit C-\#</span><span class="sxs-lookup"><span data-stu-id="7356c-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="7356c-103">Zusammengesetzte Steuerelemente bieten eine Möglichkeit, mit der benutzerdefinierte grafische Schnittstellen erstellt und wiederverwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7356c-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="7356c-104">Ein zusammengesetztes Steuerelement ist im wesentlichen eine Komponente mit visueller Darstellung.</span><span class="sxs-lookup"><span data-stu-id="7356c-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="7356c-105">Daher können zusammengesetzte Steuerelemente aus einem oder mehr Windows Forms-Steuerelementen, Komponenten oder Codeblöcken bestehen. Diese erweitern die Funktionalität durch Validieren von Benutzereingaben, verändern Anzeigeeigenschaften oder führen andere vom Autor gewünschte Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="7356c-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="7356c-106">Zusammengesetzte Steuerelemente können genau wie andere Steuerelemente in Windows Forms platziert werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="7356c-107">Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement namens `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="7356c-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="7356c-108">Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="7356c-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="7356c-109">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="7356c-109">Create the Project</span></span>

<span data-ttu-id="7356c-110">Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="7356c-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="7356c-111">So erstellen Sie die ctlClockLib-Steuerelementbibliothek und das ctlClock-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="7356c-112">Erstellen Sie in Visual Studio ein neues **Windows Forms-Steuerelement Bibliothek** -Projekt, und nennen Sie es **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="7356c-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="7356c-113">Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7356c-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="7356c-114">Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="7356c-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="7356c-115">Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ctlClock` bereitstellen, können Sie Ihre `ctlClock`-Komponente mithilfe von `ctlClockLib.ctlClock.` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7356c-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="7356c-116">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **UserControl1.cs**, und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="7356c-117">Ändern Sie den Dateinamen in `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="7356c-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="7356c-118">Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7356c-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="7356c-119">Standardmäßig erbt ein zusammengesetztes Steuerelement von der <xref:System.Windows.Forms.UserControl> Klasse, die vom System bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="7356c-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="7356c-120">Die <xref:System.Windows.Forms.UserControl>-Klasse stellt die von allen zusammengesetzten Steuerelementen benötigte Funktionalität bereit und implementiert Standardmethoden und-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7356c-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="7356c-121">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7356c-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="7356c-122">Hinzufügen von Windows-Steuerelementen und Komponenten zum zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="7356c-123">Eine visuelle Schnittstelle ist ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="7356c-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="7356c-124">Diese visuelle Schnittstelle wird durch das Hinzufügen eines oder mehrerer Windows-Steuerelemente zur Designeroberfläche implementiert.</span><span class="sxs-lookup"><span data-stu-id="7356c-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="7356c-125">Im folgenden Beispiel integrieren Sie Windows-Steuerelemente in das zusammengesetzte Steuerelement und schreiben Code, um Funktionalität zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="7356c-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="7356c-126">So fügen Sie eine Bezeichnung und einen Timer zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="7356c-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="7356c-127">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClock.cs**, und klicken Sie dann auf **Designer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="7356c-128">Erweitern Sie in der **Toolbox** den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie dann auf **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="7356c-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="7356c-129">Ein <xref:System.Windows.Forms.Label>-Steuerelement mit dem Namen `label1` wird dem Steuerelement auf der Designer Oberfläche hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7356c-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="7356c-130">Klicken Sie im Designer auf **label1**.</span><span class="sxs-lookup"><span data-stu-id="7356c-130">In the designer, click **label1**.</span></span> <span data-ttu-id="7356c-131">Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="7356c-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="7356c-132">property</span><span class="sxs-lookup"><span data-stu-id="7356c-132">Property</span></span>|<span data-ttu-id="7356c-133">Ändern in</span><span class="sxs-lookup"><span data-stu-id="7356c-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="7356c-134">**Name**</span><span class="sxs-lookup"><span data-stu-id="7356c-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="7356c-135">**Text**</span><span class="sxs-lookup"><span data-stu-id="7356c-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="7356c-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="7356c-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="7356c-137">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="7356c-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="7356c-138">Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.</span><span class="sxs-lookup"><span data-stu-id="7356c-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="7356c-139">Da eine <xref:System.Windows.Forms.Timer> eine Komponente ist, hat Sie zur Laufzeit keine visuelle Darstellung.</span><span class="sxs-lookup"><span data-stu-id="7356c-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="7356c-140">Er wird daher nicht bei den Steuerelementen auf der Designeroberfläche angezeigt, sondern im **Komponenten-Designer** (eine Taskleiste am unteren Ende der Designeroberfläche).</span><span class="sxs-lookup"><span data-stu-id="7356c-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="7356c-141">Klicken Sie im **Komponenten-Designer**auf **Timer1**, und legen Sie dann die Eigenschaft <xref:System.Windows.Forms.Timer.Interval%2A> auf `1000` und die Eigenschaft <xref:System.Windows.Forms.Timer.Enabled%2A> auf `true`fest.</span><span class="sxs-lookup"><span data-stu-id="7356c-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="7356c-142">Die <xref:System.Windows.Forms.Timer.Interval%2A>-Eigenschaft steuert die Häufigkeit, mit der die <xref:System.Windows.Forms.Timer> Komponente Ticks.</span><span class="sxs-lookup"><span data-stu-id="7356c-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="7356c-143">Bei jedem Tick von `timer1` führt sie den Code im Ereignis `timer1_Tick` aus.</span><span class="sxs-lookup"><span data-stu-id="7356c-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="7356c-144">Das Intervall stellt die Anzahl von Millisekunden zwischen Ticks dar.</span><span class="sxs-lookup"><span data-stu-id="7356c-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="7356c-145">Doppelklicken Sie im **Komponenten-Designer** auf **timer1**, um zum `timer1_Tick`-Ereignis für `ctlClock` zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="7356c-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="7356c-146">Ändern Sie den Code so, dass er folgendem Codebeispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7356c-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="7356c-147">Achten Sie darauf, den Zugriffsmodifizierer von `private` in `protected` zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7356c-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="7356c-148">Durch diesen Code wird die aktuelle Zeit in `lblDisplay` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7356c-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="7356c-149">Da das Intervall von `timer1` auf `1000` festgelegt wurde, wird dieses Ereignis alle tausend Millisekunden ausgelöst. Dadurch wird die aktuelle Zeit jede Sekunde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7356c-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="7356c-150">Ändern Sie die Methode so, dass sie mit dem Schlüsselwort `virtual` überschreibbar ist.</span><span class="sxs-lookup"><span data-stu-id="7356c-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="7356c-151">Weitere Informationen finden Sie im Abschnitt „Erben von Benutzersteuerelementen“.</span><span class="sxs-lookup"><span data-stu-id="7356c-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="7356c-152">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7356c-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="7356c-153">Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="7356c-154">Das Clock-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label>-Steuerelement und eine <xref:System.Windows.Forms.Timer>-Komponente, die jeweils über einen eigenen Satz inhärenter Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="7356c-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="7356c-155">Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, können Sie benutzerdefinierte Eigenschaften durch Schreiben der geeigneten Codeblöcke erstellen und verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="7356c-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="7356c-156">Im folgenden Vorgang fügen Sie Eigenschaften zum Steuerelement hinzu, die dem Benutzer ermöglichen, die Farbe des Hintergrunds und des Texts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7356c-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="7356c-157">So fügen Sie eine Eigenschaft zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="7356c-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="7356c-158">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClock.cs**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="7356c-159">Der **Code-Editor** für das Steuerelement wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7356c-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="7356c-160">Suchen Sie die `public partial class ctlClock`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7356c-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="7356c-161">Geben Sie unter der öffnenden Klammer (`{)` den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="7356c-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="7356c-162">Diese Anweisungen erstellen die privaten Variablen, die Sie verwenden, um die Werte für die Eigenschaften zu speichern, die Sie gleich erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="7356c-163">Geben oder fügen Sie den folgenden Code unter den Variablen Deklarationen aus Schritt 2 ein.</span><span class="sxs-lookup"><span data-stu-id="7356c-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="7356c-164">Dieser Code stellt nachfolgenden Benutzern dieses Steuerelements zwei benutzerdefinierte Eigenschaften zur Verfügung, `ClockForeColor` und `ClockBackColor`.</span><span class="sxs-lookup"><span data-stu-id="7356c-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="7356c-165">Die Anweisungen `get` und `set` ermöglichen das Speichern und Abrufen des Eigenschaftswerts sowie des Codes zum Implementieren der geeigneten Funktionalität der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7356c-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="7356c-166">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7356c-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="7356c-167">Testen des Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="7356c-167">Test the Control</span></span>

<span data-ttu-id="7356c-168">Steuerelemente sind keine eigenständigen Anwendungen. Sie müssen in einem Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="7356c-169">Testen Sie das Laufzeitverhalten Ihres Steuerelements, und überprüfen Sie die Eigenschaften im **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="7356c-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="7356c-170">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="7356c-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="7356c-171">So testen Sie das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-171">To test your control</span></span>

1. <span data-ttu-id="7356c-172">Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.</span><span class="sxs-lookup"><span data-stu-id="7356c-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="7356c-173">Suchen Sie im Eigenschaftenraster des Testcontainers die Eigenschaft `ClockBackColor`, und wählen Sie anschließend die Eigenschaft aus, um die Farbpalette anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7356c-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="7356c-174">Wählen Sie eine Farbe aus, indem sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="7356c-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="7356c-175">Die Hintergrundfarbe des Steuerelements ändert sich in die ausgewählte Farbe.</span><span class="sxs-lookup"><span data-stu-id="7356c-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="7356c-176">Verwenden Sie eine ähnliche Abfolge von Ereignissen, um zu überprüfen, ob die Eigenschaft `ClockForeColor` funktioniert wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="7356c-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="7356c-177">In diesem Abschnitt und in den vorherigen Abschnitten haben Sie gesehen, wie Komponenten und Windows-Steuerelemente mit Code und Paketen kombiniert werden können, um benutzerdefinierte Funktionalität in Form eines zusammengesetzten Steuerelements zu bieten.</span><span class="sxs-lookup"><span data-stu-id="7356c-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="7356c-178">Sie haben gelernt, Eigenschaften in Ihrem zusammengesetzten Steuerelement verfügbar zu machen, und das Steuerelement nach Abschluss zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7356c-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="7356c-179">Im nächsten Abschnitt erfahren Sie, wie man ein vererbtes zusammengesetztes Steuerelement mithilfe von `ctlClock` als Basis verwendet.</span><span class="sxs-lookup"><span data-stu-id="7356c-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="7356c-180">Von einem zusammengesetzten Steuerelement erben</span><span class="sxs-lookup"><span data-stu-id="7356c-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="7356c-181">In den vorherigen Abschnitten haben Sie gelernt, wie man Windows-Steuerelemente, Komponenten und Code in wiederverwendbare zusammengesetzte Steuerelemente kombiniert.</span><span class="sxs-lookup"><span data-stu-id="7356c-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="7356c-182">Das zusammengesetzte Steuerelement kann jetzt als Basis für die Erstellung anderer Steuerelemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="7356c-183">Der Vorgang, bei dem eine Klasse von einer Basisklasse abgeleitet wird, nennt man *Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="7356c-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="7356c-184">In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement namens `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="7356c-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="7356c-185">Dieses Steuerelement wird von seinem übergeordneten Steuerelement, `ctlClock`, abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7356c-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="7356c-186">Sie erfahren, wie Sie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitern können.</span><span class="sxs-lookup"><span data-stu-id="7356c-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="7356c-187">Der erste Schritt beim Erstellen eines geerbten Steuerelements ist das Ableiten vom übergeordneten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7356c-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="7356c-188">Diese Aktion erstellt ein neues Steuerelement, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, aber auch als Basis für das Hinzufügen neuer oder veränderter Funktionalität dienen kann.</span><span class="sxs-lookup"><span data-stu-id="7356c-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="7356c-189">So erstellen Sie das geerbte Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-189">To create the inherited control</span></span>

1. <span data-ttu-id="7356c-190">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie dann auf **Benutzer Steuer**Element.</span><span class="sxs-lookup"><span data-stu-id="7356c-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="7356c-191">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7356c-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="7356c-192">Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement**.</span><span class="sxs-lookup"><span data-stu-id="7356c-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="7356c-193">Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.cs` ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="7356c-194">Das Dialogfeld **Vererbungsauswahl** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7356c-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="7356c-195">Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="7356c-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="7356c-196">Navigieren Sie in **Projektmappen-Explorer**zu den aktuellen Projekten.</span><span class="sxs-lookup"><span data-stu-id="7356c-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7356c-197">Eine Datei namens **ctlAlarmClock.cs** wurde zum aktuellen Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7356c-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="7356c-198">Die Alarm Eigenschaften hinzufügen</span><span class="sxs-lookup"><span data-stu-id="7356c-198">Add the Alarm Properties</span></span>

<span data-ttu-id="7356c-199">Eigenschaften werden auf die gleiche Weise zu einem geerbten Steuerelement hinzugefügt wie zu einem zusammengesetzten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7356c-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="7356c-200">Sie verwenden jetzt die Syntax zum Deklarieren von Eigenschaften, um zwei Eigenschaften zu Ihrem Steuerelement hinzuzufügen: `AlarmTime`, wodurch der Wert des Datums und der Uhrzeit gespeichert wird, zu der der Wecker klingelt, und `AlarmSet`, die anzeigt, ob der Wecker eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7356c-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="7356c-201">So fügen Sie Eigenschaften zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="7356c-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="7356c-202">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="7356c-203">Suchen Sie die `public class`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7356c-203">Locate the `public class` statement.</span></span> <span data-ttu-id="7356c-204">Beachten Sie, dass das Steuerelement von `ctlClockLib.ctlClock` erbt.</span><span class="sxs-lookup"><span data-stu-id="7356c-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="7356c-205">Geben Sie unter der öffnenden Klammer (`{)`-Anweisung den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="7356c-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="7356c-206">Zur grafischen Oberfläche des Steuer Elements hinzufügen</span><span class="sxs-lookup"><span data-stu-id="7356c-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="7356c-207">Das geerbte Steuerelement verfügt über eine visuelle Schnittstelle, die mit dem Steuerelement identisch ist, von dem es erbt.</span><span class="sxs-lookup"><span data-stu-id="7356c-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="7356c-208">Es verfügt über die gleichen konstituierenden Steuerelemente wie das übergeordnete Steuerelement. Allerdings sind die Eigenschaften der konstituierenden Steuerelemente nicht verfügbar, solange sie nicht explizit verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="7356c-209">Sie können zur grafischen Schnittstelle des geerbten zusammengesetzten Steuerelements auf die gleiche Weise hinzufügen, wie Sie zu jedem anderen zusammengesetzten Steuerelement hinzufügen würden.</span><span class="sxs-lookup"><span data-stu-id="7356c-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="7356c-210">Um den Vorgang fortzusetzen, zur visuellen Schnittstelle Ihres Weckers hinzuzufügen, fügen Sie ein Label-Steuerelement hinzu, das leuchtet, wenn der Wecker klingelt.</span><span class="sxs-lookup"><span data-stu-id="7356c-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="7356c-211">So fügen Sie das Label-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="7356c-211">To add the label control</span></span>

1. <span data-ttu-id="7356c-212">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Designer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="7356c-213">Der Designer für `ctlAlarmClock` wird im Hauptfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7356c-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="7356c-214">Klicken Sie auf den Anzeigebereich des Steuerelements, und zeigen Sie das Eigenschaftenfenster an.</span><span class="sxs-lookup"><span data-stu-id="7356c-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7356c-215">Alle Eigenschaften werden angezeigt, sind aber abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="7356c-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="7356c-216">Das bedeutet, dass die Eigenschaften nativ zu `lblDisplay` sind, und dass sie nicht im Eigenschaftenfenster geändert oder auf sie zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="7356c-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="7356c-217">Standardmäßig sind in einem zusammengesetzten Steuerelement enthaltene Steuerelemente `private`, und es ist nicht möglich, auf ihre Eigenschaften zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7356c-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7356c-218">Wenn Sie möchten, dass nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf interne Steuerelemente haben, deklarieren Sie sie als `public` oder `protected`.</span><span class="sxs-lookup"><span data-stu-id="7356c-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="7356c-219">Dadurch können Sie Eigenschaften von Steuerelementen, die in Ihrem zusammengesetzten Steuerelement enthalten sind, festlegen und ändern, indem Sie den entsprechenden Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="7356c-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="7356c-220">Fügen Sie dem zusammengesetzten Steuerelement ein <xref:System.Windows.Forms.Label>-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="7356c-221">Ziehen Sie das <xref:System.Windows.Forms.Label>-Steuerelement mit der Maus direkt unterhalb des Anzeige Felds.</span><span class="sxs-lookup"><span data-stu-id="7356c-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="7356c-222">Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="7356c-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="7356c-223">property</span><span class="sxs-lookup"><span data-stu-id="7356c-223">Property</span></span>|<span data-ttu-id="7356c-224">Einstellung</span><span class="sxs-lookup"><span data-stu-id="7356c-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="7356c-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="7356c-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="7356c-226">**Text**</span><span class="sxs-lookup"><span data-stu-id="7356c-226">**Text**</span></span>|<span data-ttu-id="7356c-227">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="7356c-227">**Alarm!**</span></span>|
    |<span data-ttu-id="7356c-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="7356c-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="7356c-229">**Visible**</span><span class="sxs-lookup"><span data-stu-id="7356c-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="7356c-230">Hinzufügen der Wecker-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="7356c-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="7356c-231">In den vorherigen Schritten haben Sie Eigenschaften und ein Steuerelement hinzugefügt, dass die Wecker-Funktionalität in Ihrem zusammengesetzten Steuerelement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="7356c-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="7356c-232">In diesem Verfahren fügen Sie Code hinzu, um die aktuelle Zeit mit der Weckzeit zu vergleichen, und bei Gleichheit einen Wecker auszulösen.</span><span class="sxs-lookup"><span data-stu-id="7356c-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="7356c-233">Durch Überschreiben der Methode `timer1_Tick` von `ctlClock` und Hinzufügen von zusätzlichem Code erweitern Sie die Funktion von `ctlAlarmClock`, während alle geerbten Funktionen von `ctlClock` erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="7356c-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="7356c-234">So überschreiben Sie die Methode „Timer1_Tick“ von „ctlClock“</span><span class="sxs-lookup"><span data-stu-id="7356c-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="7356c-235">Suchen Sie im **Code-Editor** eine `private bool blnAlarmSet;`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="7356c-236">Fügen Sie direkt darunter die folgende Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="7356c-237">Suchen Sie im **Code-Editor** die schließende Klammer (`})` am Ende der Klasse.</span><span class="sxs-lookup"><span data-stu-id="7356c-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="7356c-238">Fügen Sie direkt vor der Klammer den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="7356c-239">Das Hinzufügen dieses Codes dient mehreren Zwecken.</span><span class="sxs-lookup"><span data-stu-id="7356c-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="7356c-240">Die Anweisung `override` weist das Steuerelement an, diese Methode statt der Methode zu verwenden, die vom Basissteuerelement geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="7356c-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="7356c-241">Wenn diese Methode aufgerufen wird, ruft sie durch Aufruf der `base.timer1_Tick`-Anweisung die überschriebene Methode auf. Damit wird sichergestellt, dass die gesamte Funktionalität, die im ursprünglichen Steuerelement enthalten ist, in diesem Steuerelement reproduziert wird.</span><span class="sxs-lookup"><span data-stu-id="7356c-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="7356c-242">Anschließend ruft sie zusätzlichen Code auf, um die Wecker-Funktionalität zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="7356c-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="7356c-243">Ein blinkendes Label-Steuerelement erscheint, wenn der Wecker ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="7356c-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="7356c-244">Das Wecker-Steuerelement ist fast abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7356c-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="7356c-245">Sie müssen nur noch eine Möglichkeit zum Deaktivieren implementieren.</span><span class="sxs-lookup"><span data-stu-id="7356c-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="7356c-246">Zu diesem Zweck fügen Sie Code zur Methode `lblAlarm_Click` hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="7356c-247">So implementieren Sie die Methode zum Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="7356c-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="7356c-248">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlAlarmClock.cs**, und klicken Sie dann auf **Designer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="7356c-249">Der Designer wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7356c-249">The designer opens.</span></span>

2. <span data-ttu-id="7356c-250">Fügen Sie eine Schaltfläche zum Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="7356c-250">Add a button to the control.</span></span> <span data-ttu-id="7356c-251">Legen Sie die Eigenschaften der Schaltfläche wie folgt fest.</span><span class="sxs-lookup"><span data-stu-id="7356c-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="7356c-252">property</span><span class="sxs-lookup"><span data-stu-id="7356c-252">Property</span></span>|<span data-ttu-id="7356c-253">Wert</span><span class="sxs-lookup"><span data-stu-id="7356c-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="7356c-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="7356c-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="7356c-255">**Text**</span><span class="sxs-lookup"><span data-stu-id="7356c-255">**Text**</span></span>|<span data-ttu-id="7356c-256">**Wecker deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="7356c-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="7356c-257">Doppelklicken Sie im Designer auf **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="7356c-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="7356c-258">Der **Code-Editor** wird in der Zeile `private void btnAlarmOff_Click` geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7356c-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="7356c-259">Ändern Sie die Methode so, dass sie folgendem Code ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7356c-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="7356c-260">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="7356c-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="7356c-261">Verwenden des geerbten Steuer Elements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="7356c-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="7356c-262">Sie können das geerbte Steuerelement auf die gleiche Weise testen wie das Basisklassen-Steuerelement, `ctlClock`: Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.</span><span class="sxs-lookup"><span data-stu-id="7356c-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="7356c-263">Weitere Informationen finden Sie unter [Vorgehensweise: Testen des Laufzeitverhaltens eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="7356c-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="7356c-264">Sie müssen das Steuerelement auf einem Formular hosten, um es verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="7356c-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="7356c-265">Wie standardmäßige zusammengesetzten Steuerelemente kann ein geerbtes zusammengesetztes Steuerelement nicht alleine stehen und muss in einem Formular oder einem anderen Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="7356c-266">Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, wird zusätzlicher Code für das Testen benötigt.</span><span class="sxs-lookup"><span data-stu-id="7356c-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="7356c-267">In dieser Vorgehensweise schreiben Sie ein einfaches Programm, um die Funktionalität von `ctlAlarmClock` zu testen.</span><span class="sxs-lookup"><span data-stu-id="7356c-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="7356c-268">Sie schreiben Code zum Einstellen und Anzeigen der Eigenschaft `AlarmTime` von `ctlAlarmClock` und testen die geerbten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7356c-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="7356c-269">So erstellen Sie ein Steuerelement und fügen es zu einem Testformular hinzu</span><span class="sxs-lookup"><span data-stu-id="7356c-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="7356c-270">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **ctlClockLib**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="7356c-271">Fügen Sie der Projekt Mappe ein neues **Windows-Anwendungs** Projekt hinzu, und nennen Sie es " **Test**".</span><span class="sxs-lookup"><span data-stu-id="7356c-271">Add a new **Windows Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="7356c-272">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Knoten **Verweise** für das Testprojekt.</span><span class="sxs-lookup"><span data-stu-id="7356c-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="7356c-273">Klicken Sie auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7356c-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="7356c-274">Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="7356c-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="7356c-275">Ihr `ctlClockLib`-Projekt wird unter **Projektname** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7356c-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="7356c-276">Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7356c-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="7356c-277">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="7356c-278">Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.</span><span class="sxs-lookup"><span data-stu-id="7356c-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="7356c-279">Doppelklicken Sie auf **ctlAlarmClock**, um eine Kopie von `ctlAlarmClock` zu Ihrem Formular hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="7356c-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="7356c-280">Suchen Sie in der **Toolbox**nach **DateTimePicker** , und doppelklicken Sie darauf, um dem Formular ein <xref:System.Windows.Forms.DateTimePicker>-Steuerelement hinzuzufügen, und fügen Sie dann ein <xref:System.Windows.Forms.Label> Steuerelement hinzu, indem Sie auf **Bezeichnung**doppelklicken.</span><span class="sxs-lookup"><span data-stu-id="7356c-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="7356c-281">Verwenden Sie die Maus, um das Steuerelement an einem geeigneten Ort auf dem Formular zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="7356c-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="7356c-282">Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.</span><span class="sxs-lookup"><span data-stu-id="7356c-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="7356c-283">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7356c-283">Control</span></span>|<span data-ttu-id="7356c-284">property</span><span class="sxs-lookup"><span data-stu-id="7356c-284">Property</span></span>|<span data-ttu-id="7356c-285">Wert</span><span class="sxs-lookup"><span data-stu-id="7356c-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="7356c-286">**Text**</span><span class="sxs-lookup"><span data-stu-id="7356c-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="7356c-287">**Name**</span><span class="sxs-lookup"><span data-stu-id="7356c-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="7356c-288">**Name**</span><span class="sxs-lookup"><span data-stu-id="7356c-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="7356c-289">**Format**</span><span class="sxs-lookup"><span data-stu-id="7356c-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="7356c-290">Doppelklicken Sie im Designer auf **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="7356c-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="7356c-291">Der **Code-Editor** für `private void dtpTest_ValueChanged` wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7356c-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="7356c-292">Ändern Sie den Code so, dass er folgendem Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="7356c-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="7356c-293">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="7356c-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="7356c-294">Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="7356c-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="7356c-295">Das Testprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="7356c-295">The test program starts.</span></span> <span data-ttu-id="7356c-296">Beachten Sie, dass die aktuelle Uhrzeit im `ctlAlarmClock`-Steuerelement aktualisiert wird und die Startzeit im <xref:System.Windows.Forms.DateTimePicker> Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7356c-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="7356c-297">Klicken Sie auf die <xref:System.Windows.Forms.DateTimePicker>, in der die Minuten der Stunde angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7356c-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="7356c-298">Legen Sie mithilfe der Tastatur einen Wert für die Minuten fest, der eine Minute höher ist als die aktuell von `ctlAlarmClock` angezeigte Zeit.</span><span class="sxs-lookup"><span data-stu-id="7356c-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="7356c-299">Die Zeit für die Einstellung des Weckers wird in `lblTest` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7356c-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="7356c-300">Warten Sie, bis die angezeigte Zeit die für den Wecker eingestellte Zeit erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="7356c-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="7356c-301">Wenn die angezeigte Zeit die Zeit erreicht, auf die der Wecker eingestellt ist, leuchtet `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="7356c-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="7356c-302">Deaktivieren Sie den Wecker, indem Sie auf `btnAlarmOff` klicken.</span><span class="sxs-lookup"><span data-stu-id="7356c-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="7356c-303">Sie können den Wecker nun zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="7356c-303">You may now reset the alarm.</span></span>

<span data-ttu-id="7356c-304">In diesem Artikel wurde eine Reihe wichtiger Konzepte behandelt.</span><span class="sxs-lookup"><span data-stu-id="7356c-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="7356c-305">Sie haben gelernt, ein zusammengesetztes Steuerelement zu erstellen, indem Sie Steuerelemente und Komponenten in einem Container für zusammengesetzte Steuerelemente kombiniert haben.</span><span class="sxs-lookup"><span data-stu-id="7356c-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="7356c-306">Sie haben gelernt, Eigenschaften zu Ihrem Steuerelement hinzuzufügen und Code für das Implementieren benutzerdefinierter Funktionalität zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="7356c-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="7356c-307">Im letzten Abschnitt haben Sie gelernt, die Funktionalität eines bestimmten zusammengesetzten Steuerelements durch Vererbung zu erweitern und die Funktionalität von Host-Methoden durch außer Kraft setzen dieser Methoden zu ändern.</span><span class="sxs-lookup"><span data-stu-id="7356c-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="7356c-308">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7356c-308">See also</span></span>

- [<span data-ttu-id="7356c-309">Arten von benutzerdefinierten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="7356c-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="7356c-310">Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“</span><span class="sxs-lookup"><span data-stu-id="7356c-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="7356c-311">Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="7356c-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
