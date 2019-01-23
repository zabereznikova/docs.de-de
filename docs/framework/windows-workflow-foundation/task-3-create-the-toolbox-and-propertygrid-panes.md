---
title: 'Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 8e332c2caa43e1c9703272d7f2be16b545c44fd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558422"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a><span data-ttu-id="04084-102">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="04084-102">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>
<span data-ttu-id="04084-103">In dieser Aufgabe erstellen Sie die **Toolbox** und **PropertyGrid** Bereiche und fügen sie dem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04084-103">In this task, you will create the **Toolbox** and **PropertyGrid** panes and add them to the rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span>  
  
 <span data-ttu-id="04084-104">Referenz zu der Code, der in der Datei "MainWindow.Xaml.cs" werden sollen, nach Abschluss der drei Aufgaben, in der [erneutes Hosten von Workflow-Designer](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) Reihe von Themen am Ende dieses Themas bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="04084-104">For reference, the code that should be in the MainWindow.xaml.cs file after completing the three tasks in the [Rehosting the Workflow Designer](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) series of topics is provided at the end of this topic.</span></span>  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a><span data-ttu-id="04084-105">So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.</span><span class="sxs-lookup"><span data-stu-id="04084-105">To create the Toolbox and add it to the grid</span></span>  
  
1.  <span data-ttu-id="04084-106">Öffnen Sie das HostingApplication-Projekt, das Sie erworben haben, gemäß das Verfahren in [Aufgabe 2: Hosten des Workflowdesigners](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="04084-106">Open the HostingApplication project you obtained by following the procedure described in [Task 2: Host the Workflow Designer](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).</span></span>  
  
2.  <span data-ttu-id="04084-107">In der **Projektmappen-Explorer** Bereich mit der rechten Maustaste in der Datei "MainWindow.xaml", und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="04084-107">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
3.  <span data-ttu-id="04084-108">Hinzufügen einer `GetToolboxControl` Methode, um die `MainWindow` Klasse, die erstellt eine <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, fügt ein neues **Toolbox** Kategorie, um die **Toolbox**, und weist die <xref:System.Activities.Statements.Assign> und <xref:System.Activities.Statements.Sequence> Aktivitätstypen für die auf diese Kategorie.</span><span class="sxs-lookup"><span data-stu-id="04084-108">Add a `GetToolboxControl` method to the `MainWindow` class that creates a <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, adds a new **Toolbox** category to the **Toolbox**, and assigns the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activity types to that category.</span></span>  
  
    ```csharp  
    private ToolboxControl GetToolboxControl()  
    {  
        // Create the ToolBoxControl.  
        ToolboxControl ctrl = new ToolboxControl();  
  
        // Create a category.  
        ToolboxCategory category = new ToolboxCategory("category1");  
  
        // Create Toolbox items.  
        ToolboxItemWrapper tool1 =   
            new ToolboxItemWrapper("System.Activities.Statements.Assign",   
            typeof(Assign).Assembly.FullName, null, "Assign");  
  
        ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",   
            typeof(Sequence).Assembly.FullName, null, "Sequence");  
  
        // Add the Toolbox items to the category.  
        category.Add(tool1);  
        category.Add(tool2);  
  
        // Add the category to the ToolBox control.  
        ctrl.Categories.Add(category);  
        return ctrl;  
    }  
    ```  
  
4.  <span data-ttu-id="04084-109">Hinzufügen eine privaten `AddToolbox` Methode, um die `MainWindow` -Klasse, die platziert die **Toolbox** in der linken Spalte des Rasters.</span><span class="sxs-lookup"><span data-stu-id="04084-109">Add a private `AddToolbox` method to the `MainWindow` class that places the **Toolbox** in the left column on the grid.</span></span>  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  <span data-ttu-id="04084-110">Fügen Sie der `AddToolBox`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="04084-110">Add a call to the `AddToolBox` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  <span data-ttu-id="04084-111">Drücken Sie F5, um die Lösung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="04084-111">Press F5 to build and run your solution.</span></span> <span data-ttu-id="04084-112">Die **Toolbox** , enthält die <xref:System.Activities.Statements.Assign> und <xref:System.Activities.Statements.Sequence> Aktivitäten angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="04084-112">The **Toolbox** containing the <xref:System.Activities.Statements.Assign> and <xref:System.Activities.Statements.Sequence> activities should be displayed.</span></span>  
  
### <a name="to-create-the-propertygrid"></a><span data-ttu-id="04084-113">So erstellen Sie den PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="04084-113">To create the PropertyGrid</span></span>  
  
1.  <span data-ttu-id="04084-114">In der **Projektmappen-Explorer** Bereich mit der rechten Maustaste in der Datei "MainWindow.xaml", und wählen Sie **Ansichtscode**.</span><span class="sxs-lookup"><span data-stu-id="04084-114">In the **Solution Explorer** pane, right-click the MainWindow.xaml file and select **View Code**.</span></span>  
  
2.  <span data-ttu-id="04084-115">Hinzufügen der `AddPropertyInspector` Methode, um die `MainWindow` -Klasse die **PropertyGrid** Bereich in der äußersten rechten Spalte des Rasters.</span><span class="sxs-lookup"><span data-stu-id="04084-115">Add the `AddPropertyInspector` method to the `MainWindow` class to place the **PropertyGrid** pane in the rightmost column on the grid.</span></span>  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  <span data-ttu-id="04084-116">Fügen Sie der `AddPropertyInspector`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="04084-116">Add a call to the `AddPropertyInspector` method in the `MainWindow()` class constructor as shown in the following code.</span></span>  
  
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
  
4.  <span data-ttu-id="04084-117">Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="04084-117">Press F5 to build and run the solution.</span></span> <span data-ttu-id="04084-118">Die **Toolbox**, entwurfszeichnungsbereich des Workflows und **PropertyGrid** sollte alle Bereiche angezeigt werden, und Sie ziehen, wenn ein <xref:System.Activities.Statements.Assign> Aktivität oder eine <xref:System.Activities.Statements.Sequence> Aktivität auf der Entwurfs-Canvas die Eigenschaftenraster sollte je nach markierter Aktivität aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="04084-118">The **Toolbox**, workflow design canvas, and **PropertyGrid** panes should all be displayed, and when you drag an <xref:System.Activities.Statements.Assign> activity or a <xref:System.Activities.Statements.Sequence> activity onto the design canvas, the property grid should update depending on the highlighted activity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04084-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04084-119">Example</span></span>  
 <span data-ttu-id="04084-120">Die Datei "MainWindow.xaml.cs" sollte jetzt den folgenden Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="04084-120">The MainWindow.xaml.cs file should now contain the following code.</span></span>  
  
```  
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
//dlls added  
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
            //Create an instance of WorkflowDesigner class.  
            this.wd = new WorkflowDesigner();  
  
            //Place the designer canvas in the middle column of the grid.  
            Grid.SetColumn(this.wd.View, 1);  
  
            //Load a new Sequence as default.  
            this.wd.Load(new Sequence());  
  
            //Add the designer canvas to the grid.  
            grid1.Children.Add(this.wd.View);  
        }  
  
        private void RegisterMetadata()  
        {  
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        private ToolboxControl GetToolboxControl()  
        {  
            // Create the ToolBoxControl.  
            ToolboxControl ctrl = new ToolboxControl();  
  
            // Create a category.  
            ToolboxCategory category = new ToolboxCategory("category1");  
  
            // Create Toolbox items.  
            ToolboxItemWrapper tool1 =  
                new ToolboxItemWrapper("System.Activities.Statements.Assign",  
                typeof(Assign).Assembly.FullName, null, "Assign");  
  
            ToolboxItemWrapper tool2 = new ToolboxItemWrapper("System.Activities.Statements.Sequence",  
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
  
## <a name="see-also"></a><span data-ttu-id="04084-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04084-121">See also</span></span>
- [<span data-ttu-id="04084-122">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="04084-122">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)
- [<span data-ttu-id="04084-123">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="04084-123">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="04084-124">Task 2: Hosten des Workflowdesigners</span><span class="sxs-lookup"><span data-stu-id="04084-124">Task 2: Host the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
