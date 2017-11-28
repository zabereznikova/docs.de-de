---
title: "Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0625695933b776b8cdbe5488adc116723b930dd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="ccd14-102">Exemplarische Vorgehensweise: Vererben eines Windows Forms-Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccd14-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="ccd14-103">Mit [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] können Sie leistungsstarke benutzerdefinierte Steuerelemente durch *Vererbung* erstellen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-103">With [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="ccd14-104">Durch Vererbung können Sie Steuerelemente erstellen, die die gesamte Funktionalität der standardmäßigen Windows Forms-Steuerelemente, aber auch benutzerdefinierte Funktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ccd14-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="ccd14-105">In dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches geerbtes Steuerelement mit dem Namen `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="ccd14-106">Diese Schaltfläche erbt die Funktionalität der standardmäßigen Windows Forms <xref:System.Windows.Forms.Button> steuern und macht eine benutzerdefinierte Eigenschaft mit dem Namen `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccd14-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ccd14-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ccd14-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ccd14-109">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ccd14-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ccd14-110">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ccd14-110">Creating the Project</span></span>  
 <span data-ttu-id="ccd14-111">Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="ccd14-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="ccd14-112">So erstellen Sie die „ValueButtonLib“-Steuerelementbibliothek und das „ValueButton“-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ccd14-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="ccd14-113">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ccd14-114">Wählen Sie aus der Liste der [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]-Projekte die Projektvorlage **Windows Forms**-Steuerelementbibliothek aus, und geben Sie im Feld **Name** `ValueButtonLib` ein.</span><span class="sxs-lookup"><span data-stu-id="ccd14-114">Select the **Windows Forms Control Library** project template from the list of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="ccd14-115">Der Projektname `ValueButtonLib` wird standardmäßig auch dem Stammnamespace zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="ccd14-116">Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="ccd14-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="ccd14-117">Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ValueButton` bereitstellen, können Sie Ihre `ValueButton`-Komponente mithilfe von `ValueButtonLib.ValueButton` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="ccd14-118">Weitere Informationen finden Sie unter [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="ccd14-118">For more information, see [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
3.  <span data-ttu-id="ccd14-119">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **UserControl1.vb**, und wählen Sie im Kontextmenü **Umbenennen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd14-119">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="ccd14-120">Ändern Sie den Dateinamen in `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-120">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="ccd14-121">Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-121">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>  
  
4.  <span data-ttu-id="ccd14-122">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-122">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="ccd14-123">Öffnen Sie den Knoten **ValueButton.vb**, um die vom Designer generierte Codedatei **ValueButton.Designer.vb** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-123">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="ccd14-124">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-124">Open this file in the **Code Editor**.</span></span>  
  
6.  <span data-ttu-id="ccd14-125">Suchen Sie die `Class` -Anweisung `Partial Public Class ValueButton`, und ändern Sie den Typ, von dem dieses Steuerelement von erbt <xref:System.Windows.Forms.UserControl> auf <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="ccd14-125">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="ccd14-126">Dadurch können Ihre geerbte Steuerelement erben die Funktionalität von der <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ccd14-126">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
7.  <span data-ttu-id="ccd14-127">Suchen Sie die `InitializeComponent` -Methode, und entfernen Sie die Zeile, die weist die <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ccd14-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="ccd14-128">Diese Eigenschaft ist nicht vorhanden, der <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ccd14-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="ccd14-129">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ccd14-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
     <span data-ttu-id="ccd14-130">Beachten Sie, dass kein visueller Designer mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ccd14-130">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="ccd14-131">Da die <xref:System.Windows.Forms.Button> Steuerelement bewirkt einen eigenen zeichnen, müssen Sie seine Darstellung im Designer nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="ccd14-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="ccd14-132">Die visuelle Darstellung wird genau, der sie erbt Klasse identisch sein (d. h. <xref:System.Windows.Forms.Button>), wenn im Code geändert.</span><span class="sxs-lookup"><span data-stu-id="ccd14-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ccd14-133">Sie können trotzdem Komponenten, die über keine Benutzeroberflächenelemente verfügen, zur Entwurfsoberfläche hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="ccd14-134">Hinzufügen einer Eigenschaft zum geerbten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ccd14-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="ccd14-135">Eine Verwendungsmöglichkeit von geerbten Windows Forms-Steuerelementen ist das Erstellen von Steuerelementen, die in Aussehen und Verhalten mit den standardmäßigen Windows Forms-Steuerelementen identisch sind, aber benutzerdefinierte Eigenschaften verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="ccd14-136">In diesem Abschnitt fügen Sie eine Eigenschaft namens `ButtonValue` zum Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="ccd14-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="ccd14-137">So fügen Sie die Value-Eigenschaft hinzu</span><span class="sxs-lookup"><span data-stu-id="ccd14-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="ccd14-138">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **ValueButton.vb**, und klicken Sie im Kontextmenü auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-138">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ccd14-139">Suchen Sie die `Public Class ValueButton`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ccd14-139">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="ccd14-140">Geben Sie unmittelbar unter dieser Anwendung den folgenden Code ein:</span><span class="sxs-lookup"><span data-stu-id="ccd14-140">Immediately beneath this statement, type the following code:</span></span>  
  
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
  
     <span data-ttu-id="ccd14-141">Dieser Code legt die Methoden fest, mit denen die Eigenschaft `ButtonValue` gespeichert und abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ccd14-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="ccd14-142">Die `Get`-Anweisung legt den zurückgegebenen Wert auf den Wert fest, der in der privaten Variablen `varValue` gespeichert ist. Die `Set`-Anweisung legt den Wert der privaten Variablen mithilfe des Schlüsselworts `Value` fest.</span><span class="sxs-lookup"><span data-stu-id="ccd14-142">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>  
  
3.  <span data-ttu-id="ccd14-143">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ccd14-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="ccd14-144">Testen des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="ccd14-144">Testing Your Control</span></span>  
 <span data-ttu-id="ccd14-145">Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ccd14-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="ccd14-146">Sie müssen ein Testprojekt erstellen, in dem das Steuerelement getestet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ccd14-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="ccd14-147">Sie müssen das Steuerelement auch für das Testprojekt zugänglich machen, indem Sie es erstellen (Kompilieren).</span><span class="sxs-lookup"><span data-stu-id="ccd14-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="ccd14-148">In diesem Abschnitt erstellen Sie das Steuerelement und testen es in einem Windows Form.</span><span class="sxs-lookup"><span data-stu-id="ccd14-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="ccd14-149">So erstellen Sie das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ccd14-149">To build your control</span></span>  
  
1.  <span data-ttu-id="ccd14-150">Klicken Sie im Menü **Erstellen** auf **Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="ccd14-151">Der Build sollte ohne Compilerfehler oder Warnungen erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="ccd14-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="ccd14-152">So Erstellen Sie ein Testprojekt</span><span class="sxs-lookup"><span data-stu-id="ccd14-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="ccd14-153">Zeigen Sie im Menü **Datei** mit der Maus auf **Hinzufügen**, und klicken Sie dann auf **Neues Projekt**, um das Dialogfeld **Neues Projekt hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="ccd14-154">Wählen Sie den Projektknoten [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] aus, und klicken Sie auf **Windows Forms-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-154">Select the [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] projects node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="ccd14-155">Geben Sie im Feld **Name** `Test`ein.</span><span class="sxs-lookup"><span data-stu-id="ccd14-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="ccd14-156">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-156">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="ccd14-157">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Knoten **Verweise** für Ihr Testprojekt, und wählen Sie dann im Kontextmenü **Verweis hinzufügen** aus, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-157">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="ccd14-158">Klicken Sie auf die Registerkarte **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-158">Click the **Projects** tab.</span></span>  
  
7.  <span data-ttu-id="ccd14-159">Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-159">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="ccd14-160">Ihr `ValueButtonLib`-Projekt wird unter **Projektname** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ccd14-160">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="ccd14-161">Doppelklicken Sie auf das Projekt, um den Verweis auf das Testprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ccd14-161">Double-click the project to add the reference to the test project.</span></span>  
  
8.  <span data-ttu-id="ccd14-162">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test,**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd14-162">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="ccd14-163">So fügen Sie dem Formular ein Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="ccd14-163">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="ccd14-164">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Form1.vb**, und wählen Sie im Kontextmenü **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd14-164">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="ccd14-165">Klicken Sie in der **Toolbox** auf **ValueButtonLib Components**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-165">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="ccd14-166">Doppelklicken Sie auf **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-166">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="ccd14-167">Ein **ValueButton** wird im Formular angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccd14-167">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="ccd14-168">Klicken Sie mit der rechten Maustaste auf **ValueButton**, und wählen Sie im Kontextmenü **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd14-168">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="ccd14-169">Untersuchen Sie im Fenster **Eigenschaften** die Eigenschaften dieses Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="ccd14-169">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="ccd14-170">Beachten Sie, dass sie mit den Eigenschaften identisch sind, die von einer Standardschaltfläche verfügbar gemacht werden, außer es besteht eine zusätzliche Eigenschaft `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-170">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="ccd14-171">Legen Sie die `ButtonValue`-Eigenschaft auf `5` fest.</span><span class="sxs-lookup"><span data-stu-id="ccd14-171">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="ccd14-172">Auf der **alle Windows Forms** auf der Registerkarte die **Toolbox**, doppelklicken Sie auf **Bezeichnung** Hinzufügen einer <xref:System.Windows.Forms.Label> Steuerelement dem Formular.</span><span class="sxs-lookup"><span data-stu-id="ccd14-172">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="ccd14-173">Verschieben Sie die Bezeichnung in die Mitte des Formulars.</span><span class="sxs-lookup"><span data-stu-id="ccd14-173">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="ccd14-174">Doppelklicken Sie auf `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-174">Double-click `ValueButton1`.</span></span>  
  
     <span data-ttu-id="ccd14-175">Der **Code-Editor** wird im Ereignis `ValueButton1_Click` geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ccd14-175">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="ccd14-176">Geben Sie die folgende Codezeile ein.</span><span class="sxs-lookup"><span data-stu-id="ccd14-176">Type the following line of code.</span></span>  
  
    ```vb  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. <span data-ttu-id="ccd14-177">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Test**, und wählen Sie im Kontextmenü **Als Startprojekt festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="ccd14-177">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="ccd14-178">Wählen Sie im Menü **Debuggen** die Option **Debugging starten**.</span><span class="sxs-lookup"><span data-stu-id="ccd14-178">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="ccd14-179">`Form1` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ccd14-179">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="ccd14-180">Klicken Sie auf `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="ccd14-180">Click `Valuebutton1`.</span></span>  
  
     <span data-ttu-id="ccd14-181">Die Zahl '5' wird in `Label1` angezeigt und zeigt, dass die Eigenschaft `ButtonValue` Ihres geerbten Steuerelements mit der Methode `ValueButton1_Click` an `Label1` weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="ccd14-181">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="ccd14-182">Daher erbt Ihr `ValueButton`-Steuerelement die gesamte Funktionalität der standardmäßigen Windows Forms-Schaltfläche und macht eine zusätzliche benutzerdefinierte Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ccd14-182">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd14-183">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccd14-183">See Also</span></span>  
 [<span data-ttu-id="ccd14-184">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ccd14-184">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="ccd14-185">Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“</span><span class="sxs-lookup"><span data-stu-id="ccd14-185">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="ccd14-186">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ccd14-186">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="ccd14-187">Grundlagen der Vererbung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccd14-187">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="ccd14-188">Exemplarische Vorgehensweise: Erstellen von Komponenten</span><span class="sxs-lookup"><span data-stu-id="ccd14-188">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
