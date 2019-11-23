---
title: 'Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 402a25c1cb82c245afa94f58cefc180515622ea9
ms.sourcegitcommit: 992f80328b51b165051c42ff5330788627abe973
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2019
ms.locfileid: "72275863"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="fd73a-102">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="fd73a-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>

<span data-ttu-id="fd73a-103">In dieser Aufgabe erstellen Sie die **Toolbox** -und **PropertyGrid** -Bereiche und fügen Sie dem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd73a-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>

<span data-ttu-id="fd73a-104">Der Code, der in der MainWindow.XAML.cs-Datei enthalten sein sollte, nachdem er die drei Aufgaben im [erneuten Hosting der Workflow-Designer](rehosting-the-workflow-designer.md) Reihe von Themen ausgeführt hat, wird am Ende dieses Themas bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fd73a-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="fd73a-105">So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd73a-105">To create the Toolbox and add it to the grid</span></span>

1. <span data-ttu-id="fd73a-106">Öffnen Sie das HostingApplication-Projekt, das Sie abgerufen haben, indem Sie das in [Aufgabe 2: Hosten des Workflow-Designer](task-2-host-the-workflow-designer.md)beschriebene Verfahren befolgen.</span><span class="sxs-lookup"><span data-stu-id="fd73a-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](task-2-host-the-workflow-designer.md).</span></span>

2. <span data-ttu-id="fd73a-107">Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei " *MainWindow. XAML* ", und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="fd73a-107">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

3. <span data-ttu-id="fd73a-108">Fügen Sie der `MainWindow` Klasse, die einen <xref:System.Activities.Presentation.Toolbox.ToolboxControl>erstellt, eine `GetToolboxControl` Methode hinzu, fügt der **Toolbox**eine neue **Toolbox** Kategorie hinzu, und weist der Kategorie die <xref:System.Activities.Statements.Assign>-und <xref:System.Activities.Statements.Sequence> Aktivitätstypen zu.</span><span class="sxs-lookup"><span data-stu-id="fd73a-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>

    ```csharp
    private ToolboxControl GetToolboxControl()
    {
        // Create the ToolBoxControl.
        var ctrl = new ToolboxControl();

        // Create a category.
        var category = new ToolboxCategory("category1");

        // Create Toolbox items.
        var tool1 =
            new ToolboxItemWrapper("System.Activities.Statements.Assign",
            typeof(Assign).Assembly.FullName, null, "Assign");

        var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
            typeof(Sequence).Assembly.FullName, null, "Sequence");

        // Add the Toolbox items to the category.
        category.Add(tool1);
        category.Add(tool2);

        // Add the category to the ToolBox control.
        ctrl.Categories.Add(category);
        return ctrl;
    }
    ```

4. <span data-ttu-id="fd73a-109">Fügen Sie der `MainWindow` Klasse eine private `AddToolbox` Methode hinzu, die die **Toolbox** in der linken Spalte des Rasters platziert.</span><span class="sxs-lookup"><span data-stu-id="fd73a-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. <span data-ttu-id="fd73a-110">Fügen Sie im `MainWindow()`-Klassenkonstruktor einen aufzurufenden `AddToolBox`-Methode hinzu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fd73a-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. <span data-ttu-id="fd73a-111">Drücken Sie <kbd>F5</kbd> , um die Projekt Mappe zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fd73a-111">Press <kbd>F5</kbd> to build and run your solution.</span></span> <span data-ttu-id="fd73a-112">Die **Toolbox** mit den <xref:System.Activities.Statements.Assign>-und <xref:System.Activities.Statements.Sequence> Aktivitäten sollte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fd73a-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>

## <a name="to-create-the-propertygrid"></a><span data-ttu-id="fd73a-113">So erstellen Sie den PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="fd73a-113">To create the PropertyGrid</span></span>

1. <span data-ttu-id="fd73a-114">Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei " *MainWindow. XAML* ", und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="fd73a-114">In the **Solution Explorer** pane, right-click the *MainWindow.xaml* file and select **View Code**.</span></span>

2. <span data-ttu-id="fd73a-115">Fügen Sie der `MainWindow` Klasse die `AddPropertyInspector`-Methode hinzu, um den Bereich **PropertyGrid** in der Spalte ganz rechts im Raster zu platzieren:</span><span class="sxs-lookup"><span data-stu-id="fd73a-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid:</span></span>

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. <span data-ttu-id="fd73a-116">Fügen Sie im `MainWindow()`-Klassenkonstruktor einen aufzurufenden `AddPropertyInspector`-Methode hinzu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="fd73a-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code:</span></span>

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();
        this.AddToolBox();

        this.AddPropertyInspector();
    }
    ```

4. <span data-ttu-id="fd73a-117">Drücken Sie <kbd>F5</kbd> , um die Projekt Mappe zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fd73a-117">Press <kbd>F5</kbd> to build and run the solution.</span></span> <span data-ttu-id="fd73a-118">Die **Toolbox**, der Workflow Entwurfs Bereich und der **PropertyGrid** -Bereich sollten alle angezeigt werden, und wenn Sie eine <xref:System.Activities.Statements.Assign> Aktivität oder eine <xref:System.Activities.Statements.Sequence> Aktivität auf den Entwurfs Bereich ziehen, sollte das Eigenschaften Raster abhängig von der hervorgehobenen Aktivität aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fd73a-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>

## <a name="example"></a><span data-ttu-id="fd73a-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd73a-119">Example</span></span>

<span data-ttu-id="fd73a-120">Die *MainWindow.XAML.cs* -Datei sollte jetzt den folgenden Code enthalten:</span><span class="sxs-lookup"><span data-stu-id="fd73a-120">The *MainWindow.xaml.cs* file should now contain the following code:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Windows;
using System.Windows.Controls;
using System.Windows.Data;
using System.Windows.Documents;
using System.Windows.Input;
using System.Windows.Media;
using System.Windows.Media.Imaging;
using System.Windows.Navigation;
using System.Windows.Shapes;
// dlls added.
using System.Activities;
using System.Activities.Core.Presentation;
using System.Activities.Presentation;
using System.Activities.Presentation.Metadata;
using System.Activities.Presentation.Toolbox;
using System.Activities.Statements;
using System.ComponentModel;

namespace HostingApplication
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        private WorkflowDesigner wd;

        public MainWindow()
        {
            InitializeComponent();
            RegisterMetadata();
            AddDesigner();
            this.AddToolBox();
            this.AddPropertyInspector();
        }

        private void AddDesigner()
        {
            // Create an instance of WorkflowDesigner class.
            this.wd = new WorkflowDesigner();

            // Place the designer canvas in the middle column of the grid.
            Grid.SetColumn(this.wd.View, 1);

            // Load a new Sequence as default.
            this.wd.Load(new Sequence());

            // Add the designer canvas to the grid.
            grid1.Children.Add(this.wd.View);
        }

        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }

        private ToolboxControl GetToolboxControl()
        {
            // Create the ToolBoxControl.
            var ctrl = new ToolboxControl();

            // Create a category.
            var category = new ToolboxCategory("category1");

            // Create Toolbox items.
            var tool1 =
                new ToolboxItemWrapper("System.Activities.Statements.Assign",
                typeof(Assign).Assembly.FullName, null, "Assign");

            var tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",
                typeof(Sequence).Assembly.FullName, null, "Sequence");

            // Add the Toolbox items to the category.
            category.Add(tool1);
            category.Add(tool2);

            // Add the category to the ToolBox control.
            ctrl.Categories.Add(category);
            return ctrl;
        }

        private void AddToolBox()
        {
            ToolboxControl tc = GetToolboxControl();
            Grid.SetColumn(tc, 0);
            grid1.Children.Add(tc);
        }

        private void AddPropertyInspector()
        {
            Grid.SetColumn(wd.PropertyInspectorView, 2);
            grid1.Children.Add(wd.PropertyInspectorView);
        }

    }
}
```

## <a name="see-also"></a><span data-ttu-id="fd73a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd73a-121">See also</span></span>

- [<span data-ttu-id="fd73a-122">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="fd73a-122">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="fd73a-123">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="fd73a-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="fd73a-124">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="fd73a-124">Task 2: Host the Workflow Designer</span></span>](task-2-host-the-workflow-designer.md)
