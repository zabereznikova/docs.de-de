---
title: 'Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual Basic'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 0891b64fdb26953ab90f3da931f04513ac9e8bcf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040217"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="afd30-102">Exemplarische Vorgehensweise: Vererben von einem Windows Forms-Steuerelement mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afd30-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="afd30-103">Mit Visual Basic können Sie durch *Vererbung*leistungsstarke benutzerdefinierte Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="afd30-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="afd30-104">Durch Vererbung können Sie Steuerelemente erstellen, die die gesamte Funktionalität der standardmäßigen Windows Forms-Steuerelemente, aber auch benutzerdefinierte Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="afd30-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="afd30-105">In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches geerbtes Steuerelement mit dem Namen `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="afd30-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="afd30-106">Diese Schaltfläche erbt Funktionen vom Standard Windows Forms <xref:System.Windows.Forms.Button> -Steuerelement und macht eine benutzerdefinierte Eigenschaft `ButtonValue`mit dem Namen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afd30-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="afd30-107">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="afd30-107">Creating the Project</span></span>
 <span data-ttu-id="afd30-108">Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="afd30-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="afd30-109">So erstellen Sie die „ValueButtonLib“-Steuerelementbibliothek und das „ValueButton“-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="afd30-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="afd30-110">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="afd30-110">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="afd30-111">Wählen Sie die Projektvorlage **Windows Forms-Steuerelement Bibliothek** aus der Liste der Visual Basic Projekte `ValueButtonLib` aus, und geben Sie im Feld **Name den Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="afd30-111">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>

     <span data-ttu-id="afd30-112">Der Projektname `ValueButtonLib` wird standardmäßig auch dem Stammnamespace zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="afd30-112">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="afd30-113">Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="afd30-113">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="afd30-114">Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ValueButton` bereitstellen, können Sie Ihre `ValueButton`-Komponente mithilfe von `ValueButtonLib.ValueButton` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="afd30-114">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="afd30-115">Weitere Informationen finden Sie unter [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="afd30-115">For more information, see [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span></span>

3. <span data-ttu-id="afd30-116">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **UserControl1.vb**, und wählen Sie im Kontextmenü **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="afd30-116">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="afd30-117">Ändern Sie den Dateinamen in `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="afd30-117">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="afd30-118">Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="afd30-118">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>

4. <span data-ttu-id="afd30-119">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="afd30-119">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="afd30-120">Öffnen Sie den Knoten **ValueButton.vb**, um die vom Designer generierte Codedatei **ValueButton.Designer.vb** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="afd30-120">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="afd30-121">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="afd30-121">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="afd30-122">Suchen Sie `Class` die- `Partial Public Class ValueButton`Anweisung,, und ändern Sie den Typ, von dem dieses <xref:System.Windows.Forms.UserControl> Steuer <xref:System.Windows.Forms.Button>Element erbt, von in.</span><span class="sxs-lookup"><span data-stu-id="afd30-122">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="afd30-123">Dadurch kann das geerbte Steuerelement sämtliche Funktionen des <xref:System.Windows.Forms.Button> Steuer Elements erben.</span><span class="sxs-lookup"><span data-stu-id="afd30-123">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="afd30-124">Suchen Sie `InitializeComponent` die-Methode, und entfernen Sie die <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> Zeile, die die Eigenschaft zuweist.</span><span class="sxs-lookup"><span data-stu-id="afd30-124">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="afd30-125">Diese Eigenschaft ist im <xref:System.Windows.Forms.Button> Steuerelement nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="afd30-125">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

8. <span data-ttu-id="afd30-126">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="afd30-126">From the **File** menu, choose **Save All** to save the project.</span></span>

     <span data-ttu-id="afd30-127">Beachten Sie, dass kein visueller Designer mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="afd30-127">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="afd30-128">Da das <xref:System.Windows.Forms.Button> Steuerelement seine eigene Zeichnung durchführt, können Sie seine Darstellung im Designer nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="afd30-128">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="afd30-129">Die visuelle Darstellung ist identisch mit der der Klasse, von der Sie erbt (d. h.) <xref:System.Windows.Forms.Button>, es sei denn, Sie wird im Code geändert.</span><span class="sxs-lookup"><span data-stu-id="afd30-129">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>

> [!NOTE]
>  <span data-ttu-id="afd30-130">Sie können trotzdem Komponenten, die über keine Benutzeroberflächenelemente verfügen, zur Entwurfsoberfläche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="afd30-130">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="afd30-131">Hinzufügen einer Eigenschaft zum geerbten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="afd30-131">Adding a Property to Your Inherited Control</span></span>
 <span data-ttu-id="afd30-132">Eine Verwendungsmöglichkeit von geerbten Windows Forms-Steuerelementen ist das Erstellen von Steuerelementen, die in Aussehen und Verhalten mit den standardmäßigen Windows Forms-Steuerelementen identisch sind, aber benutzerdefinierte Eigenschaften verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="afd30-132">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="afd30-133">In diesem Abschnitt fügen Sie eine Eigenschaft namens `ButtonValue` zum Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="afd30-133">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="afd30-134">So fügen Sie die Value-Eigenschaft hinzu</span><span class="sxs-lookup"><span data-stu-id="afd30-134">To add the Value property</span></span>

1. <span data-ttu-id="afd30-135">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **ValueButton.vb**, und klicken Sie im Kontextmenü auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="afd30-135">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="afd30-136">Suchen Sie die `Public Class ValueButton`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="afd30-136">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="afd30-137">Geben Sie unmittelbar unter dieser Anwendung den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="afd30-137">Immediately beneath this statement, type the following code:</span></span>

    ```vb
    ' Creates the private variable that will store the value of your
    ' property.
    Private varValue as integer
    ' Declares the property.
    Property ButtonValue() as Integer
    ' Sets the method for retrieving the value of your property.
       Get
          Return varValue
       End Get
    ' Sets the method for setting the value of your property.
       Set(ByVal Value as Integer)
          varValue = Value
       End Set
    End Property
    ```

     <span data-ttu-id="afd30-138">Dieser Code legt die Methoden fest, mit denen die Eigenschaft `ButtonValue` gespeichert und abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="afd30-138">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="afd30-139">Die `Get`-Anweisung legt den zurückgegebenen Wert auf den Wert fest, der in der privaten Variablen `varValue` gespeichert ist. Die `Set`-Anweisung legt den Wert der privaten Variablen mithilfe des Schlüsselworts `Value` fest.</span><span class="sxs-lookup"><span data-stu-id="afd30-139">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>

3. <span data-ttu-id="afd30-140">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="afd30-140">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="testing-your-control"></a><span data-ttu-id="afd30-141">Testen des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="afd30-141">Testing Your Control</span></span>
 <span data-ttu-id="afd30-142">Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="afd30-142">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="afd30-143">Sie müssen ein Testprojekt erstellen, in dem das Steuerelement getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="afd30-143">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="afd30-144">Sie müssen das Steuerelement auch für das Testprojekt zugänglich machen, indem Sie es erstellen (Kompilieren).</span><span class="sxs-lookup"><span data-stu-id="afd30-144">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="afd30-145">In diesem Abschnitt erstellen Sie das Steuerelement und testen es in einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="afd30-145">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="afd30-146">So erstellen Sie das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="afd30-146">To build your control</span></span>

1. <span data-ttu-id="afd30-147">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="afd30-147">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="afd30-148">Der Build sollte ohne Compilerfehler oder Warnungen erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="afd30-148">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="afd30-149">So Erstellen Sie ein Testprojekt</span><span class="sxs-lookup"><span data-stu-id="afd30-149">To create a test project</span></span>

1. <span data-ttu-id="afd30-150">Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="afd30-150">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="afd30-151">Wählen Sie den Knoten Visual Basic Projekte aus, und klicken Sie auf **Windows Forms Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="afd30-151">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="afd30-152">Geben Sie im Feld **Name** `Test`ein.</span><span class="sxs-lookup"><span data-stu-id="afd30-152">In the **Name** box, type `Test`.</span></span>

4. <span data-ttu-id="afd30-153">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="afd30-153">In **Solution Explorer**, click the **Show All Files** button.</span></span>

5. <span data-ttu-id="afd30-154">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für Ihr Testprojekt, und wählen Sie dann im Kontextmenü **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="afd30-154">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

6. <span data-ttu-id="afd30-155">Klicken Sie auf die Registerkarte **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="afd30-155">Click the **Projects** tab.</span></span>

7. <span data-ttu-id="afd30-156">Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="afd30-156">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="afd30-157">Ihr `ValueButtonLib`-Projekt wird unter **Projektname** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="afd30-157">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="afd30-158">Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="afd30-158">Double-click the project to add the reference to the test project.</span></span>

8. <span data-ttu-id="afd30-159">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test,** , und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="afd30-159">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="afd30-160">So fügen Sie dem Formular ein Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="afd30-160">To add your control to the form</span></span>

1. <span data-ttu-id="afd30-161">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Form1.vb**, und wählen Sie im Kontextmenü **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="afd30-161">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="afd30-162">Klicken Sie in der **Toolbox** auf **ValueButtonLib Components**.</span><span class="sxs-lookup"><span data-stu-id="afd30-162">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="afd30-163">Doppelklicken Sie auf **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="afd30-163">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="afd30-164">Ein **ValueButton** wird im Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afd30-164">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="afd30-165">Klicken Sie mit der rechten Maustaste auf **ValueButton**, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="afd30-165">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="afd30-166">Untersuchen Sie im Fenster **Eigenschaften** die Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="afd30-166">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="afd30-167">Beachten Sie, dass sie mit den Eigenschaften identisch sind, die von einer Standardschaltfläche verfügbar gemacht werden, außer es besteht eine zusätzliche Eigenschaft `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="afd30-167">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>

5. <span data-ttu-id="afd30-168">Legen Sie die `ButtonValue` -Eigenschaft auf `5`fest.</span><span class="sxs-lookup"><span data-stu-id="afd30-168">Set the `ButtonValue` property to `5`.</span></span>

6. <span data-ttu-id="afd30-169">Doppelklicken Sie auf der Registerkarte **alle Windows Forms** der **Toolbox**auf **Bezeichnung** , um dem <xref:System.Windows.Forms.Label> Formular ein Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="afd30-169">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="afd30-170">Verschieben Sie die Bezeichnung in die Mitte des Formulars.</span><span class="sxs-lookup"><span data-stu-id="afd30-170">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="afd30-171">Doppelklicken Sie auf `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="afd30-171">Double-click `ValueButton1`.</span></span>

     <span data-ttu-id="afd30-172">Der **Code-Editor** wird im Ereignis `ValueButton1_Click` geöffnet.</span><span class="sxs-lookup"><span data-stu-id="afd30-172">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>

9. <span data-ttu-id="afd30-173">Geben Sie die folgende Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="afd30-173">Type the following line of code.</span></span>

    ```vb
    Label1.Text = CStr(ValueButton1.ButtonValue)
    ```

10. <span data-ttu-id="afd30-174">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie im Kontextmenü **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="afd30-174">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="afd30-175">Wählen Sie im Menü **Debuggen** die Option **Debugging starten**.</span><span class="sxs-lookup"><span data-stu-id="afd30-175">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="afd30-176">`Form1` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="afd30-176">`Form1` appears.</span></span>

12. <span data-ttu-id="afd30-177">Klicken Sie auf `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="afd30-177">Click `Valuebutton1`.</span></span>

     <span data-ttu-id="afd30-178">Die Zahl '5' wird in `Label1` angezeigt und zeigt, dass die Eigenschaft `ButtonValue` Ihres geerbten Steuerelements mit der Methode `ValueButton1_Click` an `Label1` weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="afd30-178">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="afd30-179">Daher erbt Ihr `ValueButton`-Steuerelement die gesamte Funktionalität der standardmäßigen Windows Forms-Schaltfläche und macht eine zusätzliche benutzerdefinierte Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="afd30-179">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="afd30-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afd30-180">See also</span></span>

- [<span data-ttu-id="afd30-181">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuer Elements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="afd30-181">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="afd30-182">Vorgehensweise: Anzeigen eines Steuer Elements im Dialog Feld "Toolbox Elemente auswählen"</span><span class="sxs-lookup"><span data-stu-id="afd30-182">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="afd30-183">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="afd30-183">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="afd30-184">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afd30-184">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
