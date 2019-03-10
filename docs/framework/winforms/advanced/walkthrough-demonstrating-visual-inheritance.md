---
title: 'Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: aa4d18c0e3bbc2613502c7232771c57acc7f0dc8
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721449"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="3c0e5-102">Exemplarische Vorgehensweise: Demonstrieren der visuellen Vererbung</span><span class="sxs-lookup"><span data-stu-id="3c0e5-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="3c0e5-103">Mit visueller Vererbung können Sie die Steuerelemente auf dem Basisformular anzeigen und neue Steuerelemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="3c0e5-104">In dieser exemplarischen Vorgehensweise erstellen Sie ein Basisformular und kompilieren es in eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="3c0e5-105">Sie importieren diese Klassenbibliothek in ein anderes Projekt und erstellen ein neues Formular, das vom Basisformular erbt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="3c0e5-106">Bei dieser exemplarischen Vorgehensweise lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="3c0e5-107">Erstellen eines Klassenbibliotheksprojekts, das ein Basisformular enthält.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="3c0e5-108">Hinzufügen einer Schaltfläche mit Eigenschaften, die abgeleitete Klassen des Basisformulars ändern können.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="3c0e5-109">Hinzufügen einer Schaltfläche, die von Erben des Basisformulars nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="3c0e5-110">Erstellen eines Projekts, das ein Formular enthält, das von `BaseForm` erbt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="3c0e5-111">Schließlich wird in dieser exemplarischen Vorgehensweise der Unterschied zwischen privaten und geschützten Steuerelementen in einem geerbten Formular gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c0e5-112">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3c0e5-113">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3c0e5-114">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-114">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3c0e5-115">Nicht alle Steuerelemente unterstützen visuelle Vererbung von einem Basisformular.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="3c0e5-116">Die folgenden Steuerelemente unterstützen das in dieser exemplarischen Vorgehensweise beschriebene Szenario nicht:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  <span data-ttu-id="3c0e5-117">Diese Steuerelemente im geerbten Formular sind immer schreibgeschützt, unabhängig von den verwendeten Modifizierern (`private`, `protected` oder `public`).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="3c0e5-118">Szenarioschritte</span><span class="sxs-lookup"><span data-stu-id="3c0e5-118">Scenario Steps</span></span>  
 <span data-ttu-id="3c0e5-119">Der erste Schritt ist das Erstellen des Basisformulars.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="3c0e5-120">So erstellen Sie ein Klassenbibliotheksprojekt, das ein Basisformular enthält</span><span class="sxs-lookup"><span data-stu-id="3c0e5-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="3c0e5-121">Aus der **Datei** im Menü wählen **neu**, und klicken Sie dann **Projekt** öffnen die **neues Projekt** im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="3c0e5-122">Erstellen eine Windows Forms-Anwendung, die mit dem Namen `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="3c0e5-123">Erstellen Sie eine Klassenbibliothek anstelle einer standardmäßigen Windows Forms-Anwendung in **Projektmappen-Explorer**, mit der rechten Maustaste die **BaseFormLibrary** Projektknoten und wählen Sie dann **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="3c0e5-124">Ändern Sie in den Eigenschaften für das Projekt, das **Ausgabetyp** aus **Windows-Anwendung** zu **Klassenbibliothek**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="3c0e5-125">Von der **Datei** Menü wählen **Alles speichern** um das Projekt und die Dateien am Standardspeicherort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="3c0e5-126">Mit den nächsten zwei Verfahren werden dem Basisformular Schaltflächen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="3c0e5-127">Zur Demonstration der visuellen Vererbung weisen Sie den Schaltflächen verschiedene Zugriffsebenen zu, indem Sie ihre `Modifiers`Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="3c0e5-128">So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars geändert werden kann</span><span class="sxs-lookup"><span data-stu-id="3c0e5-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="3c0e5-129">Öffnen Sie **Form1** im Designer.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="3c0e5-130">Auf der **alle Windows Forms** Registerkarte die **Toolbox**, doppelklicken Sie auf **Schaltfläche** auf dem Formular eine Schaltfläche hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="3c0e5-131">Verwenden Sie die Maus, um die Position und Größe der Schaltfläche anzupassen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="3c0e5-132">Legen Sie im "Eigenschaftenfenster" die folgenden Eigenschaften der Schaltfläche fest:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="3c0e5-133">Legen Sie die **Text** Eigenschaft **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="3c0e5-134">Legen Sie die **(Name)** Eigenschaft **BtnProtected**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="3c0e5-135">Legen Sie die **Modifizierer** Eigenschaft **geschützte**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-135">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="3c0e5-136">Dadurch wird es möglich, dass Formulare, die von erben **Form1** beim Ändern der Eigenschaften von **BtnProtected**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="3c0e5-137">Doppelklicken Sie auf die **Say Hello** Schaltfläche zum Hinzufügen eines ereignishandlers für das **klicken Sie auf** Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="3c0e5-138">Fügen Sie dem Ereignishandler folgende Codezeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="3c0e5-139">So fügen Sie eine Schaltfläche hinzu, die von Erben des Basisformulars nicht geändert werden kann</span><span class="sxs-lookup"><span data-stu-id="3c0e5-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="3c0e5-140">Wechseln Sie zur Entwurfsansicht durch Klicken auf die **Form1.vb [Entwurf], Form1.cs [Entwurf] oder Form1.jsl [Design]** Registerkarte, die über den Code-Editor, oder drücken Sie F7.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="3c0e5-141">Fügen Sie eine zweite Schaltfläche hinzu, und legen Sie deren Eigenschaften wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="3c0e5-142">Legen Sie die **Text** Eigenschaft **Say Goodbye**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="3c0e5-143">Legen Sie die **(Name)** Eigenschaft **BtnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="3c0e5-144">Legen Sie die **Modifizierer** Eigenschaft **Private**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="3c0e5-145">Dies macht es unmöglich, Formularen, die von erben **Form1** beim Ändern der Eigenschaften von **BtnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="3c0e5-146">Doppelklicken Sie auf die **Say Goodbye** Schaltfläche zum Hinzufügen eines ereignishandlers für das **klicken Sie auf** Ereignis.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="3c0e5-147">Platzieren Sie die folgende Codezeile in der Ereignisprozedur:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="3c0e5-148">Aus der **erstellen** Menü wählen **BaseFormLibrary** die Klassenbibliothek erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="3c0e5-149">Nachdem die Bibliothek erstellt wurde, können Sie ein neues Projekt erstellen, das von dem Formular erbt, das Sie gerade erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="3c0e5-150">So erstellen Sie ein Projekt, das ein Formular enthält, das vom Basisformular erbt</span><span class="sxs-lookup"><span data-stu-id="3c0e5-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="3c0e5-151">Aus der **Datei** im Menü wählen **hinzufügen** und klicken Sie dann **neues Projekt** zum Öffnen der **neues Projekt hinzufügen** im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="3c0e5-152">Erstellen eine Windows Forms-Anwendung, die mit dem Namen `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="3c0e5-153">So fügen Sie ein geerbtes Formular hinzu</span><span class="sxs-lookup"><span data-stu-id="3c0e5-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="3c0e5-154">In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** -Projekt, wählen **hinzufügen**, und wählen Sie dann **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>  
  
2.  <span data-ttu-id="3c0e5-155">In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Windows Forms** Kategorie (Wenn Sie eine Liste der Kategorien haben), und wählen Sie dann die **geerbtes Formular** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="3c0e5-156">Übernehmen Sie den Standardnamen der `Form2` , und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="3c0e5-157">In der **Vererbungsauswahl** wählen Sie im Dialogfeld **Form1** aus der **BaseFormLibrary** Projekt wie das Formular erben, und klicken Sie auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="3c0e5-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="3c0e5-158">Dies erstellt ein Formular in der **InheritanceTest** -Projekt, das das Formular im abgeleitet **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="3c0e5-159">Öffnen Sie das geerbte Formular (**Form2**) im Designer, indem Sie darauf doppelklicken, wenn es nicht bereits geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="3c0e5-160">Im Designer haben die geerbten Schaltflächen ein Symbol (![VisualBasicInheritanceSymbol-bildschirmabbildung](./media/vbinheritanceglyph.gif "VbInheritanceGlyph")) in der oberen Ecke, der angibt, sie werden geerbt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](./media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="3c0e5-161">Wählen Sie die **Say Hello** Schaltfläche, und beobachten Sie die Handles zur Größenänderung.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="3c0e5-162">Da diese Schaltfläche geschützt ist, können die Erben sie verschieben, ihre Größe ändern, ihre Beschriftung ändern und andere Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="3c0e5-163">Wählen Sie die Private **Say Goodbye** Schaltfläche, und beachten Sie, dass sie nicht über die Handles zur Größenänderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="3c0e5-164">Darüber hinaus wird in der **Eigenschaften** werden im Fenster die Eigenschaften dieser Schaltfläche abgeblendet, um anzugeben, kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="3c0e5-165">Wenn Sie Visual C# -Code verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c0e5-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="3c0e5-166">In **Projektmappen-Explorer**, mit der rechten Maustaste **Form1** in die **InheritanceTest** Projekt, und wählen Sie dann **löschen**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="3c0e5-167">Klicken Sie im Meldungsfeld, das angezeigt wird, klicken Sie auf **OK** zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="3c0e5-168">Öffnen Sie die Datei "Program.cs", und ändern Sie die Zeile `Application.Run(new Form1());` in `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="3c0e5-169">In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** Projekt, und wählen **als Startprojekt festlegen**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="3c0e5-170">In **Projektmappen-Explorer**, mit der rechten Maustaste die **InheritanceTest** Projekt, und wählen **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="3c0e5-171">In der **InheritanceTest** Eigenschaftenseiten, Festlegen der **Startobjekt** das geerbte Formular sein (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="3c0e5-172">Drücken Sie F5, um die Anwendung auszuführen, und beobachten Sie das Verhalten des geerbten Formulars.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3c0e5-173">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c0e5-173">Next Steps</span></span>  
 <span data-ttu-id="3c0e5-174">Die Vererbung bei Benutzersteuerelementen funktioniert größtenteils auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="3c0e5-175">Öffnen Sie ein neues Klassenbibliotheksprojekt, und fügen Sie ein Benutzersteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="3c0e5-176">Platzieren Sie konstituierende Steuerelemente darauf, und kompilieren Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="3c0e5-177">Öffnen Sie ein weiteres, neues Klassenbibliotheksprojekt, und fügen Sie einen Verweis auf die kompilierte Klassenbibliothek hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="3c0e5-178">Auch versuchen, ein geerbtes Steuerelement hinzuzufügen (über die **neue Elemente hinzufügen** Dialogfeld) für das Projekt und die **Vererbungsauswahl**.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="3c0e5-179">Fügen Sie ein Benutzersteuerelement hinzu, und Ändern der `Inherits` (`:` in Visual c#)-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="3c0e5-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="3c0e5-180">Weitere Informationen finden Sie unter [Vorgehensweise: Erben von Windows Forms](how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="3c0e5-180">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c0e5-181">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c0e5-181">See also</span></span>
- [<span data-ttu-id="3c0e5-182">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c0e5-182">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="3c0e5-183">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c0e5-183">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="3c0e5-184">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c0e5-184">Windows Forms</span></span>](../index.md)
