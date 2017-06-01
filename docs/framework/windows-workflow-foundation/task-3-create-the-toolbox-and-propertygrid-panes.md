---
title: "Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72c1546a-eed5-4f0f-a616-719a163414f4
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche
In dieser Aufgabe erstellen Sie die Bereiche **Toolbox** und **PropertyGrid** und fügen sie dem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] hinzu.  
  
 Als Referenz wird am Ende dieses Themas der Code bereitgestellt, der nach Abschluss der drei Aufgaben in der Reihe [Erneutes Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md) von Themen in der Datei "MainWindow.xaml.cs" vorhanden sein sollte.  
  
### So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.  
  
1.  Öffnen Sie das Projekt "HostingApplication", das Sie erhalten haben, indem Sie das in [Aufgabe 2: Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md) beschriebene Verfahren ausgeführt haben.  
  
2.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei "MainWindow.xaml", und wählen Sie **Code anzeigen** aus.  
  
3.  Fügen Sie eine Methode namens `GetToolboxControl` der `MainWindow`\-Klasse hinzu, mit der ein <xref:System.Activities.Presentation.Toolbox.ToolboxControl>\-Objekt erstellt wird, der **Toolbox** eine neue **Toolbox**\-Kategorie hinzugefügt wird und dieser Kategorie der <xref:System.Activities.Statements.Assign>\-Aktivitätstyp und der <xref:System.Activities.Statements.Sequence>\-Aktivitätstyp hinzugefügt wird.  
  
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
  
4.  Fügen Sie der `MainWindow`\-Klasse eine private `AddToolbox`\-Methode hinzu, um die **Toolbox** in der linken Spalte des Rasters einzufügen.  
  
    ```csharp  
  
    private void AddToolBox()  
    {  
        ToolboxControl tc = GetToolboxControl();  
        Grid.SetColumn(tc, 0);  
        grid1.Children.Add(tc);  
    }  
  
    ```  
  
5.  Fügen Sie der `AddToolBox`\-Methode im `MainWindow()`\-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
    ```csharp  
  
    public MainWindow()  
    {  
        InitializeComponent();  
        this.RegisterMetadata();  
        this.AddDesigner();  
  
        this.AddToolBox();  
    }  
  
    ```  
  
6.  Drücken Sie F5, um die Lösung zu erstellen und auszuführen.Die **Toolbox** mit der <xref:System.Activities.Statements.Assign>\-Aktivität und der <xref:System.Activities.Statements.Sequence>\-Aktivität wird angezeigt.  
  
### So erstellen Sie den PropertyGrid  
  
1.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf die Datei "MainWindow.xaml", und wählen Sie **Code anzeigen** aus.  
  
2.  Fügen Sie der `MainWindow`\-Klasse die `AddPropertyInspector`\-Methode hinzu, um den Bereich **PropertyGrid** in der Spalte ganz rechts im Raster einzufügen.  
  
    ```csharp  
  
    private void AddPropertyInspector()  
    {  
        Grid.SetColumn(wd.PropertyInspectorView, 2);  
        grid1.Children.Add(wd.PropertyInspectorView);              
    }  
  
    ```  
  
3.  Fügen Sie der `AddPropertyInspector`\-Methode im `MainWindow()`\-Klassenkonstruktor einen Aufruf hinzu, wie im folgenden Code gezeigt.  
  
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
  
4.  Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.Die **Toolbox**, der Entwurfszeichnungsbereich des Workflows und die **PropertyGrid**\-Bereiche werden normalerweise alle angezeigt, und wenn Sie eine <xref:System.Activities.Statements.Assign>\-Aktivität oder eine <xref:System.Activities.Statements.Sequence>\-Aktivität auf den Entwurfszeichnungsbereich ziehen, wird das Eigenschaftenraster je nach markierter Aktivität aktualisiert.  
  
## Beispiel  
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
  
## Siehe auch  
 [Erneutes Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation\-Anwendung](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Aufgabe 2: Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//task-2-host-the-workflow-designer.md)