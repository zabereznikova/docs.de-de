---
title: 'Vorgehensweise: Erstellen einer Aktivität'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: 48df9b90a92468858bd3ac5498bd83fd0d57fe75
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315139"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="96c9e-102">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="96c9e-102">How to: Create an Activity</span></span>

<span data-ttu-id="96c9e-103">Aktivitäten sind die wichtigsten Einheiten für das Verhalten in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96c9e-103">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="96c9e-104">Die Ausführungslogik einer Aktivität kann in verwaltetem Code oder mithilfe anderer Aktivitäten implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="96c9e-104">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="96c9e-105">In diesem Thema wird veranschaulicht, wie zwei Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="96c9e-105">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="96c9e-106">Die erste Aktivität ist eine einfache Aktivität, die die Ausführungslogik auf der Basis von Code implementiert.</span><span class="sxs-lookup"><span data-stu-id="96c9e-106">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="96c9e-107">Die Implementierung der zweiten Aktivität wird mithilfe anderer Aktivitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="96c9e-107">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="96c9e-108">Diese Aktivitäten werden in den folgenden Schritten des Lernprogramms verwendet.</span><span class="sxs-lookup"><span data-stu-id="96c9e-108">These activities are used in following steps in the tutorial.</span></span>

> [!NOTE]
> <span data-ttu-id="96c9e-109">Eine abgeschlossene Version des Tutorials können Sie im [Windows Workflow Foundation (WF45) Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="96c9e-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="96c9e-110">Erstellen Sie die Workflow-aktivitätsbibliothekprojekt</span><span class="sxs-lookup"><span data-stu-id="96c9e-110">Create the activity library project</span></span>

1. <span data-ttu-id="96c9e-111">Öffnen Sie Visual Studio, und wählen Sie **neu** > **Projekt** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="96c9e-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="96c9e-112">In der **neues Projekt** Dialogfeld unter die **installiert** Kategorie **Visual C#-** > **Workflow** (oder **Visual Basic** > **Workflow**).</span><span class="sxs-lookup"><span data-stu-id="96c9e-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="96c9e-113">Wenn Sie nicht sehen die **Workflow** Vorlagenkategorie, müssen Sie möglicherweise installieren die **Windows Workflow Foundation** Komponente von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96c9e-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="96c9e-114">Wählen Sie die **Visual Studio-Installer öffnen** Link auf der linken Seite die **neues Projekt** Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="96c9e-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="96c9e-115">Wählen Sie in Visual Studio-Installer die **Einzelkomponenten** Registerkarte. Klicken Sie unter den **Entwicklungsaktivitäten** Kategorie der **Windows Workflow Foundation** Komponente.</span><span class="sxs-lookup"><span data-stu-id="96c9e-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="96c9e-116">Wählen Sie **ändern** die Komponente installieren.</span><span class="sxs-lookup"><span data-stu-id="96c9e-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="96c9e-117">Wählen Sie die **Aktivitätsbibliothek** Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="96c9e-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="96c9e-118">Typ `NumberGuessWorkflowActivities` in die **Namen** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="96c9e-119">Mit der rechten Maustaste **Activity1.xaml** in **Projektmappen-Explorer** , und wählen Sie **löschen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="96c9e-120">Klicken Sie zur Bestätigung auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="96c9e-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="96c9e-121">Erstellen Sie die ReadInt-Aktivität</span><span class="sxs-lookup"><span data-stu-id="96c9e-121">Create the ReadInt activity</span></span>

1. <span data-ttu-id="96c9e-122">Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="96c9e-122">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="96c9e-123">In der **installiert** > **gemeinsame Elemente** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="96c9e-124">Wählen Sie **Codeaktivität** aus der **Workflow** Liste.</span><span class="sxs-lookup"><span data-stu-id="96c9e-124">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="96c9e-125">Typ `ReadInt` in die **Namen** ein, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="96c9e-126">Ersetzen Sie die vorhandene `ReadInt`-Definition durch die folgende Definition.</span><span class="sxs-lookup"><span data-stu-id="96c9e-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="96c9e-127">Die `ReadInt`-Aktivität wird von <xref:System.Activities.NativeActivity%601> statt von <xref:System.Activities.CodeActivity> abgeleitet. Das entspricht dem Standard für die Vorlage "Codeaktivität".</span><span class="sxs-lookup"><span data-stu-id="96c9e-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="96c9e-128"><xref:System.Activities.CodeActivity%601> kann verwendet werden, wenn die Aktivität ein einziges Ergebnis bereitstellt, das durch das <xref:System.Activities.Activity%601.Result%2A>-Argument verfügbar gemacht wird, da <xref:System.Activities.CodeActivity%601> jedoch nicht die Verwendung von Lesezeichen unterstützt, wird <xref:System.Activities.NativeActivity%601> verwendet.</span><span class="sxs-lookup"><span data-stu-id="96c9e-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="96c9e-129">Erstellen Sie die Prompt-Aktivität</span><span class="sxs-lookup"><span data-stu-id="96c9e-129">Create the Prompt activity</span></span>

1. <span data-ttu-id="96c9e-130">Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="96c9e-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="96c9e-131">Durch das Erstellen des Projekts wird die `ReadInt`-Aktivität in diesem Projekt erstellt, mit der die benutzerdefinierte Aktivität aus diesem Schritt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="96c9e-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="96c9e-132">Wählen Sie **neues Element hinzufügen** aus der **Projekt** Menü.</span><span class="sxs-lookup"><span data-stu-id="96c9e-132">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="96c9e-133">In der **installiert** > **gemeinsame Elemente** Knoten **Workflow**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="96c9e-134">Wählen Sie **Aktivität** aus der **Workflow** Liste.</span><span class="sxs-lookup"><span data-stu-id="96c9e-134">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="96c9e-135">Typ `Prompt` in die **Namen** ein, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="96c9e-136">Doppelklicken Sie auf **Prompt.xaml** in **Projektmappen-Explorer** um es im Designer anzuzeigen, wenn er nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="96c9e-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="96c9e-137">Klicken Sie auf **Argumente** in den links unten auf der der Aktivitäts-Designer zum Anzeigen der **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="96c9e-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="96c9e-138">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-138">Click **Create Argument**.</span></span>

8. <span data-ttu-id="96c9e-139">Typ `BookmarkName` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Zeichenfolge** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE** auf das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="96c9e-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="96c9e-140">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="96c9e-141">Typ `Result` in die **Namen** Feld unter dem neu hinzugefügten `BookmarkName` Argument die Option **Out** aus der **Richtung** Dropdown-Liste **Int32** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="96c9e-142">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="96c9e-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="96c9e-143">Typ `Text` in die **Namen** wählen Sie im **In** aus der **Richtung** Dropdown-Liste **Zeichenfolge** aus der **Argumenttyp** Dropdown-Liste, und drücken Sie dann die **EINGABETASTE** auf das Argument zu speichern.</span><span class="sxs-lookup"><span data-stu-id="96c9e-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="96c9e-144">Diese drei Argumente werden an die entsprechenden Argumente der <xref:System.Activities.Statements.WriteLine>-Aktivität und `ReadInt`-Aktivität gebunden, die der `Prompt`-Aktivität in den folgenden Schritten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="96c9e-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="96c9e-145">Klicken Sie auf **Argumente** in der unteren linken Seite des Aktivitätsdesigners zu schließen die **Argumente** Bereich.</span><span class="sxs-lookup"><span data-stu-id="96c9e-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="96c9e-146">Ziehen Sie eine **Sequenz** Aktivität aus der **Ablaufsteuerung** im Abschnitt der **Toolbox** und legen ihn auf der **Aktivität hier ablegen** Bezeichnung der **Eingabeaufforderung** Aktivitäts-Designer.</span><span class="sxs-lookup"><span data-stu-id="96c9e-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="96c9e-147">Wenn die **Toolbox** Fenster nicht angezeigt wird, wählen Sie **Toolbox** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="96c9e-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="96c9e-148">Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** im Abschnitt der **Toolbox** und legen ihn auf die **Aktivität hier ablegen** Bezeichnung der **Sequenz** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="96c9e-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="96c9e-149">Binden der **Text** Argument der **WriteLine** Aktivität, um die **Text** Argument der **Eingabeaufforderung** Aktivität durch Eingabe `Text` in der **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** im Feld der **Eigenschaften** Fenster, und drücken Sie dann die **Registerkarte** -Taste zwei Mal.</span><span class="sxs-lookup"><span data-stu-id="96c9e-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="96c9e-150">Dadurch wird das Fenster mit den IntelliSense-Listenmembern geschlossen und der Eigenschaftswert gespeichert, indem die Auswahl der Eigenschaft aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="96c9e-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="96c9e-151">Diese Eigenschaft kann auch festgelegt werden, indem Sie eingeben `Text` in die **Geben Sie einen C#-Ausdruck** oder **VB-Ausdruck eingeben** Feld in der Aktivität selbst.</span><span class="sxs-lookup"><span data-stu-id="96c9e-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="96c9e-152">Wenn die **Fenster "Eigenschaften"** als nicht angezeigt, aktivieren **Fenster "Eigenschaften"** aus der **Ansicht** Menü.</span><span class="sxs-lookup"><span data-stu-id="96c9e-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="96c9e-153">Ziehen Sie eine **ReadInt** Aktivität aus der **NumberGuessWorkflowActivities** Teil der **Toolbox** und legen Sie sie in der **Sequenz** -Aktivität, folgt die **WriteLine** Aktivität.</span><span class="sxs-lookup"><span data-stu-id="96c9e-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="96c9e-154">Binden der **BookmarkName** Argument der **ReadInt** Aktivität, um die **BookmarkName** Argument der **Eingabeaufforderung** Aktivität durch Eingabe von `BookmarkName` in die **VB-Ausdruck eingeben** Feld rechts neben der **BookmarkName** -Argument in der **Fenster "Eigenschaften"**, und drücken Sie dann die **Registerkarte** Schlüssel doppelt so groß wie das IntelliSense-Liste-Member-Fenster zu schließen und speichern Sie die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96c9e-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="96c9e-155">Binden der **Ergebnis** Argument der **ReadInt** Aktivität, um die **Ergebnis** Argument der **Eingabeaufforderung** Aktivität durch Eingabe `Result` in der **VB-Ausdruck eingeben** Feld rechts neben der **Ergebnis** -Argument in der **Fenster "Eigenschaften"**, und drücken Sie dann die **Registerkarte** zweimal-Taste.</span><span class="sxs-lookup"><span data-stu-id="96c9e-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="96c9e-156">Drücken Sie **STRG**+**UMSCHALT**+**B** zum Erstellen der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="96c9e-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96c9e-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="96c9e-157">Next steps</span></span>

<span data-ttu-id="96c9e-158">Anweisungen zum Erstellen eines Workflows mit den Aktivitäten besteht, finden Sie im nächsten Schritt im Tutorial [Vorgehensweise: Erstellen eines Workflows](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="96c9e-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96c9e-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96c9e-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="96c9e-160">Entwerfen und Implementieren von benutzerdefinierten Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="96c9e-160">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="96c9e-161">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="96c9e-161">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="96c9e-162">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="96c9e-162">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="96c9e-163">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="96c9e-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)