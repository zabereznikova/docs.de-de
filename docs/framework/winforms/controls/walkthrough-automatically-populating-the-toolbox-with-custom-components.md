---
title: 'Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 8ddb248d2e011714ddc7fb68474f0e92e9ad8b5e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723971"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="ec801-102">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="ec801-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="ec801-103">Wenn die Komponenten von einem Projekt in der aktuell geöffneten Projektmappe definiert sind, werden sie automatisch in angezeigt der **Toolbox**, keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec801-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="ec801-104">Sie können auch manuell Auffüllen der **Toolbox** mit den benutzerdefinierten Komponenten mithilfe der [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), aber die **Toolbox** berücksichtigt der Elemente in der Projektmappe Buildausgaben Sie mit folgenden Merkmalen:</span><span class="sxs-lookup"><span data-stu-id="ec801-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="ec801-105">Implementiert <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="ec801-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="ec801-106">Keine <xref:System.ComponentModel.ToolboxItemAttribute> festgelegt `false`;</span><span class="sxs-lookup"><span data-stu-id="ec801-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="ec801-107">Keine <xref:System.ComponentModel.DesignTimeVisibleAttribute> festgelegt `false`.</span><span class="sxs-lookup"><span data-stu-id="ec801-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec801-108">Die **Toolbox** Verweisketten, werden nicht befolgt werden, damit es keine Elemente angezeigt werden, die von einem Projekt in der Projektmappe nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ec801-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="ec801-109">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in angezeigt wird der **Toolbox** , nachdem die Komponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ec801-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="ec801-110">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ec801-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ec801-111">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ec801-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="ec801-112">Erstellen eine benutzerdefinierte Komponente an.</span><span class="sxs-lookup"><span data-stu-id="ec801-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="ec801-113">Erstellen einer Instanz einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="ec801-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="ec801-114">Entladen und das erneute Laden einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="ec801-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="ec801-115">Wenn Sie fertig sind, sehen Sie, den **Toolbox** wird aufgefüllt, mit einer Komponente, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ec801-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec801-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="ec801-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ec801-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ec801-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ec801-118">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="ec801-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ec801-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ec801-119">Creating the Project</span></span>  
 <span data-ttu-id="ec801-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ec801-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="ec801-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="ec801-121">To create the project</span></span>  
  
1.  <span data-ttu-id="ec801-122">Erstellen Sie ein Windows-basierten Anwendung mit dem Namen `ToolboxExample` (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="ec801-122">Create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="ec801-123">Fügen Sie dem Projekt eine neue Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="ec801-123">Add a new component to the project.</span></span> <span data-ttu-id="ec801-124">Geben Sie ihm den Namen `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="ec801-124">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="ec801-125">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ec801-125">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="ec801-126">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="ec801-126">Build the project.</span></span>  
  
4.  <span data-ttu-id="ec801-127">Von der **Tools** Menü klicken Sie auf die **Optionen** Element.</span><span class="sxs-lookup"><span data-stu-id="ec801-127">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="ec801-128">Klicken Sie auf **allgemeine** unter der **Windows Forms-Designer** Element aus, und stellen sicher, dass die **AutoToolboxPopulate** Option wird festgelegt, um **"true"**.</span><span class="sxs-lookup"><span data-stu-id="ec801-128">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="ec801-129">Erstellen einer Instanz einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="ec801-129">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="ec801-130">Der nächste Schritt ist eine Instanz der benutzerdefinierten Komponente auf dem Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec801-130">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="ec801-131">Da die **Toolbox** automatisch Konten für die neue Komponente, dies ist so einfach wie das Erstellen einer anderen Komponente oder Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ec801-131">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="ec801-132">Zum Erstellen einer Instanz einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="ec801-132">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="ec801-133">Öffnen Sie das Formular des Projekts in der **Formulardesigner**.</span><span class="sxs-lookup"><span data-stu-id="ec801-133">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="ec801-134">In der **Toolbox**, klicken Sie auf die neue Registerkarte **ToolboxExample-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="ec801-134">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="ec801-135">Sobald Sie die Registerkarte klicken, wird Ihnen **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="ec801-135">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec801-136">Aus Leistungsgründen Komponenten in den automatisch ausgefüllten Bereich des der **Toolbox** zeigen keine benutzerdefinierten Bitmaps, und die <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ec801-136">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="ec801-137">Zum Anzeigen eines Symbols für eine benutzerdefinierte Komponente in der **Toolbox**, verwenden Sie die **Toolboxelemente auswählen** (Dialogfeld), laden Sie die Komponente.</span><span class="sxs-lookup"><span data-stu-id="ec801-137">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="ec801-138">Ziehen Sie die Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="ec801-138">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="ec801-139">Eine Instanz der Komponente erstellt und hinzugefügt werden, um die **Komponentenleiste**.</span><span class="sxs-lookup"><span data-stu-id="ec801-139">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="ec801-140">Entladen und Neuladen einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="ec801-140">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="ec801-141">Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt, und wenn ein Projekt entladen wird, entfernt Verweise auf das Projekt die Komponenten.</span><span class="sxs-lookup"><span data-stu-id="ec801-141">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="ec801-142">Experimentieren Sie mit dem Effekt in der Toolbox entladen und Neuladen von Komponenten</span><span class="sxs-lookup"><span data-stu-id="ec801-142">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="ec801-143">Entladen Sie das Projekt aus der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ec801-143">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="ec801-144">Weitere Informationen zum Entladen von Projekten finden Sie unter [Vorgehensweise: Entladen und Laden von Projekten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ec801-144">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="ec801-145">Wenn Sie aufgefordert werden, um zu speichern, wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ec801-145">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="ec801-146">Fügen Sie einen neuen **Windows-Anwendung** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ec801-146">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="ec801-147">Öffnen Sie das Formular in der **Designer**.</span><span class="sxs-lookup"><span data-stu-id="ec801-147">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="ec801-148">Die **ToolboxExample-Komponenten** Registerkarte aus dem vorherigen Projekt ist jetzt nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="ec801-148">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="ec801-149">Erneutes Laden der `ToolboxExample` Projekt.</span><span class="sxs-lookup"><span data-stu-id="ec801-149">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="ec801-150">Die **ToolboxExample-Komponenten** Registerkarte wird wieder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ec801-150">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ec801-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ec801-151">Next Steps</span></span>  
 <span data-ttu-id="ec801-152">In dieser exemplarischen Vorgehensweise wird veranschaulicht, dass die **Toolbox** berücksichtigt Komponenten eines Projekts, aber die **Toolbox** ist auch Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ec801-152">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="ec801-153">Experimentieren Sie mit Ihren eigenen benutzerdefinierten Steuerelementen durch Hinzufügen und Entfernen von Projekten aus Ihrer Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="ec801-153">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec801-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec801-154">See also</span></span>
- <span data-ttu-id="ec801-155">[Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ec801-155">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="ec801-156">[Vorgehensweise: Ändern Sie Toolbox-Registerkarten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ec801-156">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="ec801-157">[Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ec801-157">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="ec801-158">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ec801-158">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
