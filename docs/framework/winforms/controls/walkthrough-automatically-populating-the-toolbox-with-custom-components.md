---
title: 'Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 876de650f9c182c0f82a02d1c5b356faa4f7f118
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211161"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a><span data-ttu-id="bf3f7-102">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="bf3f7-102">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>

<span data-ttu-id="bf3f7-103">Wenn die Komponenten von einem Projekt in der aktuell geöffneten Projektmappe definiert sind, werden sie automatisch in angezeigt der **Toolbox**, keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-103">If your components are defined by a project in the currently open solution, they will automatically appear in the **Toolbox**, with no action required by you.</span></span> <span data-ttu-id="bf3f7-104">Sie können auch manuell Auffüllen der **Toolbox** mit den benutzerdefinierten Komponenten mithilfe der [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), aber die **Toolbox** berücksichtigt der Elemente in der Projektmappe Buildausgaben Sie mit folgenden Merkmalen:</span><span class="sxs-lookup"><span data-stu-id="bf3f7-104">You can also manually populate the **Toolbox** with your custom components by using the [Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), but the **Toolbox** takes account of items in your solution's build outputs with all the following characteristics:</span></span>

- <span data-ttu-id="bf3f7-105">Implementiert <xref:System.ComponentModel.IComponent>;</span><span class="sxs-lookup"><span data-stu-id="bf3f7-105">Implements <xref:System.ComponentModel.IComponent>;</span></span>

- <span data-ttu-id="bf3f7-106">Keine <xref:System.ComponentModel.ToolboxItemAttribute> festgelegt `false`;</span><span class="sxs-lookup"><span data-stu-id="bf3f7-106">Does not have <xref:System.ComponentModel.ToolboxItemAttribute> set to `false`;</span></span>

- <span data-ttu-id="bf3f7-107">Keine <xref:System.ComponentModel.DesignTimeVisibleAttribute> festgelegt `false`.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-107">Does not have <xref:System.ComponentModel.DesignTimeVisibleAttribute> set to `false`.</span></span>

> [!NOTE]
> <span data-ttu-id="bf3f7-108">Die **Toolbox** Verweisketten, werden nicht befolgt werden, sodass er nicht Elemente angezeigt, die von einem Projekt in der Projektmappe nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-108">The **Toolbox** does not follow reference chains, so it won't display items that are not built by a project in your solution.</span></span>

<span data-ttu-id="bf3f7-109">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie eine benutzerdefinierte Komponente automatisch in angezeigt wird der **Toolbox** , nachdem die Komponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-109">This walkthrough demonstrates how a custom component automatically appears in the **Toolbox** once the component is built.</span></span> <span data-ttu-id="bf3f7-110">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="bf3f7-110">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="bf3f7-111">Erstellen ein Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-111">Creating a Windows Forms project.</span></span>

- <span data-ttu-id="bf3f7-112">Erstellen eine benutzerdefinierte Komponente an.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-112">Creating a custom component.</span></span>

- <span data-ttu-id="bf3f7-113">Erstellen einer Instanz einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-113">Creating an instance of a custom component.</span></span>

- <span data-ttu-id="bf3f7-114">Entladen und das erneute Laden einer benutzerdefinierten Komponente.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-114">Unloading and reloading a custom component.</span></span>

<span data-ttu-id="bf3f7-115">Wenn Sie fertig sind, sehen Sie, den **Toolbox** wird aufgefüllt, mit einer Komponente, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-115">When you are finished, you will see that the **Toolbox** is populated with a component that you have created.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="bf3f7-116">Erstellen eines Projekts</span><span class="sxs-lookup"><span data-stu-id="bf3f7-116">Create the project</span></span>

1. <span data-ttu-id="bf3f7-117">Erstellen Sie in Visual Studio ein Windows-basierten Anwendung mit dem Namen `ToolboxExample` (**Datei** > **neu** > **Projekt**  >  **Visual C#**  oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="bf3f7-117">In Visual Studio, create a Windows-based application project called `ToolboxExample` (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="bf3f7-118">Fügen Sie dem Projekt eine neue Komponente hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-118">Add a new component to the project.</span></span> <span data-ttu-id="bf3f7-119">Geben Sie ihm den Namen `DemoComponent`.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-119">Call it `DemoComponent`.</span></span>

     <span data-ttu-id="bf3f7-120">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bf3f7-120">For more information, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span>

3. <span data-ttu-id="bf3f7-121">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-121">Build the project.</span></span>

4. <span data-ttu-id="bf3f7-122">Von der **Tools** Menü klicken Sie auf die **Optionen** Element.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-122">From the **Tools** menu, click the **Options** item.</span></span> <span data-ttu-id="bf3f7-123">Klicken Sie auf **allgemeine** unter der **Windows Forms-Designer** Element aus, und stellen sicher, dass die **AutoToolboxPopulate** Option wird festgelegt, um **"true"**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-123">Click **General** under the **Windows Forms Designer** item and ensure that the **AutoToolboxPopulate** option is set to **True**.</span></span>

## <a name="create-an-instance-of-a-custom-component"></a><span data-ttu-id="bf3f7-124">Erstellen Sie eine Instanz einer benutzerdefinierten Komponente</span><span class="sxs-lookup"><span data-stu-id="bf3f7-124">Create an instance of a custom component</span></span>

<span data-ttu-id="bf3f7-125">Der nächste Schritt ist eine Instanz der benutzerdefinierten Komponente auf dem Formular zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-125">The next step is to create an instance of the custom component on the form.</span></span> <span data-ttu-id="bf3f7-126">Da die **Toolbox** automatisch Konten für die neue Komponente, dies ist so einfach wie das Erstellen einer anderen Komponente oder Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-126">Because the **Toolbox** automatically accounts for the new component, this is as easy as creating any other component or control.</span></span>

1. <span data-ttu-id="bf3f7-127">Öffnen Sie das Formular des Projekts in der **Formulardesigner**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-127">Open the project's form in the **Forms Designer**.</span></span>

2. <span data-ttu-id="bf3f7-128">In der **Toolbox**, klicken Sie auf die neue Registerkarte **ToolboxExample-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-128">In the **Toolbox**, click the new tab called **ToolboxExample Components**.</span></span>

     <span data-ttu-id="bf3f7-129">Sobald Sie die Registerkarte klicken, wird Ihnen **DemoComponent**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-129">Once you click the tab, you will see **DemoComponent**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf3f7-130">Aus Leistungsgründen Komponenten in den automatisch ausgefüllten Bereich des der **Toolbox** zeigen keine benutzerdefinierten Bitmaps, und die <xref:System.Drawing.ToolboxBitmapAttribute> wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-130">For performance reasons, components in the auto-populated area of the **Toolbox** do not display custom bitmaps, and the <xref:System.Drawing.ToolboxBitmapAttribute> is not supported.</span></span> <span data-ttu-id="bf3f7-131">Zum Anzeigen eines Symbols für eine benutzerdefinierte Komponente in der **Toolbox**, verwenden Sie die **Toolboxelemente auswählen** (Dialogfeld), laden Sie die Komponente.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-131">To display an icon for a custom component in the **Toolbox**, use the **Choose Toolbox Items** dialog box to load your component.</span></span>

3. <span data-ttu-id="bf3f7-132">Ziehen Sie die Komponente auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-132">Drag your component onto your form.</span></span>

     <span data-ttu-id="bf3f7-133">Eine Instanz der Komponente erstellt und hinzugefügt werden, um die **Komponentenleiste**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-133">An instance of the component is created and added to the **Component Tray**.</span></span>

## <a name="unload-and-reload-a-custom-component"></a><span data-ttu-id="bf3f7-134">Entladen Sie und Laden Sie eine benutzerdefinierte Komponente</span><span class="sxs-lookup"><span data-stu-id="bf3f7-134">Unload and reload a custom component</span></span>

<span data-ttu-id="bf3f7-135">Die **Toolbox** berücksichtigt die Komponenten in jedem geladenen Projekt, und wenn ein Projekt entladen wird, entfernt Verweise auf das Projekt die Komponenten.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-135">The **Toolbox** takes account of the components in each loaded project, and when a project is unloaded, it removes references to the project's components.</span></span>

1. <span data-ttu-id="bf3f7-136">Entladen Sie das Projekt aus der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-136">Unload the project from the solution.</span></span>

     <span data-ttu-id="bf3f7-137">Weitere Informationen zum Entladen von Projekten finden Sie unter [Vorgehensweise: Entladen und Laden von Projekten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="bf3f7-137">For more information about unloading projects, see [How to: Unload and Reload Projects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)).</span></span> <span data-ttu-id="bf3f7-138">Wenn Sie aufgefordert werden, um zu speichern, wählen Sie **Ja**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-138">If you are prompted to save, choose **Yes**.</span></span>

2. <span data-ttu-id="bf3f7-139">Fügen Sie einen neuen **Windows-Anwendung** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-139">Add a new **Windows Application** project to the solution.</span></span> <span data-ttu-id="bf3f7-140">Öffnen Sie das Formular in der **Designer**.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-140">Open the form in the **Designer**.</span></span>

     <span data-ttu-id="bf3f7-141">Die **ToolboxExample-Komponenten** Registerkarte aus dem vorherigen Projekt ist jetzt nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-141">The **ToolboxExample Components** tab from the previous project is now gone.</span></span>

3. <span data-ttu-id="bf3f7-142">Erneutes Laden der `ToolboxExample` Projekt.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-142">Reload the `ToolboxExample` project.</span></span>

     <span data-ttu-id="bf3f7-143">Die **ToolboxExample-Komponenten** Registerkarte wird wieder angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-143">The **ToolboxExample Components** tab now reappears.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf3f7-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bf3f7-144">Next steps</span></span>

<span data-ttu-id="bf3f7-145">In dieser exemplarischen Vorgehensweise wird veranschaulicht, dass die **Toolbox** berücksichtigt Komponenten eines Projekts, aber die **Toolbox** ist auch Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-145">This walkthrough demonstrates that the **Toolbox** takes account of a project's components, but the **Toolbox** is also takes account of controls.</span></span> <span data-ttu-id="bf3f7-146">Experimentieren Sie mit Ihren eigenen benutzerdefinierten Steuerelementen durch Hinzufügen und Entfernen von Projekten aus Ihrer Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="bf3f7-146">Experiment with your own custom controls by adding and removing control projects from your solution.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf3f7-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf3f7-147">See also</span></span>

- <span data-ttu-id="bf3f7-148">[Allgemein, Windows Forms-Designer, Optionen (Dialogfeld)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf3f7-148">[General, Windows Forms Designer, Options Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))</span></span>
- <span data-ttu-id="bf3f7-149">[Vorgehensweise: Ändern Sie Toolbox-Registerkarten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf3f7-149">[How to: Manipulate Toolbox Tabs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))</span></span>
- <span data-ttu-id="bf3f7-150">[Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bf3f7-150">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- [<span data-ttu-id="bf3f7-151">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bf3f7-151">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
