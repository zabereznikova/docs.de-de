---
title: "Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 08cb39215ea1d9aff1cd7ecc125bd731f14a4d7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="3c294-102">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="3c294-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>
<span data-ttu-id="3c294-103">Wenn die Komponenten von einem Projekt in der gerade geöffneten Projektmappe definiert sind, werden sie automatisch in angezeigt der **Toolbox**, keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3c294-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="3c294-104">Sie können auch manuell Auffüllen der **Toolbox** mit den benutzerdefinierten Komponenten mithilfe der [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), aber die **Toolbox** berücksichtigt der Elemente in der Projektmappe erstellen Sie Ausgaben mit den folgenden Merkmalen:</span><span class="sxs-lookup"><span data-stu-id="3c294-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>  
  
-   <span data-ttu-id="3c294-105">Implementiert <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="3c294-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>  
  
-   <span data-ttu-id="3c294-106">Verfügt nicht über <xref:System.ComponentModel.ToolboxItemAttribute> festgelegt `false`;</span><span class="sxs-lookup"><span data-stu-id="3c294-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>  
  
-   <span data-ttu-id="3c294-107">Verfügt nicht über <xref:System.ComponentModel.DesignTimeVisibleAttribute> festgelegt `false`.</span><span class="sxs-lookup"><span data-stu-id="3c294-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c294-108">Die **Toolbox** Verweis Ketten zu erkennen, werden nicht befolgt werden, damit keine Elemente angezeigt werden, die nicht von einem Projekt in der Projektmappe erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3c294-108">The **Toolbox** does not follow reference chains, so it will not display items that are not built by a project in your solution.</span></span>  
  
 <span data-ttu-id="3c294-109">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in angezeigt wird der **Toolbox** , nachdem die Komponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3c294-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="3c294-110">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="3c294-110">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="3c294-111">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="3c294-111">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="3c294-112">Erstellen eine benutzerdefinierte Komponente.</span><span class="sxs-lookup"><span data-stu-id="3c294-112">Creating a custom component.</span></span>  
  
-   <span data-ttu-id="3c294-113">Erstellen eine Instanz einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="3c294-113">Creating an instance of a custom component.</span></span>  
  
-   <span data-ttu-id="3c294-114">Entladen und erneutes Laden einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="3c294-114">Unloading and reloading a custom component.</span></span>  
  
 <span data-ttu-id="3c294-115">Wenn Sie fertig sind, sehen Sie, den **Toolbox** wird aufgefüllt, mit einer Komponente, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="3c294-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c294-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="3c294-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3c294-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3c294-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3c294-118">Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="3c294-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="3c294-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="3c294-119">Creating the Project</span></span>  
 <span data-ttu-id="3c294-120">Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="3c294-120">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="3c294-121">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="3c294-121">To create the project</span></span>  
  
1.  <span data-ttu-id="3c294-122">Erstellen Sie ein Windows-basiertes Anwendungsprojekt mit dem Namen `ToolboxExample`.</span><span class="sxs-lookup"><span data-stu-id="3c294-122">Create a Windows-based application project called `ToolboxExample`.</span></span>  
  
     <span data-ttu-id="3c294-123">Weitere Informationen finden Sie unter [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="3c294-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="3c294-124">Fügen Sie dem Projekt eine neue Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="3c294-124">Add a new component to the project.</span></span> <span data-ttu-id="3c294-125">Rufen sie `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="3c294-125">Call it `DemoComponent`.</span></span>  
  
     <span data-ttu-id="3c294-126">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen neuer Projektelemente](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span><span class="sxs-lookup"><span data-stu-id="3c294-126">For more information, see [NIB:How to: Add New Project Items](http://msdn.microsoft.com/en-us/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).</span></span>  
  
3.  <span data-ttu-id="3c294-127">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="3c294-127">Build the project.</span></span>  
  
4.  <span data-ttu-id="3c294-128">Aus der **Tools** Menü klicken Sie auf die **Optionen** Element.</span><span class="sxs-lookup"><span data-stu-id="3c294-128">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="3c294-129">Klicken Sie auf **allgemeine** unter der **Windows Forms-Designer** Element und sicherstellen, dass die **AutoToolboxPopulate** Option wird festgelegt, um **"true"**.</span><span class="sxs-lookup"><span data-stu-id="3c294-129">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>  
  
## <a name="creating-an-instance-of-a-custom-component"></a><span data-ttu-id="3c294-130">Erstellen einer Instanz einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="3c294-130">Creating an Instance of a Custom Component</span></span>  
 <span data-ttu-id="3c294-131">Der nächste Schritt besteht, eine Instanz der benutzerdefinierten Komponente auf dem Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c294-131">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="3c294-132">Da die **Toolbox** automatisch die Konten für die neue Komponente, dies ist genauso einfach wie beliebige andere Komponenten oder Steuerelemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c294-132">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>  
  
#### <a name="to-create-an-instance-of-a-custom-component"></a><span data-ttu-id="3c294-133">Zum Erstellen einer Instanz einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="3c294-133">To create an instance of a custom component</span></span>  
  
1.  <span data-ttu-id="3c294-134">Öffnen Sie das Formular des Projekts in der **Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="3c294-134">Open the project's form in the **Forms Designer**.</span></span>  
  
2.  <span data-ttu-id="3c294-135">In der **Toolbox**, klicken Sie auf die neue Registerkarte **ToolboxExample-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="3c294-135">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>  
  
     <span data-ttu-id="3c294-136">Sobald Sie auf die Registerkarte "klicken, sehen Sie **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="3c294-136">Once you click the tab, you will see **DemoComponent**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3c294-137">Aus Leistungsgründen Komponenten im Bereich automatisch aufgefüllt, der die **Toolbox** benutzerdefinierte Bitmaps werden nicht angezeigt und die <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c294-137">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="3c294-138">Zum Anzeigen eines Symbols für eine benutzerdefinierte Komponente in der **Toolbox**, verwenden Sie die **Toolboxelemente auswählen** (Dialogfeld), um die Komponente zu laden.</span><span class="sxs-lookup"><span data-stu-id="3c294-138">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>  
  
3.  <span data-ttu-id="3c294-139">Ziehen Sie die Komponente auf dem Formular aus.</span><span class="sxs-lookup"><span data-stu-id="3c294-139">Drag your component onto your form.</span></span>  
  
     <span data-ttu-id="3c294-140">Eine Instanz der Komponente erstellt und hinzugefügt werden, um die **Komponentenleiste**.</span><span class="sxs-lookup"><span data-stu-id="3c294-140">An instance of the component is created and added to the **Component Tray**.</span></span>  
  
## <a name="unloading-and-reloading-a-custom-component"></a><span data-ttu-id="3c294-141">Entladen und erneutes Laden einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="3c294-141">Unloading and Reloading a Custom Component</span></span>  
 <span data-ttu-id="3c294-142">Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt entspricht, und bei einem Projekt entladen wurde, entfernen Sie Verweise auf Komponenten des Projekts.</span><span class="sxs-lookup"><span data-stu-id="3c294-142">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>  
  
#### <a name="to-experiment-with-the-effect-on-the-toolbox-of-unloading-and-reloading-components"></a><span data-ttu-id="3c294-143">Experimentieren Sie mit dem Effekt in der Toolbox des Entladens und erneuten Laden von Komponenten</span><span class="sxs-lookup"><span data-stu-id="3c294-143">To experiment with the effect on the Toolbox of unloading and reloading components</span></span>  
  
1.  <span data-ttu-id="3c294-144">Entladen Sie das Projekt aus der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3c294-144">Unload the project from the solution.</span></span>  
  
     <span data-ttu-id="3c294-145">Weitere Informationen zu Projekte entladen, finden Sie unter [NIB: Gewusst: entladen und erneutes Laden von Projekten](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span><span class="sxs-lookup"><span data-stu-id="3c294-145">For more information about unloading projects, see [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/en-us/abc0155b-8fcb-4ffc-95b6-698518a7100b).</span></span> <span data-ttu-id="3c294-146">Wenn Sie aufgefordert werden, speichern, wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="3c294-146">If you are prompted to save, choose **Yes**.</span></span>  
  
2.  <span data-ttu-id="3c294-147">Fügen Sie einen neuen **Windows-Anwendung** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="3c294-147">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="3c294-148">Öffnen Sie das Formular in der **Designer**.</span><span class="sxs-lookup"><span data-stu-id="3c294-148">Open the form in the **Designer**.</span></span>  
  
     <span data-ttu-id="3c294-149">Die **ToolboxExample-Komponenten** Registerkarte aus dem vorherigen Projekt ist nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3c294-149">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>  
  
3.  <span data-ttu-id="3c294-150">Zum erneuten Laden der `ToolboxExample` Projekt.</span><span class="sxs-lookup"><span data-stu-id="3c294-150">Reload the `ToolboxExample` project.</span></span>  
  
     <span data-ttu-id="3c294-151">Die **ToolboxExample-Komponenten** Registerkarte jetzt wird erneut angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c294-151">The **ToolboxExample Components** tab now reappears.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3c294-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c294-152">Next Steps</span></span>  
 <span data-ttu-id="3c294-153">Diese exemplarische Vorgehensweise veranschaulicht, die die **Toolbox** berücksichtigt Komponenten eines Projekts, aber die **Toolbox** ist auch Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="3c294-153">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="3c294-154">Experimentieren Sie eigene benutzerdefinierte Steuerelemente durch Hinzufügen und entfernen Projekte in der Projektmappe aus.</span><span class="sxs-lookup"><span data-stu-id="3c294-154">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c294-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c294-155">See Also</span></span>  
 [<span data-ttu-id="3c294-156">Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="3c294-156">General, Windows Forms Designer, Options Dialog Box</span></span>](http://msdn.microsoft.com/en-us/8dd170af-72f0-4212-b04b-034ceee92834)  
 [<span data-ttu-id="3c294-157">Vorgehensweise: Ändern von Registerkarten der Toolbox</span><span class="sxs-lookup"><span data-stu-id="3c294-157">How to: Manipulate Toolbox Tabs</span></span>](http://msdn.microsoft.com/en-us/21285050-cadd-455a-b1f5-a2289a89c4db)  
 [<span data-ttu-id="3c294-158">Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="3c294-158">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="3c294-159">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c294-159">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)
