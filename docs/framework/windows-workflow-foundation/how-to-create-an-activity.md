---
title: 'Vorgehensweise: Erstellen einer Aktivität'
description: 'In diesem Artikel erfahren Sie, wie Sie zwei Aktivitäten in Workflow Foundation erstellen: eine, die Code verwendet, um die Logik zu implementieren, und eine, die mithilfe anderer Aktivitäten definiert wurde.'
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
ms.assetid: c09b1e99-21b5-4d96-9c04-ec31db3f4436
ms.openlocfilehash: c7610d8612eb944afa9c23e1bf2abceeb3a6d38b
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190766"
---
# <a name="how-to-create-an-activity"></a><span data-ttu-id="1b21d-103">Vorgehensweise: Erstellen einer Aktivität</span><span class="sxs-lookup"><span data-stu-id="1b21d-103">How to: Create an Activity</span></span>

<span data-ttu-id="1b21d-104">Aktivitäten sind die wichtigsten Einheiten für das Verhalten in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1b21d-104">Activities are the core unit of behavior in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span> <span data-ttu-id="1b21d-105">Die Ausführungslogik einer Aktivität kann in verwaltetem Code oder mithilfe anderer Aktivitäten implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b21d-105">The execution logic of an activity can be implemented in managed code or it can be implemented by using other activities.</span></span> <span data-ttu-id="1b21d-106">In diesem Thema wird veranschaulicht, wie zwei Aktivitäten erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b21d-106">This topic demonstrates how to create two activities.</span></span> <span data-ttu-id="1b21d-107">Die erste Aktivität ist eine einfache Aktivität, die die Ausführungslogik auf der Basis von Code implementiert.</span><span class="sxs-lookup"><span data-stu-id="1b21d-107">The first activity is a simple activity that uses code to implement its execution logic.</span></span> <span data-ttu-id="1b21d-108">Die Implementierung der zweiten Aktivität wird mithilfe anderer Aktivitäten definiert.</span><span class="sxs-lookup"><span data-stu-id="1b21d-108">The implementation of the second activity is defined by using other activities.</span></span> <span data-ttu-id="1b21d-109">Diese Aktivitäten werden in den folgenden Schritten des Lernprogramms verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b21d-109">These activities are used in following steps in the tutorial.</span></span>

## <a name="create-the-activity-library-project"></a><span data-ttu-id="1b21d-110">Erstellen des Aktivitäts Bibliotheks Projekts</span><span class="sxs-lookup"><span data-stu-id="1b21d-110">Create the activity library project</span></span>

1. <span data-ttu-id="1b21d-111">Öffnen Sie Visual Studio, und wählen Sie  >  im Menü **Datei** die Option neues **Projekt** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-111">Open Visual Studio and choose **New** > **Project** from the **File** menu.</span></span>

2. <span data-ttu-id="1b21d-112">Wählen Sie im Dialogfeld **Neues Projekt** unter der Kategorie **installiert** die Option **Visual c#**-  >  **Workflow** (oder **Visual Basic**  >  **Workflow**) aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-112">In the **New Project** dialog, under the **Installed** category, select **Visual C#** > **Workflow** (or **Visual Basic** > **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1b21d-113">Wenn die Kategorie **Workflow** Vorlage nicht angezeigt wird, müssen Sie möglicherweise die **Windows Workflow Foundation** Komponente von Visual Studio installieren.</span><span class="sxs-lookup"><span data-stu-id="1b21d-113">If you don't see the **Workflow** template category, you may need to install the **Windows Workflow Foundation** component of Visual Studio.</span></span> <span data-ttu-id="1b21d-114">Wählen Sie auf der linken Seite des Dialog Felds **Neues Projekt** den Link **Visual Studio-Installer öffnen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-114">Choose the **Open Visual Studio Installer** link on the left-hand side of the **New Project** dialog.</span></span> <span data-ttu-id="1b21d-115">Wählen Sie in Visual Studio-Installer die Registerkarte **einzelne Komponenten** aus. Wählen Sie dann unter der Kategorie **Entwicklungsaktivitäten** die **Windows Workflow Foundation** Komponente aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-115">In Visual Studio Installer, select the **Individual components** tab. Then, under the **Development activities** category, select the **Windows Workflow Foundation** component.</span></span> <span data-ttu-id="1b21d-116">Wählen Sie **ändern** aus, um die Komponente zu installieren.</span><span class="sxs-lookup"><span data-stu-id="1b21d-116">Choose **Modify** to install the component.</span></span>

3. <span data-ttu-id="1b21d-117">Wählen Sie die Projektvorlage **Aktivitäts Bibliothek** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-117">Select the **Activity Library** project template.</span></span> <span data-ttu-id="1b21d-118">Geben Sie `NumberGuessWorkflowActivities` in das Feld **Name** ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-118">Type `NumberGuessWorkflowActivities` in the **Name** box and then click **OK**.</span></span>

4. <span data-ttu-id="1b21d-119">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf **Activity1.xaml**, und wählen Sie dann **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-119">Right-click **Activity1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="1b21d-120">Klicken Sie auf **OK** , um zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="1b21d-120">Click **OK** to confirm.</span></span>

## <a name="create-the-readint-activity"></a><span data-ttu-id="1b21d-121">Erstellen der Read int-Aktivität</span><span class="sxs-lookup"><span data-stu-id="1b21d-121">Create the ReadInt activity</span></span>

1. <span data-ttu-id="1b21d-122">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-122">Choose **Add New Item** from the **Project** menu.</span></span>

2. <span data-ttu-id="1b21d-123">Wählen Sie im Knoten **installierte**  >  **Allgemeine Elemente** die Option **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-123">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="1b21d-124">Wählen Sie **Code Aktivität** aus der Liste **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-124">Select **Code Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="1b21d-125">Geben Sie `ReadInt` in das Feld **Name** ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-125">Type `ReadInt` into the **Name** box and then click **Add**.</span></span>

4. <span data-ttu-id="1b21d-126">Ersetzen Sie die vorhandene `ReadInt`-Definition durch die folgende Definition.</span><span class="sxs-lookup"><span data-stu-id="1b21d-126">Replace the existing `ReadInt` definition with the following definition.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#1](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/readint.cs#1)]
     [!code-vb[CFX_WF_GettingStarted#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/readint.vb#1)]

    > [!NOTE]
    > <span data-ttu-id="1b21d-127">Die `ReadInt`-Aktivität wird von <xref:System.Activities.NativeActivity%601> statt von <xref:System.Activities.CodeActivity> abgeleitet. Das entspricht dem Standard für die Vorlage "Codeaktivität".</span><span class="sxs-lookup"><span data-stu-id="1b21d-127">The `ReadInt` activity derives from <xref:System.Activities.NativeActivity%601> instead of <xref:System.Activities.CodeActivity>, which is the default for the code activity template.</span></span> <span data-ttu-id="1b21d-128"><xref:System.Activities.CodeActivity%601> kann verwendet werden, wenn die Aktivität ein einziges Ergebnis bereitstellt, das durch das <xref:System.Activities.Activity%601.Result%2A>-Argument verfügbar gemacht wird, da <xref:System.Activities.CodeActivity%601> jedoch nicht die Verwendung von Lesezeichen unterstützt, wird <xref:System.Activities.NativeActivity%601> verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b21d-128"><xref:System.Activities.CodeActivity%601> can be used if the activity provides a single result, which is exposed through the <xref:System.Activities.Activity%601.Result%2A> argument, but <xref:System.Activities.CodeActivity%601> does not support the use of bookmarks, so <xref:System.Activities.NativeActivity%601> is used.</span></span>

## <a name="create-the-prompt-activity"></a><span data-ttu-id="1b21d-129">Erstellen der prompt-Aktivität</span><span class="sxs-lookup"><span data-stu-id="1b21d-129">Create the Prompt activity</span></span>

1. <span data-ttu-id="1b21d-130">Drücken Sie **STRG** + **UMSCHALT** + **B** , um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b21d-130">Press **Ctrl**+**Shift**+**B** to build the project.</span></span> <span data-ttu-id="1b21d-131">Durch das Erstellen des Projekts wird die `ReadInt`-Aktivität in diesem Projekt erstellt, mit der die benutzerdefinierte Aktivität aus diesem Schritt erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1b21d-131">Building the project enables the `ReadInt` activity in this project to be used to build the custom activity from this step.</span></span>

2. <span data-ttu-id="1b21d-132">Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-132">Choose **Add New Item** from the **Project** menu.</span></span>

3. <span data-ttu-id="1b21d-133">Wählen Sie im Knoten **installierte**  >  **Allgemeine Elemente** die Option **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-133">In the **Installed** > **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="1b21d-134">Wählen Sie **Aktivität** aus der Liste **Workflow** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-134">Select **Activity** from the **Workflow** list.</span></span>

4. <span data-ttu-id="1b21d-135">Geben Sie `Prompt` in das Feld **Name** ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-135">Type `Prompt` into the **Name** box and then click **Add**.</span></span>

5. <span data-ttu-id="1b21d-136">Doppelklicken Sie in **Projektmappen-Explorer** auf **prompt. XAML** , um Sie im Designer anzuzeigen, wenn Sie nicht bereits angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1b21d-136">Double-click **Prompt.xaml** in **Solution Explorer** to display it in the designer if it is not already displayed.</span></span>

6. <span data-ttu-id="1b21d-137">Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b21d-137">Click **Arguments** in the lower-left side of the activity designer to display the **Arguments** pane.</span></span>

7. <span data-ttu-id="1b21d-138">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-138">Click **Create Argument**.</span></span>

8. <span data-ttu-id="1b21d-139">Geben `BookmarkName` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Zeichenfolge** aus, und drücken **Sie** dann die EINGABETASTE, um das Argument</span><span class="sxs-lookup"><span data-stu-id="1b21d-139">Type `BookmarkName` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

9. <span data-ttu-id="1b21d-140">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-140">Click **Create Argument**.</span></span>

10. <span data-ttu-id="1b21d-141">Geben `Result` Sie in das Feld **Name** unter dem neu hinzugefügten `BookmarkName` Argument ein, wählen Sie aus der Dropdown Liste **Richtung** die Option **aus** , wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Int32** aus, und drücken Sie dann die **Eingabe** Taste.</span><span class="sxs-lookup"><span data-stu-id="1b21d-141">Type `Result` into the **Name** box that is underneath the newly added `BookmarkName` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press **Enter**.</span></span>

11. <span data-ttu-id="1b21d-142">Klicken Sie auf **Argument erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1b21d-142">Click **Create Argument**.</span></span>

12. <span data-ttu-id="1b21d-143">Geben `Text` Sie in das Feld **Name** ein, wählen Sie in der Dropdown Liste **Richtung** die Option **in** aus, wählen Sie in der Dropdown Liste **Argumenttyp** die Option **Zeichenfolge** aus, und drücken **Sie** dann die EINGABETASTE, um das Argument</span><span class="sxs-lookup"><span data-stu-id="1b21d-143">Type `Text` into the **Name** box, select **In** from the **Direction** drop-down list, select **String** from the **Argument type** drop-down list, and then press **Enter** to save the argument.</span></span>

     <span data-ttu-id="1b21d-144">Diese drei Argumente werden an die entsprechenden Argumente der <xref:System.Activities.Statements.WriteLine>-Aktivität und `ReadInt`-Aktivität gebunden, die der `Prompt`-Aktivität in den folgenden Schritten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1b21d-144">These three arguments are bound to the corresponding arguments of the <xref:System.Activities.Statements.WriteLine> and `ReadInt` activities that are added to the `Prompt` activity in the following steps.</span></span>

13. <span data-ttu-id="1b21d-145">Klicken Sie unten links im Aktivitäts-Designer auf **Argumente**, um den Bereich **Argumente** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1b21d-145">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

14. <span data-ttu-id="1b21d-146">Ziehen Sie eine **Sequence** -Aktivität aus dem Abschnitt **Ablauf Steuerung** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** des **prompt** -Aktivitäts Designers ab.</span><span class="sxs-lookup"><span data-stu-id="1b21d-146">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Prompt** activity designer.</span></span>

    > [!TIP]
    > <span data-ttu-id="1b21d-147">Wird das Fenster **Toolbox** nicht angezeigt, wählen Sie **Toolbox** im Menü **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-147">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

15. <span data-ttu-id="1b21d-148">Ziehen Sie eine " **Write teline** "-Aktivität aus dem Abschnitt **primitive** der **Toolbox** , und legen Sie Sie auf der Bezeichnung **Aktivität hier ablegen** der **Sequence** -Aktivität ab.</span><span class="sxs-lookup"><span data-stu-id="1b21d-148">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Drop activity here** label of the **Sequence** activity.</span></span>

16. <span data-ttu-id="1b21d-149">Binden Sie das **Text** -Argument der " **Write teline** "-Aktivität an das **Text** -Argument der **prompt** -Aktivität `Text` , indem Sie in das Feld " **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben** " im **Eigenschaften** Fenster eingeben und dann zweimal die **Tab** -Taste drücken.</span><span class="sxs-lookup"><span data-stu-id="1b21d-149">Bind the **Text** argument of the **WriteLine** activity to the **Text** argument of the **Prompt** activity by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box in the **Properties** window, and then press the **Tab** key two times.</span></span> <span data-ttu-id="1b21d-150">Dadurch wird das Fenster mit den IntelliSense-Listenmembern geschlossen und der Eigenschaftswert gespeichert, indem die Auswahl der Eigenschaft aufgehoben wird.</span><span class="sxs-lookup"><span data-stu-id="1b21d-150">This dismisses the IntelliSense list members window and saves the property value by moving the selection off the property.</span></span> <span data-ttu-id="1b21d-151">Diese Eigenschaft kann auch festgelegt werden, indem `Text` Sie in das Feld **c#-Ausdruck eingeben** oder **VB-Ausdruck eingeben** der Aktivität selbst eingeben.</span><span class="sxs-lookup"><span data-stu-id="1b21d-151">This property can also be set by typing `Text` into the **Enter a C# expression** or **Enter a VB expression** box on the activity itself.</span></span>

    > [!TIP]
    > <span data-ttu-id="1b21d-152">Wenn das **Fenster Eigenschaften** nicht angezeigt wird, wählen Sie im Menü **Ansicht** die Option **Eigenschaften Fenster** aus.</span><span class="sxs-lookup"><span data-stu-id="1b21d-152">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

17. <span data-ttu-id="1b21d-153">Ziehen Sie eine Aktivität vom Typ "read **int** " aus dem Abschnitt " **nummeriguess Workflow Activities** " der **Toolbox** , und legen Sie Sie in der **Sequence** -Aktivität ab, sodass Sie der Aktivität " **Write teline** " folgt.</span><span class="sxs-lookup"><span data-stu-id="1b21d-153">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the **WriteLine** activity.</span></span>

18. <span data-ttu-id="1b21d-154">Binden Sie das **BookmarkName** -Argument der Read **int** -Aktivität an das **BookmarkName** -Argument der **prompt** -Aktivität, indem `BookmarkName` Sie in das Feld **VB-Ausdruck eingeben** rechts neben dem **BookmarkName** -Argument im **Eigenschaften Fenster** eingeben. Drücken Sie dann zweimal die **Tab** -Taste, um das Fenster IntelliSense-Listenelemente zu schließen und die Eigenschaft zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1b21d-154">Bind the **BookmarkName** argument of the **ReadInt** activity to the **BookmarkName** argument of the **Prompt** activity by typing `BookmarkName` into the **Enter a VB expression** box to the right of the **BookmarkName** argument in the **Properties Window**, and then press the **Tab** key two times to close the IntelliSense list members window and save the property.</span></span>

19. <span data-ttu-id="1b21d-155">Binden Sie das **Ergebnis** Argument der Aktivität "read **int** " an das **Ergebnis** Argument **der prompt** -Aktivität, indem Sie in `Result` das Feld "vb- **Ausdruck eingeben** " rechts neben dem **Ergebnis** Argument im **Eigenschaften Fenster** eingeben und dann die **Tab** -Taste zweimal drücken.</span><span class="sxs-lookup"><span data-stu-id="1b21d-155">Bind the **Result** argument of the **ReadInt** activity to the **Result** argument of the **Prompt** activity by typing `Result` into the **Enter a VB expression** box to the right of the **Result** argument in the **Properties Window**, and then press the **Tab** key two times.</span></span>

20. <span data-ttu-id="1b21d-156">Drücken Sie **STRG** + **UMSCHALT** + **B** , um die Projekt Mappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1b21d-156">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b21d-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1b21d-157">Next steps</span></span>

<span data-ttu-id="1b21d-158">Anweisungen zum Erstellen eines Workflows mithilfe dieser Aktivitäten finden Sie im nächsten Schritt des Tutorials, Vorgehens [Weise: Erstellen eines Workflows](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="1b21d-158">For instructions on how to create a workflow by using these activities, see the next step in the tutorial, [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b21d-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b21d-159">See also</span></span>

- <xref:System.Activities.CodeActivity>
- <xref:System.Activities.NativeActivity%601>
- [<span data-ttu-id="1b21d-160">Entwerfen und Implementieren von benutzerdefinierten Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="1b21d-160">Designing and Implementing Custom Activities</span></span>](designing-and-implementing-custom-activities.md)
- [<span data-ttu-id="1b21d-161">Lernprogramm 'Erste Schritte'</span><span class="sxs-lookup"><span data-stu-id="1b21d-161">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="1b21d-162">Vorgehensweise: Erstellen eines Workflows</span><span class="sxs-lookup"><span data-stu-id="1b21d-162">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="1b21d-163">Verwenden des ExpressionTextBox in einem benutzerdefinierten Aktivitätsdesigner</span><span class="sxs-lookup"><span data-stu-id="1b21d-163">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
