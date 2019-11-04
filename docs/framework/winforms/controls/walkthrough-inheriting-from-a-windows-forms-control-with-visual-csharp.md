---
title: 'Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual C#'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c54733a340b1855b3fc7b90ff2b5178fad8c5303
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460595"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="5ab67-102">Exemplarische Vorgehensweise: Erben von einem Windows Forms-Steuerelement mit C\#</span><span class="sxs-lookup"><span data-stu-id="5ab67-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="5ab67-103">Mit Visual C#können Sie durch *Vererbung*leistungsstarke benutzerdefinierte Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-103">With Visual C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="5ab67-104">Durch Vererbung können Sie Steuerelemente erstellen, die die gesamte Funktionalität der standardmäßigen Windows Forms-Steuerelemente, aber auch benutzerdefinierte Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5ab67-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="5ab67-105">In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches geerbtes Steuerelement mit dem Namen `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="5ab67-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="5ab67-106">Diese Schaltfläche erbt Funktionen von der Standard Windows Forms <xref:System.Windows.Forms.Button>-Steuerelement und macht eine benutzerdefinierte Eigenschaft mit dem Namen `ButtonValue`verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5ab67-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="5ab67-107">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="5ab67-107">Create the Project</span></span>

<span data-ttu-id="5ab67-108">Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="5ab67-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="5ab67-109">So erstellen Sie die „ValueButtonLib“-Steuerelementbibliothek und das „ValueButton“-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ab67-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="5ab67-110">Erstellen Sie in Visual Studio ein neues **Windows Forms-Steuerelement Bibliothek** -Projekt, und nennen Sie es **ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="5ab67-111">Der Projektname `ValueButtonLib` wird standardmäßig auch dem Stammnamespace zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="5ab67-112">Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ab67-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="5ab67-113">Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ValueButton` bereitstellen, können Sie Ihre `ValueButton`-Komponente mithilfe von `ValueButtonLib.ValueButton` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="5ab67-114">Weitere Informationen finden Sie unter [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="5ab67-114">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>

2. <span data-ttu-id="5ab67-115">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **UserControl1.cs**, und wählen Sie im Kontextmenü **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="5ab67-116">Ändern Sie den Dateinamen in **ValueButton.cs**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="5ab67-117">Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement `UserControl1` umbenannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="5ab67-118">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **ValueButton.cs**, und wählen Sie **Code anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="5ab67-119">Suchen Sie die `class` Anweisungs Zeile, `public partial class ValueButton`, und ändern Sie den Typ, von dem dieses Steuerelement erbt, von <xref:System.Windows.Forms.UserControl> in <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="5ab67-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="5ab67-120">Dadurch kann das geerbte Steuerelement die gesamte Funktionalität des <xref:System.Windows.Forms.Button> Steuer Elements erben.</span><span class="sxs-lookup"><span data-stu-id="5ab67-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="5ab67-121">Öffnen Sie im **Projektmappen-Explorer** den Knoten **ValueButton.cs**, um die vom Designer generierte Codedatei **ValueButton.Designer.cs** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="5ab67-122">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="5ab67-123">Suchen Sie die `InitializeComponent` Methode, und entfernen Sie die Zeile, die die <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>-Eigenschaft zuweist.</span><span class="sxs-lookup"><span data-stu-id="5ab67-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="5ab67-124">Diese Eigenschaft ist im <xref:System.Windows.Forms.Button> Steuerelement nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5ab67-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="5ab67-125">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5ab67-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ab67-126">Ein visueller Designer ist nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5ab67-126">A visual designer is no longer available.</span></span> <span data-ttu-id="5ab67-127">Da das <xref:System.Windows.Forms.Button> Steuerelement seine eigene Zeichnung durchführt, können Sie seine Darstellung im Designer nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="5ab67-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="5ab67-128">Die visuelle Darstellung ist identisch mit der der Klasse, von der Sie erbt (d. h. <xref:System.Windows.Forms.Button>), sofern Sie nicht im Code geändert wird.</span><span class="sxs-lookup"><span data-stu-id="5ab67-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="5ab67-129">Sie können trotzdem Komponenten, die über keine Benutzeroberflächenelemente verfügen, zur Entwurfsoberfläche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="5ab67-130">Hinzufügen einer Eigenschaft zu einem geerbten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ab67-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="5ab67-131">Eine Verwendungsmöglichkeit von geerbten Windows Forms-Steuerelementen ist das Erstellen von Steuerelementen, die in Aussehen und Verhalten mit den standardmäßigen Windows Forms-Steuerelementen identisch sind, aber benutzerdefinierte Eigenschaften verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="5ab67-132">In diesem Abschnitt fügen Sie eine Eigenschaft namens `ButtonValue` zum Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="5ab67-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="5ab67-133">So fügen Sie die Value-Eigenschaft hinzu</span><span class="sxs-lookup"><span data-stu-id="5ab67-133">To add the Value property</span></span>

1. <span data-ttu-id="5ab67-134">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **ValueButton.cs**, und klicken Sie im Kontextmenü auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="5ab67-135">Suchen Sie die `class`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5ab67-135">Locate the `class` statement.</span></span> <span data-ttu-id="5ab67-136">Geben Sie direkt nach `{` den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="5ab67-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="5ab67-137">Dieser Code legt die Methoden fest, mit denen die Eigenschaft `ButtonValue` gespeichert und abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5ab67-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="5ab67-138">Die `get`-Anweisung legt den zurückgegebenen Wert auf den Wert fest, der in der privaten Variablen `varValue` gespeichert ist. Die `set`-Anweisung legt den Wert der privaten Variablen mithilfe des Schlüsselworts `value` fest.</span><span class="sxs-lookup"><span data-stu-id="5ab67-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="5ab67-139">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5ab67-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="5ab67-140">Testen des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="5ab67-140">Test the control</span></span>

<span data-ttu-id="5ab67-141">Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="5ab67-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="5ab67-142">Sie müssen ein Testprojekt erstellen, in dem das Steuerelement getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ab67-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="5ab67-143">Sie müssen das Steuerelement auch für das Testprojekt zugänglich machen, indem Sie es erstellen (Kompilieren).</span><span class="sxs-lookup"><span data-stu-id="5ab67-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="5ab67-144">In diesem Abschnitt erstellen Sie das Steuerelement und testen es in einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="5ab67-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="5ab67-145">So erstellen Sie das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5ab67-145">To build your control</span></span>

<span data-ttu-id="5ab67-146">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="5ab67-147">Der Build sollte ohne Compilerfehler oder Warnungen erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="5ab67-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="5ab67-148">So Erstellen Sie ein Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5ab67-148">To create a test project</span></span>

1. <span data-ttu-id="5ab67-149">Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="5ab67-150">Wählen Sie den Knoten **Windows** unter dem Knoten **Visual C#-** aus, und klicken Sie auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="5ab67-151">Geben Sie im Feld **Name den Namen** **Test**ein.</span><span class="sxs-lookup"><span data-stu-id="5ab67-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="5ab67-152">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für Ihr Testprojekt, und wählen Sie dann im Kontextmenü **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="5ab67-153">Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="5ab67-154">Ihr ValueButtonLib-Projekt wird unter **Projekt Name**aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5ab67-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="5ab67-155">Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="5ab67-156">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test,** , und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="5ab67-157">So fügen Sie dem Formular ein Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="5ab67-157">To add your control to the form</span></span>

1. <span data-ttu-id="5ab67-158">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Form1.cs**, und wählen Sie im Kontextmenü **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="5ab67-159">Wählen Sie in der **Toolbox**die Option **ValueButtonLib Components**aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="5ab67-160">Doppelklicken Sie auf **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="5ab67-161">Ein **ValueButton** wird im Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ab67-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="5ab67-162">Klicken Sie mit der rechten Maustaste auf **ValueButton**, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="5ab67-163">Untersuchen Sie im Fenster **Eigenschaften** die Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="5ab67-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="5ab67-164">Beachten Sie, dass Sie mit den Eigenschaften identisch sind, die von einer Standard Schaltfläche verfügbar gemacht werden, außer dass es eine zusätzliche Eigenschaft, ButtonValue, gibt.</span><span class="sxs-lookup"><span data-stu-id="5ab67-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="5ab67-165">Legen Sie die Eigenschaft **ButtonValue** auf **5**fest.</span><span class="sxs-lookup"><span data-stu-id="5ab67-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="5ab67-166">Doppelklicken Sie auf der Registerkarte **alle Windows Forms** der **Toolbox**auf **Bezeichnung** , um dem Formular ein <xref:System.Windows.Forms.Label>-Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ab67-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="5ab67-167">Verschieben Sie die Bezeichnung in die Mitte des Formulars.</span><span class="sxs-lookup"><span data-stu-id="5ab67-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="5ab67-168">Doppelklicken Sie auf `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="5ab67-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="5ab67-169">Der **Code-Editor** wird im Ereignis `valueButton1_Click` geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5ab67-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="5ab67-170">Fügen Sie die folgende Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="5ab67-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="5ab67-171">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie im Kontextmenü **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ab67-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="5ab67-172">Wählen Sie im Menü **Debuggen** die Option **Debugging starten**.</span><span class="sxs-lookup"><span data-stu-id="5ab67-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="5ab67-173">`Form1` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ab67-173">`Form1` appears.</span></span>

12. <span data-ttu-id="5ab67-174">Klicken Sie auf `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="5ab67-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="5ab67-175">Die Zahl '5' wird in `label1` angezeigt und zeigt, dass die Eigenschaft `ButtonValue` Ihres geerbten Steuerelements mit der Methode `valueButton1_Click` an `label1` weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5ab67-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="5ab67-176">Daher erbt Ihr `ValueButton`-Steuerelement die gesamte Funktionalität der standardmäßigen Windows Forms-Schaltfläche und macht eine zusätzliche benutzerdefinierte Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5ab67-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ab67-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ab67-177">See also</span></span>

- [<span data-ttu-id="5ab67-178">Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“</span><span class="sxs-lookup"><span data-stu-id="5ab67-178">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="5ab67-179">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual C#</span><span class="sxs-lookup"><span data-stu-id="5ab67-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
