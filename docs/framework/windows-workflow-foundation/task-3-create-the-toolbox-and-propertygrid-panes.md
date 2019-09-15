---
title: 'Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche'
ms.date: 03/30/2017
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
ms.openlocfilehash: 6339969c52a5c4eedfb0e89eebdc982ca3fe6686
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988712"
---
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche
In dieser Aufgabe erstellen Sie die **Toolbox** -und **PropertyGrid** -Bereiche und fügen Sie der neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]hinzu.  
  
 Der Code, der in der MainWindow.XAML.cs-Datei enthalten sein sollte, nachdem er die drei Aufgaben im [erneuten Hosting der Workflow-Designer](rehosting-the-workflow-designer.md) Reihe von Themen ausgeführt hat, wird am Ende dieses Themas bereitgestellt.  
  
### <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.  
  
1. Öffnen Sie das HostingApplication-Projekt, das Sie abgerufen haben, [indem Sie das in Aufgabe 2 beschriebene Verfahren befolgen: Hosten Sie](task-2-host-the-workflow-designer.md)die Workflow-Designer.  
  
2. Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei "MainWindow. XAML", und wählen Sie **Code anzeigen**aus.  
  
3. `MainWindow` <xref:System.Activities.Presentation.Toolbox.ToolboxControl> <xref:System.Activities.Statements.Assign> <xref:System.Activities.Statements.Sequence>FügenSie der Klasse, die einen erstellt, eine- Methodehinzu,fügtderToolboxeineneueToolboxKategoriehinzu,undweistder-Klassedie-Aktivitätunddie-Aktivität`GetToolboxControl` zu.  
  
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
  
4. Fügen Sie der `AddToolbox` `MainWindow` Klasse eine private Methode hinzu, die die **Toolbox** in der linken Spalte des Rasters platziert.  
  
    ```csharp  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
    ```  
  
5. Fügen Sie der `AddToolBox`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
    ```csharp  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
    ```  
  
6. Drücken Sie F5, um die Lösung zu erstellen und auszuführen. Die **Toolbox** mit den <xref:System.Activities.Statements.Assign> Aktivitäten <xref:System.Activities.Statements.Sequence> und sollte angezeigt werden.  
  
### <a name="to-create-the-propertygrid"></a>So erstellen Sie den PropertyGrid  
  
1. Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei "MainWindow. XAML", und wählen Sie **Code anzeigen**aus.  
  
2. Fügen Sie `AddPropertyInspector` der- `MainWindow` Klasse die-Methode hinzu, um den Bereich **PropertyGrid** in der Spalte ganz rechts im Raster zu platzieren.  
  
    ```csharp  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
    ```  
  
3. Fügen Sie der `AddPropertyInspector`-Methode im `MainWindow()`-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
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
  
4. Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen. Die **Toolbox**, der Workflow Entwurfs Bereich und der **PropertyGrid** -Bereich sollten alle angezeigt werden, und wenn Sie <xref:System.Activities.Statements.Assign> eine Aktivität oder <xref:System.Activities.Statements.Sequence> eine-Aktivität auf den Entwurfs Bereich ziehen, sollte das Eigenschaften Raster abhängig von der hervorgehobene Aktivität.  
  
## <a name="example"></a>Beispiel  
 Die Datei "MainWindow.xaml.cs" sollte jetzt den folgenden Code enthalten.  
  
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

- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation Anwendung](task-1-create-a-new-wpf-app.md)
- [Aufgabe 2: Hosten des Workflow-Designer](task-2-host-the-workflow-designer.md)
