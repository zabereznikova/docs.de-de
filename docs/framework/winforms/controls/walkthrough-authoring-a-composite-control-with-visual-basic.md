---
title: 'Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: 6404e5933f886578b4ad8afd0d3da324541fc3f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792248"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="6d386-102">Exemplarische Vorgehensweise: Erstellen eines zusammengesetzten Steuerelements mit Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d386-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="6d386-103">Zusammengesetzte Steuerelemente bieten eine Möglichkeit, mit der benutzerdefinierte grafische Schnittstellen erstellt und wiederverwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6d386-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="6d386-104">Ein zusammengesetztes Steuerelement ist im wesentlichen eine Komponente mit visueller Darstellung.</span><span class="sxs-lookup"><span data-stu-id="6d386-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="6d386-105">Daher können zusammengesetzte Steuerelemente aus einem oder mehr Windows Forms-Steuerelementen, Komponenten oder Codeblöcken bestehen. Diese erweitern die Funktionalität durch Validieren von Benutzereingaben, verändern Anzeigeeigenschaften oder führen andere vom Autor gewünschte Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="6d386-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="6d386-106">Zusammengesetzte Steuerelemente können genau wie andere Steuerelemente in Windows Forms platziert werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="6d386-107">Im ersten Teil dieser exemplarischen Vorgehensweise erstellen Sie ein einfaches zusammengesetztes Steuerelement namens `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="6d386-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="6d386-108">Im zweiten Teil der exemplarischen Vorgehensweise erweitern Sie die Funktionalität von `ctlClock` durch Vererbung.</span><span class="sxs-lookup"><span data-stu-id="6d386-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6d386-109">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="6d386-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6d386-110">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6d386-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6d386-111">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6d386-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="6d386-112">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="6d386-112">Creating the Project</span></span>  
 <span data-ttu-id="6d386-113">Geben Sie beim Erstellen des Projekts den Namen an, um den Stammnamespace, Assemblynamen und Projektnamen festzulegen und sicherzustellen, dass sich die Standardkomponente im richtigen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="6d386-113">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="6d386-114">So erstellen Sie die ctlClockLib-Steuerelementbibliothek und das ctlClock-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-114">To create the ctlClockLib control library and the ctlClock control</span></span>  
  
1. <span data-ttu-id="6d386-115">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**, um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6d386-115">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="6d386-116">Wählen Sie aus der Liste der Visual Basic-Projekte, die **Windows-Steuerelementbibliothek** Projekt aus, geben `ctlClockLib` in die **Namen** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="6d386-116">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6d386-117">Der Projektname `ctlClockLib` wird standardmäßig auch dem Stammnamespace zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6d386-117">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="6d386-118">Der Stammnamespace wird verwendet, um die Namen der Komponenten in der Assembly zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="6d386-118">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="6d386-119">Wenn z.B. zwei Assemblys Komponenten mit dem Namen `ctlClock` bereitstellen, können Sie Ihre `ctlClock`-Komponente mithilfe von `ctlClockLib.ctlClock.` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6d386-119">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>  
  
3. <span data-ttu-id="6d386-120">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **UserControl1.vb** und klicken Sie dann auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-120">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="6d386-121">Ändern Sie den Dateinamen in `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="6d386-121">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="6d386-122">Klicken Sie auf die Schaltfläche **Ja**, wenn Sie gefragt werden, ob alle Verweise auf das Codeelement „UserControl1“ umbenannt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6d386-122">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d386-123">Standardmäßig erbt ein zusammengesetztes Steuerelement von der <xref:System.Windows.Forms.UserControl> Klasse, die vom System bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-123">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="6d386-124">Die <xref:System.Windows.Forms.UserControl> Klasse bietet Funktionen, die von allen zusammengesetzten Steuerelementen benötigt und implementiert Standardmethoden und-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6d386-124">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>  
  
4. <span data-ttu-id="6d386-125">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d386-125">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="6d386-126">Hinzufügen von Windows-Steuerelementen und -Komponenten zum zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-126">Adding Windows Controls and Components to the Composite Control</span></span>  
 <span data-ttu-id="6d386-127">Eine visuelle Schnittstelle ist ein wesentlicher Bestandteil von zusammengesetzten Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="6d386-127">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="6d386-128">Diese visuelle Schnittstelle wird durch das Hinzufügen eines oder mehrerer Windows-Steuerelemente zur Designeroberfläche implementiert.</span><span class="sxs-lookup"><span data-stu-id="6d386-128">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="6d386-129">Im folgenden Beispiel integrieren Sie Windows-Steuerelemente in das zusammengesetzte Steuerelement und schreiben Code, um Funktionalität zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6d386-129">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="6d386-130">So fügen Sie eine Bezeichnung und einen Timer zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="6d386-130">To add a Label and a Timer to your composite control</span></span>  
  
1. <span data-ttu-id="6d386-131">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und wählen Sie **Designer anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="6d386-131">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>  
  
2. <span data-ttu-id="6d386-132">Erweitern Sie in der Toolbox den Knoten **Allgemeine Steuerelemente**, und doppelklicken Sie dann auf **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="6d386-132">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>  
  
     <span data-ttu-id="6d386-133">Ein <xref:System.Windows.Forms.Label> Steuerelement mit dem Namen `Label1` zu Ihrem Steuerelement auf der Designeroberfläche hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6d386-133">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>  
  
3. <span data-ttu-id="6d386-134">Klicken Sie im Designer auf **Label1**.</span><span class="sxs-lookup"><span data-stu-id="6d386-134">In the designer, click **Label1**.</span></span> <span data-ttu-id="6d386-135">Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="6d386-135">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="6d386-136">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6d386-136">Property</span></span>|<span data-ttu-id="6d386-137">Ändern in</span><span class="sxs-lookup"><span data-stu-id="6d386-137">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="6d386-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="6d386-138">**Name**</span></span>|`lblDisplay`|  
    |<span data-ttu-id="6d386-139">**Text**</span><span class="sxs-lookup"><span data-stu-id="6d386-139">**Text**</span></span>|`(blank space)`|  
    |<span data-ttu-id="6d386-140">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="6d386-140">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="6d386-141">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="6d386-141">**Font.Size**</span></span>|`14`|  
  
4. <span data-ttu-id="6d386-142">Erweitern Sie in der **Toolbox** den Knoten **Komponenten**, und doppelklicken Sie dann auf **Timer**.</span><span class="sxs-lookup"><span data-stu-id="6d386-142">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>  
  
     <span data-ttu-id="6d386-143">Da eine <xref:System.Windows.Forms.Timer> ist eine Komponente, zur Laufzeit keine visuelle Darstellung hat.</span><span class="sxs-lookup"><span data-stu-id="6d386-143">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="6d386-144">Er wird daher nicht bei den Steuerelementen auf der Designeroberfläche angezeigt, sondern im Komponenten-Designer (eine Taskleiste am unteren Ende der Designeroberfläche).</span><span class="sxs-lookup"><span data-stu-id="6d386-144">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>  
  
5. <span data-ttu-id="6d386-145">Klicken Sie im Komponenten-Designer auf **Timer1**, und legen Sie dann die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft `1000` und die <xref:System.Windows.Forms.Timer.Enabled%2A> Eigenschaft, um `True`.</span><span class="sxs-lookup"><span data-stu-id="6d386-145">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>  
  
     <span data-ttu-id="6d386-146">Die <xref:System.Windows.Forms.Timer.Interval%2A> Eigenschaft steuert die Häufigkeit, mit dem die Timer-Komponente Teilstriche.</span><span class="sxs-lookup"><span data-stu-id="6d386-146">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="6d386-147">Bei jedem Tick von `Timer1` führt sie den Code im Ereignis `Timer1_Tick` aus.</span><span class="sxs-lookup"><span data-stu-id="6d386-147">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="6d386-148">Das Intervall stellt die Anzahl von Millisekunden zwischen Ticks dar.</span><span class="sxs-lookup"><span data-stu-id="6d386-148">The interval represents the number of milliseconds between ticks.</span></span>  
  
6. <span data-ttu-id="6d386-149">Doppelklicken Sie im Komponenten-Designer auf **Timer1**, um zum `Timer1_Tick`-Ereignis für `ctlClock` zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="6d386-149">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>  
  
7. <span data-ttu-id="6d386-150">Ändern Sie den Code so, dass er folgendem Codebeispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="6d386-150">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="6d386-151">Achten Sie darauf, den Zugriffsmodifizierer von `Private` in `Protected` zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6d386-151">Be sure to change the access modifier from `Private` to `Protected`.</span></span>  
  
    ```vb  
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles Timer1.Tick  
        ' Causes the label to display the current time.    
        lblDisplay.Text = Format(Now, "hh:mm:ss")  
    End Sub  
    ```  
  
     <span data-ttu-id="6d386-152">Durch diesen Code wird die aktuelle Zeit in `lblDisplay` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d386-152">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="6d386-153">Da das Intervall von `Timer1` auf `1000` festgelegt wurde, wird dieses Ereignis alle tausend Millisekunden ausgelöst. Dadurch wird die aktuelle Zeit jede Sekunde aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6d386-153">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>  
  
8. <span data-ttu-id="6d386-154">Ändern Sie die Methode so, dass sie überschreibbar ist.</span><span class="sxs-lookup"><span data-stu-id="6d386-154">Modify the method to be overridable.</span></span> <span data-ttu-id="6d386-155">Weitere Informationen finden Sie im Abschnitt „Erben von Benutzersteuerelementen“.</span><span class="sxs-lookup"><span data-stu-id="6d386-155">For more information, see the "Inheriting from a User Control" section below.</span></span>  
  
    ```vb  
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _  
        e As System.EventArgs) Handles Timer1.Tick  
    ```  
  
9. <span data-ttu-id="6d386-156">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d386-156">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="6d386-157">Hinzufügen von Eigenschaften zum zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-157">Adding Properties to the Composite Control</span></span>  
 <span data-ttu-id="6d386-158">Ihr Uhr-Steuerelement kapselt nun ein <xref:System.Windows.Forms.Label> Steuerelement und ein <xref:System.Windows.Forms.Timer> -Komponente, beide mit eigenen vererbten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="6d386-158">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="6d386-159">Während nachfolgende Benutzer des Steuerelements nicht auf die einzelnen Eigenschaften dieser Steuerelemente zugreifen können, können Sie benutzerdefinierte Eigenschaften durch Schreiben der geeigneten Codeblöcke erstellen und verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="6d386-159">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="6d386-160">Im folgenden Vorgang fügen Sie Eigenschaften zum Steuerelement hinzu, die dem Benutzer ermöglichen, die Farbe des Hintergrunds und des Texts zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6d386-160">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>  
  
#### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="6d386-161">So fügen Sie eine Eigenschaft zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="6d386-161">To add a property to your composite control</span></span>  
  
1. <span data-ttu-id="6d386-162">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClock.vb**, und klicken Sie auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-162">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="6d386-163">Der Code-Editor für das Steuerelement wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d386-163">The Code Editor for your control opens.</span></span>  
  
2. <span data-ttu-id="6d386-164">Suchen Sie die Anweisung `Public Class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="6d386-164">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="6d386-165">Geben Sie darunter den folgenden Code ein.</span><span class="sxs-lookup"><span data-stu-id="6d386-165">Beneath it, type the following code.</span></span>  
  
    ```vb  
    Private colFColor as Color  
    Private colBColor as Color  
    ```  
  
     <span data-ttu-id="6d386-166">Diese Anweisungen erstellen die privaten Variablen, die Sie verwenden, um die Werte für die Eigenschaften zu speichern, die Sie gleich erstellen werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-166">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>  
  
3. <span data-ttu-id="6d386-167">Fügen Sie den folgenden Code unter den variablen Deklarationen aus Schritt 2 ein.</span><span class="sxs-lookup"><span data-stu-id="6d386-167">Insert the following code beneath the variable declarations from step 2.</span></span>  
  
    ```vb  
    ' Declares the name and type of the property.  
    Property ClockBackColor() as Color  
        ' Retrieves the value of the private variable colBColor.  
        Get  
            Return colBColor  
        End Get  
        ' Stores the selected value in the private variable colBColor, and   
        ' updates the background color of the label control lblDisplay.  
        Set(ByVal value as Color)  
            colBColor = value  
            lblDisplay.BackColor = colBColor     
        End Set  
  
    End Property  
    ' Provides a similar set of instructions for the foreground color.  
    Property ClockForeColor() as Color  
        Get  
            Return colFColor  
        End Get  
        Set(ByVal value as Color)  
            colFColor = value  
            lblDisplay.ForeColor = colFColor  
        End Set  
    End Property  
    ```  
  
     <span data-ttu-id="6d386-168">Dieser Code stellt nachfolgenden Benutzern dieses Steuerelements zwei benutzerdefinierte Eigenschaften zur Verfügung, `ClockForeColor` und `ClockBackColor`, indem er die Anweisung `Property` aufruft.</span><span class="sxs-lookup"><span data-stu-id="6d386-168">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="6d386-169">Die Anweisungen `Get` und `Set` ermöglichen das Speichern und Abrufen des Eigenschaftswerts sowie des Codes zum Implementieren der geeigneten Funktionalität der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6d386-169">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>  
  
4. <span data-ttu-id="6d386-170">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d386-170">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="testing-the-control"></a><span data-ttu-id="6d386-171">Testen des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="6d386-171">Testing the Control</span></span>  
 <span data-ttu-id="6d386-172">Steuerelemente sind keine eigenständigen Projekte. Sie müssen in einem Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-172">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="6d386-173">Testen Sie das Laufzeitverhalten Ihres Steuerelements, und überprüfen Sie die Eigenschaften im **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="6d386-173">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="6d386-174">Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="6d386-174">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-your-control"></a><span data-ttu-id="6d386-175">So testen Sie das Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-175">To test your control</span></span>  
  
1. <span data-ttu-id="6d386-176">Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.</span><span class="sxs-lookup"><span data-stu-id="6d386-176">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2. <span data-ttu-id="6d386-177">Wählen Sie im Eigenschaftenraster des Testcontainers die Eigenschaft `ClockBackColor` aus, und klicken Sie anschließend auf den Dropdownpfeil, um die Farbpalette anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d386-177">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>  
  
3. <span data-ttu-id="6d386-178">Wählen Sie eine Farbe aus, indem sie darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="6d386-178">Choose a color by clicking it.</span></span>  
  
     <span data-ttu-id="6d386-179">Die Hintergrundfarbe des Steuerelements ändert sich in die ausgewählte Farbe.</span><span class="sxs-lookup"><span data-stu-id="6d386-179">The background color of your control changes to the color you selected.</span></span>  
  
4. <span data-ttu-id="6d386-180">Verwenden Sie eine ähnliche Abfolge von Ereignissen, um zu überprüfen, ob die Eigenschaft `ClockForeColor` funktioniert wie erwartet.</span><span class="sxs-lookup"><span data-stu-id="6d386-180">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>  
  
5. <span data-ttu-id="6d386-181">Klicken Sie auf **Schließen**, um den **UserControl-Testcontainer** zu beenden.</span><span class="sxs-lookup"><span data-stu-id="6d386-181">Click **Close** to close the **UserControl Test Container**.</span></span>  
  
     <span data-ttu-id="6d386-182">In diesem Abschnitt und in den vorherigen Abschnitten haben Sie gesehen, wie Komponenten und Windows-Steuerelemente mit Code und Paketen kombiniert werden können, um benutzerdefinierte Funktionalität in Form eines zusammengesetzten Steuerelements zu bieten.</span><span class="sxs-lookup"><span data-stu-id="6d386-182">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="6d386-183">Sie haben gelernt, Eigenschaften in Ihrem zusammengesetzten Steuerelement verfügbar zu machen, und das Steuerelement nach Abschluss zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6d386-183">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="6d386-184">Im nächsten Abschnitt erfahren Sie, wie man ein vererbtes zusammengesetztes Steuerelement mithilfe von `ctlClock` als Basis verwendet.</span><span class="sxs-lookup"><span data-stu-id="6d386-184">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>  
  
## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="6d386-185">Erben von einem zusammengesetzten Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-185">Inheriting from a Composite Control</span></span>  
 <span data-ttu-id="6d386-186">In den vorherigen Abschnitten haben Sie gelernt, wie man Windows-Steuerelemente, Komponenten und Code in wiederverwendbare zusammengesetzte Steuerelemente kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6d386-186">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="6d386-187">Das zusammengesetzte Steuerelement kann jetzt als Basis für die Erstellung anderer Steuerelemente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-187">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="6d386-188">Der Vorgang, bei dem eine Klasse von einer Basisklasse abgeleitet wird, nennt man *Vererbung*.</span><span class="sxs-lookup"><span data-stu-id="6d386-188">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="6d386-189">In diesem Abschnitt erstellen Sie ein zusammengesetztes Steuerelement namens `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="6d386-189">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="6d386-190">Dieses Steuerelement wird von seinem übergeordneten Steuerelement, `ctlClock`, abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="6d386-190">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="6d386-191">Sie erfahren, wie Sie die Funktionalität von `ctlClock` durch Überschreiben der übergeordneten Methoden und Hinzufügen neuer Methoden und Eigenschaften erweitern können.</span><span class="sxs-lookup"><span data-stu-id="6d386-191">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>  
  
 <span data-ttu-id="6d386-192">Der erste Schritt beim Erstellen eines geerbten Steuerelements ist das Ableiten vom übergeordneten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6d386-192">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="6d386-193">Diese Aktion erstellt ein neues Steuerelement, das über alle Eigenschaften, Methoden und grafischen Merkmale des übergeordneten Steuerelements verfügt, aber auch als Basis für das Hinzufügen neuer oder veränderter Funktionalität dienen kann.</span><span class="sxs-lookup"><span data-stu-id="6d386-193">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>  
  
#### <a name="to-create-the-inherited-control"></a><span data-ttu-id="6d386-194">So erstellen Sie das geerbte Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-194">To create the inherited control</span></span>  
  
1. <span data-ttu-id="6d386-195">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClockLib**, zeigen Sie auf **Hinzufügen**, und klicken Sie anschließend auf **Benutzersteuerelement**.</span><span class="sxs-lookup"><span data-stu-id="6d386-195">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>  
  
     <span data-ttu-id="6d386-196">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d386-196">The **Add New Item** dialog box opens.</span></span>  
  
2. <span data-ttu-id="6d386-197">Wählen Sie die Vorlage **Geerbtes Benutzersteuerelement**.</span><span class="sxs-lookup"><span data-stu-id="6d386-197">Select the **Inherited User Control** template.</span></span>  
  
3. <span data-ttu-id="6d386-198">Geben Sie im Feld **Name** die Bezeichnung `ctlAlarmClock.vb` ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-198">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="6d386-199">Das Dialogfeld **Vererbungsauswahl** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d386-199">The **Inheritance Picker** dialog box appears.</span></span>  
  
4. <span data-ttu-id="6d386-200">Doppelklicken Sie unter **Komponentenname** auf **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="6d386-200">Under **Component Name**, double-click **ctlClock**.</span></span>  
  
5. <span data-ttu-id="6d386-201">Durchsuchen Sie die aktuellen Projekte im Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="6d386-201">In Solution Explorer, browse through the current projects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d386-202">Eine Datei namens **ctlAlarmClock.vb** wurde zum aktuellen Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d386-202">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>  
  
### <a name="adding-the-alarm-properties"></a><span data-ttu-id="6d386-203">Hinzufügen von Wecker-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="6d386-203">Adding the Alarm Properties</span></span>  
 <span data-ttu-id="6d386-204">Eigenschaften werden auf die gleiche Weise zu einem geerbten Steuerelement hinzugefügt wie zu einem zusammengesetzten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6d386-204">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="6d386-205">Sie verwenden jetzt die Syntax zum Deklarieren von Eigenschaften, um zwei Eigenschaften zu Ihrem Steuerelement hinzuzufügen: `AlarmTime`, wodurch der Wert des Datums und der Uhrzeit gespeichert wird, zu der der Wecker klingelt, und `AlarmSet`, die anzeigt, ob der Wecker eingestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d386-205">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>  
  
##### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="6d386-206">So fügen Sie Eigenschaften zum zusammengesetzten Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="6d386-206">To add properties to your composite control</span></span>  
  
1. <span data-ttu-id="6d386-207">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-207">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="6d386-208">Suchen Sie die Klassendeklaration für das ctlAlarmClock-Steuerelement, das als `Public Class ctlAlarmClock` angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6d386-208">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="6d386-209">Fügen Sie den folgenden Code in der Klassendeklaration ein.</span><span class="sxs-lookup"><span data-stu-id="6d386-209">In the class declaration, insert the following code.</span></span>  
  
    ```vb  
    Private dteAlarmTime As Date  
    Private blnAlarmSet As Boolean  
    ' These properties will be declared as Public to allow future   
    ' developers to access them.  
    Public Property AlarmTime() As Date  
        Get  
            Return dteAlarmTime  
        End Get  
        Set(ByVal value as Date)  
            dteAlarmTime = value  
        End Set  
    End Property  
    Public Property AlarmSet() As Boolean  
        Get  
            Return blnAlarmSet  
        End Get  
        Set(ByVal value as Boolean)  
            blnAlarmSet = value  
        End Set  
    End Property  
    ```  
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="6d386-210">Hinzufügen zur grafischen Oberfläche des Steuerelements</span><span class="sxs-lookup"><span data-stu-id="6d386-210">Adding to the Graphical Interface of the Control</span></span>  
 <span data-ttu-id="6d386-211">Das geerbte Steuerelement verfügt über eine visuelle Schnittstelle, die mit dem Steuerelement identisch ist, von dem es erbt.</span><span class="sxs-lookup"><span data-stu-id="6d386-211">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="6d386-212">Es verfügt über die gleichen konstituierenden Steuerelemente wie das übergeordnete Steuerelement. Allerdings sind die Eigenschaften der konstituierenden Steuerelemente nicht verfügbar, solange sie nicht explizit verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-212">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="6d386-213">Sie können zur grafischen Schnittstelle des geerbten zusammengesetzten Steuerelements auf die gleiche Weise hinzufügen, wie Sie zu jedem anderen zusammengesetzten Steuerelement hinzufügen würden.</span><span class="sxs-lookup"><span data-stu-id="6d386-213">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="6d386-214">Um den Vorgang fortzusetzen, zur visuellen Schnittstelle Ihres Weckers hinzuzufügen, fügen Sie ein Label-Steuerelement hinzu, das leuchtet, wenn der Wecker klingelt.</span><span class="sxs-lookup"><span data-stu-id="6d386-214">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>  
  
##### <a name="to-add-the-label-control"></a><span data-ttu-id="6d386-215">So fügen Sie das Label-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="6d386-215">To add the label control</span></span>  
  
1. <span data-ttu-id="6d386-216">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock**, und klicken Sie auf **Designer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-216">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>  
  
     <span data-ttu-id="6d386-217">Der Designer für `ctlAlarmClock` wird im Hauptfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d386-217">The designer for `ctlAlarmClock` opens in the main window.</span></span>  
  
2. <span data-ttu-id="6d386-218">Klicken Sie auf `lblDisplay` (der Anzeigebereich des Steuerelements), und zeigen Sie das Eigenschaftenfenster an.</span><span class="sxs-lookup"><span data-stu-id="6d386-218">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d386-219">Alle Eigenschaften werden angezeigt, sind aber abgeblendet.</span><span class="sxs-lookup"><span data-stu-id="6d386-219">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="6d386-220">Das bedeutet, dass die Eigenschaften nativ zu `lblDisplay` sind, und dass sie nicht im Eigenschaftenfenster geändert oder auf sie zugegriffen werden können.</span><span class="sxs-lookup"><span data-stu-id="6d386-220">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="6d386-221">Standardmäßig sind in einem zusammengesetzten Steuerelement enthaltene Steuerelemente `Private`, und es ist nicht möglich, auf ihre Eigenschaften zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6d386-221">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d386-222">Wenn Sie möchten, dass nachfolgende Benutzer des zusammengesetzten Steuerelements Zugriff auf interne Steuerelemente haben, deklarieren Sie sie als `Public` oder `Protected`.</span><span class="sxs-lookup"><span data-stu-id="6d386-222">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="6d386-223">Dadurch können Sie Eigenschaften von Steuerelementen, die in Ihrem zusammengesetzten Steuerelement enthalten sind, festlegen und ändern, indem Sie den entsprechenden Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d386-223">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>  
  
3. <span data-ttu-id="6d386-224">Hinzufügen einer <xref:System.Windows.Forms.Label> Steuerelement zum zusammengesetzten Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6d386-224">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>  
  
4. <span data-ttu-id="6d386-225">Ziehen Sie mit der Maus die <xref:System.Windows.Forms.Label> -Steuerelement direkt unter das Anzeigefeld.</span><span class="sxs-lookup"><span data-stu-id="6d386-225">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="6d386-226">Legen Sie im Eigenschaftenfenster die folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="6d386-226">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="6d386-227">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6d386-227">Property</span></span>|<span data-ttu-id="6d386-228">Einstellung</span><span class="sxs-lookup"><span data-stu-id="6d386-228">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="6d386-229">**Name**</span><span class="sxs-lookup"><span data-stu-id="6d386-229">**Name**</span></span>|`lblAlarm`|  
    |<span data-ttu-id="6d386-230">**Text**</span><span class="sxs-lookup"><span data-stu-id="6d386-230">**Text**</span></span>|<span data-ttu-id="6d386-231">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="6d386-231">**Alarm!**</span></span>|  
    |<span data-ttu-id="6d386-232">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="6d386-232">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="6d386-233">**Visible**</span><span class="sxs-lookup"><span data-stu-id="6d386-233">**Visible**</span></span>|`False`|  
  
### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="6d386-234">Hinzufügen der Wecker-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="6d386-234">Adding the Alarm Functionality</span></span>  
 <span data-ttu-id="6d386-235">In den vorherigen Schritten haben Sie Eigenschaften und ein Steuerelement hinzugefügt, dass die Wecker-Funktionalität in Ihrem zusammengesetzten Steuerelement aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6d386-235">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="6d386-236">In diesem Verfahren fügen Sie Code hinzu, um die aktuelle Zeit mit der Weckzeit zu vergleichen, und bei Gleichheit einen Wecker klingeln und leuchten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="6d386-236">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="6d386-237">Durch Überschreiben der Methode `Timer1_Tick` von `ctlClock` und Hinzufügen von zusätzlichem Code erweitern Sie die Funktion von `ctlAlarmClock` während alle geerbten Funktionen von `ctlClock` erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="6d386-237">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a><span data-ttu-id="6d386-238">So überschreiben Sie die Methode „Timer1_Tick“ von „ctlClock“</span><span class="sxs-lookup"><span data-stu-id="6d386-238">To override the Timer1_Tick method of ctlClock</span></span>  
  
1. <span data-ttu-id="6d386-239">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und klicken Sie dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-239">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="6d386-240">Suchen Sie die `Private blnAlarmSet As Boolean`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6d386-240">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="6d386-241">Fügen Sie direkt darunter die folgende Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d386-241">Immediately beneath it, add the following statement.</span></span>  
  
    ```vb  
    Dim blnColorTicker as Boolean  
    ```  
  
3. <span data-ttu-id="6d386-242">Suchen Sie die `End Class` Anweisung unten auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="6d386-242">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="6d386-243">Fügen Sie direkt vor der Anweisung `End Class` den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d386-243">Just before the `End Class` statement, add the following code.</span></span>  
  
    ```vb  
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _  
        As System.EventArgs)  
        ' Calls the Timer1_Tick method of ctlClock.  
        MyBase.Timer1_Tick(sender, e)  
        ' Checks to see if the Alarm is set.  
        If AlarmSet = False Then  
            Exit Sub  
        End If  
        ' If the date, hour, and minute of the alarm time are the same as  
        ' now, flash and beep an alarm.   
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _  
            AlarmTime.Minute = Now.Minute Then  
            ' Sounds an audible beep.  
            Beep()  
            ' Sets lblAlarmVisible to True, and changes the background color based on the   
            ' value of blnColorTicker. The background color of the label will   
            ' flash once per tick of the clock.  
            lblAlarm.Visible = True  
            If blnColorTicker = False Then  
                lblAlarm.BackColor = Color.PeachPuff  
                blnColorTicker = True  
            Else  
                lblAlarm.BackColor = Color.Plum  
                blnColorTicker = False  
            End If  
        Else  
            ' Once the alarm has sounded for a minute, the label is made   
            ' invisible again.  
            lblAlarm.Visible = False  
        End If  
    End Sub  
    ```  
  
     <span data-ttu-id="6d386-244">Das Hinzufügen dieses Codes dient mehreren Zwecken.</span><span class="sxs-lookup"><span data-stu-id="6d386-244">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="6d386-245">Die Anweisung `Overrides` weist das Steuerelement an, diese Methode statt der Methode zu verwenden, die vom Basissteuerelement geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d386-245">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="6d386-246">Wenn diese Methode aufgerufen wird, ruft sie durch Aufruf der `MyBase.Timer1_Tick`-Anweisung die überschriebene Methode auf. Damit wird sichergestellt, dass die gesamte Funktionalität, die im ursprünglichen Steuerelement enthalten ist, in diesem Steuerelement reproduziert wird.</span><span class="sxs-lookup"><span data-stu-id="6d386-246">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="6d386-247">Anschließend ruft sie zusätzlichen Code auf, um die Wecker-Funktionalität zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="6d386-247">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="6d386-248">Ein blinkendes Label-Steuerelement erscheint, wenn der Wecker ausgelöst wird, und ein hörbarer Signalton ertönt.</span><span class="sxs-lookup"><span data-stu-id="6d386-248">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d386-249">Da Sie einen geerbten Ereignishandler außer Kraft setzen, müssen Sie das Ereignis nicht mit dem Schlüsselwort `Handles` angeben.</span><span class="sxs-lookup"><span data-stu-id="6d386-249">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="6d386-250">Das Ereignis ist bereits eingebunden.</span><span class="sxs-lookup"><span data-stu-id="6d386-250">The event is already hooked up.</span></span> <span data-ttu-id="6d386-251">Sie überschreiben lediglich die Implementierung des Handlers.</span><span class="sxs-lookup"><span data-stu-id="6d386-251">All you are overriding is the implementation of the handler.</span></span>  
  
     <span data-ttu-id="6d386-252">Das Wecker-Steuerelement ist fast abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6d386-252">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="6d386-253">Sie müssen nur noch eine Möglichkeit zum Deaktivieren implementieren.</span><span class="sxs-lookup"><span data-stu-id="6d386-253">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="6d386-254">Zu diesem Zweck fügen Sie Code zur Methode `lblAlarm_Click` hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d386-254">To do this, you will add code to the `lblAlarm_Click` method.</span></span>  
  
##### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="6d386-255">So implementieren Sie die Methode zum Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="6d386-255">To implement the shutoff method</span></span>  
  
1. <span data-ttu-id="6d386-256">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlAlarmClock.vb**, und klicken Sie dann auf **Designer anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-256">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>  
  
2. <span data-ttu-id="6d386-257">Doppelklicken Sie im Designer auf **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="6d386-257">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="6d386-258">Der **Code-Editor** wird in der Zeile `Private Sub lblAlarm_Click` geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d386-258">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>  
  
3. <span data-ttu-id="6d386-259">Ändern Sie die Methode so, dass sie folgendem Code ähnelt.</span><span class="sxs-lookup"><span data-stu-id="6d386-259">Modify this method so that it resembles the following code.</span></span>  
  
    ```vb  
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _  
     System.EventArgs) Handles lblAlarm.Click  
        ' Turns off the alarm.  
        AlarmSet = False  
        ' Hides the flashing label.  
        lblAlarm.Visible = False  
    End Sub  
    ```  
  
4. <span data-ttu-id="6d386-260">Klicken Sie im Menü **Datei** auf **Alles speichern**, um das Projekt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d386-260">On the **File** menu, click **Save All** to save the project.</span></span>  
  
### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="6d386-261">Verwenden des geerbten Steuerelements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="6d386-261">Using the Inherited Control on a Form</span></span>  
 <span data-ttu-id="6d386-262">Sie können Ihr geerbte Steuerelement die gleiche Weise, wie Sie das Steuerelement Basisklasse getestet testen `ctlClock`: Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.</span><span class="sxs-lookup"><span data-stu-id="6d386-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="6d386-263">Weitere Informationen finden Sie unter [Vorgehensweise: Testen Sie das Laufzeitverhalten eines UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="6d386-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="6d386-264">Sie müssen das Steuerelement auf einem Formular hosten, um es verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="6d386-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="6d386-265">Wie standardmäßige zusammengesetzten Steuerelemente kann ein geerbtes zusammengesetztes Steuerelement nicht alleine stehen und muss in einem Formular oder einem anderen Container gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="6d386-266">Da `ctlAlarmClock` über eine tiefer gehende Funktionalität verfügt, wird zusätzlicher Code für das Testen benötigt.</span><span class="sxs-lookup"><span data-stu-id="6d386-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="6d386-267">In dieser Vorgehensweise schreiben Sie ein einfaches Programm, um die Funktionalität von `ctlAlarmClock` zu testen.</span><span class="sxs-lookup"><span data-stu-id="6d386-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="6d386-268">Sie schreiben Code zum Einstellen und Anzeigen der Eigenschaft `AlarmTime` von `ctlAlarmClock` und testen die geerbten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6d386-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="6d386-269">So erstellen Sie ein Steuerelement und fügen es zu einem Testformular hinzu</span><span class="sxs-lookup"><span data-stu-id="6d386-269">To build and add your control to a test form</span></span>  
  
1. <span data-ttu-id="6d386-270">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **ctlClockLib**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-270">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>  
  
2. <span data-ttu-id="6d386-271">Zeigen Sie im Menü **Datei** auf die Option **Hinzufügen**, und klicken Sie anschließend auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="6d386-271">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>  
  
3. <span data-ttu-id="6d386-272">Fügen Sie der Projektmappe ein neues **Windows-Anwendungsprojekt** mit dem Namen `Test` hinzu.</span><span class="sxs-lookup"><span data-stu-id="6d386-272">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>  
  
     <span data-ttu-id="6d386-273">Das **Test**-Projekt wird zum Projektmappen-Explorer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6d386-273">The **Test** project is added to Solution Explorer.</span></span>  
  
4. <span data-ttu-id="6d386-274">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten `Test`, und klicken Sie anschließend auf **Verweis hinzufügen**, um das Dialogfeld **Verweis hinzufügen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d386-274">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>  
  
5. <span data-ttu-id="6d386-275">Klicken Sie auf die Registerkarte mit der Bezeichnung **Projekte**.</span><span class="sxs-lookup"><span data-stu-id="6d386-275">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="6d386-276">Das Projekt **ctlClockLib** wird unter **Projektname** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6d386-276">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="6d386-277">Doppelklicken Sie auf **ctlClockLib**, um den Verweis auf das Testprojekt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d386-277">Double-click **ctlClockLib** to add the reference to the test project.</span></span>  
  
6. <span data-ttu-id="6d386-278">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Test**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-278">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>  
  
7. <span data-ttu-id="6d386-279">Erweitern Sie in der **Toolbox** den Knoten **ctlClockLib Components**.</span><span class="sxs-lookup"><span data-stu-id="6d386-279">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>  
  
8. <span data-ttu-id="6d386-280">Doppelklicken Sie auf **ctlAlarmClock**, um eine Instanz von `ctlAlarmClock` zu Ihrem Formular hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d386-280">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>  
  
9. <span data-ttu-id="6d386-281">In der **Toolbox**, suchen, und doppelklicken Sie auf **DateTimePicker** Hinzufügen einer <xref:System.Windows.Forms.DateTimePicker> -Steuerelement auf das Formular, und fügen Sie dann eine <xref:System.Windows.Forms.Label> Steuerelement durch Doppelklicken auf **Bezeichnung**.</span><span class="sxs-lookup"><span data-stu-id="6d386-281">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>  
  
10. <span data-ttu-id="6d386-282">Verwenden Sie die Maus, um das Steuerelement an einem geeigneten Ort auf dem Formular zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="6d386-282">Use the mouse to position the controls in a convenient place on the form.</span></span>  
  
11. <span data-ttu-id="6d386-283">Legen Sie die Eigenschaften dieser Steuerelemente wie folgt fest.</span><span class="sxs-lookup"><span data-stu-id="6d386-283">Set the properties of these controls in the following manner.</span></span>  
  
    |<span data-ttu-id="6d386-284">Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6d386-284">Control</span></span>|<span data-ttu-id="6d386-285">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6d386-285">Property</span></span>|<span data-ttu-id="6d386-286">Wert</span><span class="sxs-lookup"><span data-stu-id="6d386-286">Value</span></span>|  
    |-------------|--------------|-----------|  
    |`label1`|<span data-ttu-id="6d386-287">**Text**</span><span class="sxs-lookup"><span data-stu-id="6d386-287">**Text**</span></span>|`(blank space)`|  
    ||<span data-ttu-id="6d386-288">**Name**</span><span class="sxs-lookup"><span data-stu-id="6d386-288">**Name**</span></span>|`lblTest`|  
    |`dateTimePicker1`|<span data-ttu-id="6d386-289">**Name**</span><span class="sxs-lookup"><span data-stu-id="6d386-289">**Name**</span></span>|`dtpTest`|  
    ||<span data-ttu-id="6d386-290">**Format**</span><span class="sxs-lookup"><span data-stu-id="6d386-290">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
12. <span data-ttu-id="6d386-291">Doppelklicken Sie im Designer auf **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="6d386-291">In the designer, double-click **dtpTest**.</span></span>  
  
     <span data-ttu-id="6d386-292">Der **Code-Editor** für `Private Sub dtpTest_ValueChanged` wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6d386-292">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>  
  
13. <span data-ttu-id="6d386-293">Ändern Sie den Code so, dass er folgendem Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="6d386-293">Modify the code so that it resembles the following.</span></span>  
  
    ```vb  
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _  
        System.EventArgs) Handles dtpTest.ValueChanged  
        ctlAlarmClock1.AlarmTime = dtpTest.Value  
        ctlAlarmClock1.AlarmSet = True  
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _  
            "hh:mm")  
    End Sub  
    ```  
  
14. <span data-ttu-id="6d386-294">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf **Test**, und klicken Sie anschließend auf **Als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="6d386-294">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>  
  
15. <span data-ttu-id="6d386-295">Klicken Sie im Menü **Debuggen** auf **Debuggen starten**.</span><span class="sxs-lookup"><span data-stu-id="6d386-295">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="6d386-296">Das Testprogramm wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="6d386-296">The test program starts.</span></span> <span data-ttu-id="6d386-297">Beachten Sie, dass die aktuelle Uhrzeit, in aktualisiert wird der `ctlAlarmClock` -Steuerelement, und die Startzeit in angezeigt wird der <xref:System.Windows.Forms.DateTimePicker> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6d386-297">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>  
  
16. <span data-ttu-id="6d386-298">Klicken Sie auf die <xref:System.Windows.Forms.DateTimePicker> , in dem die Minuten der Stunde angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d386-298">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>  
  
17. <span data-ttu-id="6d386-299">Legen Sie mithilfe der Tastatur einen Wert für die Minuten fest, der eine Minute höher ist als die aktuell von `ctlAlarmClock` angezeigte Zeit.</span><span class="sxs-lookup"><span data-stu-id="6d386-299">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>  
  
     <span data-ttu-id="6d386-300">Die Zeit für die Einstellung des Weckers wird in `lblTest` angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d386-300">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="6d386-301">Warten Sie, bis die angezeigte Zeit die für den Wecker eingestellte Zeit erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="6d386-301">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="6d386-302">Wenn die angezeigte Zeit die Zeit erreicht, auf die der Wecker eingestellt ist, ertönt ein Signalton und `lblAlarm` leuchtet.</span><span class="sxs-lookup"><span data-stu-id="6d386-302">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>  
  
18. <span data-ttu-id="6d386-303">Deaktivieren Sie den Wecker, indem Sie auf `lblAlarm` klicken.</span><span class="sxs-lookup"><span data-stu-id="6d386-303">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="6d386-304">Sie können den Wecker nun zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="6d386-304">You may now reset the alarm.</span></span>  
  
     <span data-ttu-id="6d386-305">In dieser exemplarischen Vorgehensweise wurden zahlreiche wichtige Konzepte behandelt.</span><span class="sxs-lookup"><span data-stu-id="6d386-305">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="6d386-306">Sie haben gelernt, ein zusammengesetztes Steuerelement zu erstellen, indem Sie Steuerelemente und Komponenten in einem Container für zusammengesetzte Steuerelemente kombiniert haben.</span><span class="sxs-lookup"><span data-stu-id="6d386-306">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="6d386-307">Sie haben gelernt, Eigenschaften zu Ihrem Steuerelement hinzuzufügen und Code für das Implementieren benutzerdefinierter Funktionalität zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="6d386-307">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="6d386-308">Im letzten Abschnitt haben Sie gelernt, die Funktionalität eines bestimmten zusammengesetzten Steuerelements durch Vererbung zu erweitern und die Funktionalität von Host-Methoden durch außer Kraft setzen dieser Methoden zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6d386-308">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d386-309">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d386-309">See also</span></span>

- [<span data-ttu-id="6d386-310">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="6d386-310">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="6d386-311">Vorgehensweise: Erstellen von zusammengesetzten Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="6d386-311">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="6d386-312">Vorgehensweise: Anzeigen eines Steuerelements in der Toolbox-Elemente-Dialogfeld "auswählen"</span><span class="sxs-lookup"><span data-stu-id="6d386-312">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
