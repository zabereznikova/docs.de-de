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
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche
In dieser Aufgabe erstellen Sie die **Toolbox** und **PropertyGrid** Bereiche und fügen sie dem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].  
  
 Referenz zu der Code, der in der Datei "MainWindow.Xaml.cs" werden sollen, nach Abschluss der drei Aufgaben, in der [erneutes Hosten von Workflow-Designer](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md) Reihe von Themen am Ende dieses Themas bereitgestellt wird.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.  
  
1.  Öffnen Sie das HostingApplication-Projekt, das Sie erworben haben, gemäß das Verfahren in [Aufgabe 2: Hosten des Workflowdesigners](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md).  
  
2.  In der **Projektmappen-Explorer** Bereich mit der rechten Maustaste in der Datei "MainWindow.xaml", und wählen Sie **Ansichtscode**.  
  
3.  Hinzufügen einer `GetToolboxControl` Methode, um die `MainWindow` Klasse, die erstellt eine <xref:System.Activities.Presentation.Toolbox.ToolboxControl>, fügt ein neues **Toolbox** Kategorie, um die **Toolbox**, und weist die <xref:System.Activities.Statements.Assign> und <xref:System.Activities.Statements.Sequence> Aktivitätstypen für die auf diese Kategorie.  
  
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
  
4.  Hinzufügen eine privaten `AddToolbox` Methode, um die `MainWindow` -Klasse, die platziert die **Toolbox** in der linken Spalte des Rasters.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5.  Fügen Sie der `AddToolBox`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6.  Drücken Sie F5, um die Lösung zu erstellen und auszuführen. Die **Toolbox** , enthält die <xref:System.Activities.Statements.Assign> und <xref:System.Activities.Statements.Sequence> Aktivitäten angezeigt werden soll.  
  
### <a name="to-create-the-propertygrid"></a>So erstellen Sie den PropertyGrid  
  
1.  In der **Projektmappen-Explorer** Bereich mit der rechten Maustaste in der Datei "MainWindow.xaml", und wählen Sie **Ansichtscode**.  
  
2.  Hinzufügen der `AddPropertyInspector` Methode, um die `MainWindow` -Klasse die **PropertyGrid** Bereich in der äußersten rechten Spalte des Rasters.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3.  Fügen Sie der `AddPropertyInspector`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
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
  
4.  Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen. Die **Toolbox**, entwurfszeichnungsbereich des Workflows und **PropertyGrid** sollte alle Bereiche angezeigt werden, und Sie ziehen, wenn ein <xref:System.Activities.Statements.Assign> Aktivität oder eine <xref:System.Activities.Statements.Sequence> Aktivität auf der Entwurfs-Canvas die Eigenschaftenraster sollte je nach markierter Aktivität aktualisiert werden.  
  
## <a name="example"></a>Beispiel  
 Die Datei "MainWindow.xaml.cs" sollte jetzt den folgenden Code enthalten.  
  
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
  
## <a name="see-also"></a>Siehe auch
- [Erneutes Hosten des Workflow-Designers](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)
- [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)
- [Task 2: Hosten des Workflowdesigners](../../../docs/framework/windows-workflow-foundation/task-2-host-the-workflow-designer.md)
