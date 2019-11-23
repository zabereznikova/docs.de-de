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
# <a name="task-3-create-the-toolbox-and-propertygrid-panes"></a>Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche

In dieser Aufgabe erstellen Sie die **Toolbox** -und **PropertyGrid** -Bereiche und fügen Sie dem neu gehosteten [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]hinzu.

Der Code, der in der MainWindow.XAML.cs-Datei enthalten sein sollte, nachdem er die drei Aufgaben im [erneuten Hosting der Workflow-Designer](rehosting-the-workflow-designer.md) Reihe von Themen ausgeführt hat, wird am Ende dieses Themas bereitgestellt.

## <a name="to-create-the-toolbox-and-add-it-to-the-grid"></a>So erstellen Sie die Toolbox und fügen sie dem Raster hinzu.

1. Öffnen Sie das HostingApplication-Projekt, das Sie abgerufen haben, indem Sie das in [Aufgabe 2: Hosten des Workflow-Designer](task-2-host-the-workflow-designer.md)beschriebene Verfahren befolgen.

2. Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei " *MainWindow. XAML* ", und wählen Sie **Code anzeigen**aus.

3. Fügen Sie der `MainWindow` Klasse, die einen <xref:System.Activities.Presentation.Toolbox.ToolboxControl>erstellt, eine `GetToolboxControl` Methode hinzu, fügt der **Toolbox**eine neue **Toolbox** Kategorie hinzu, und weist der Kategorie die <xref:System.Activities.Statements.Assign>-und <xref:System.Activities.Statements.Sequence> Aktivitätstypen zu.

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

4. Fügen Sie der `MainWindow` Klasse eine private `AddToolbox` Methode hinzu, die die **Toolbox** in der linken Spalte des Rasters platziert.

    ```csharp
    private void AddToolBox()
    {
        ToolboxControl tc = GetToolboxControl();
        Grid.SetColumn(tc, 0);
        grid1.Children.Add(tc);
    }
    ```

5. Fügen Sie im `MainWindow()`-Klassenkonstruktor einen aufzurufenden `AddToolBox`-Methode hinzu, wie im folgenden Code gezeigt:

    ```csharp
    public MainWindow()
    {
        InitializeComponent();
        this.RegisterMetadata();
        this.AddDesigner();

        this.AddToolBox();
    }
    ```

6. Drücken Sie <kbd>F5</kbd> , um die Projekt Mappe zu erstellen und auszuführen. Die **Toolbox** mit den <xref:System.Activities.Statements.Assign>-und <xref:System.Activities.Statements.Sequence> Aktivitäten sollte angezeigt werden.

## <a name="to-create-the-propertygrid"></a>So erstellen Sie den PropertyGrid

1. Klicken Sie im **Projektmappen-Explorer** Bereich mit der rechten Maustaste auf die Datei " *MainWindow. XAML* ", und wählen Sie **Code anzeigen**aus.

2. Fügen Sie der `MainWindow` Klasse die `AddPropertyInspector`-Methode hinzu, um den Bereich **PropertyGrid** in der Spalte ganz rechts im Raster zu platzieren:

    ```csharp
    private void AddPropertyInspector()
    {
        Grid.SetColumn(wd.PropertyInspectorView, 2);
        grid1.Children.Add(wd.PropertyInspectorView);
    }
    ```

3. Fügen Sie im `MainWindow()`-Klassenkonstruktor einen aufzurufenden `AddPropertyInspector`-Methode hinzu, wie im folgenden Code gezeigt:

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

4. Drücken Sie <kbd>F5</kbd> , um die Projekt Mappe zu erstellen und auszuführen. Die **Toolbox**, der Workflow Entwurfs Bereich und der **PropertyGrid** -Bereich sollten alle angezeigt werden, und wenn Sie eine <xref:System.Activities.Statements.Assign> Aktivität oder eine <xref:System.Activities.Statements.Sequence> Aktivität auf den Entwurfs Bereich ziehen, sollte das Eigenschaften Raster abhängig von der hervorgehobenen Aktivität aktualisiert werden.

## <a name="example"></a>Beispiel

Die *MainWindow.XAML.cs* -Datei sollte jetzt den folgenden Code enthalten:

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

## <a name="see-also"></a>Siehe auch

- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung](task-1-create-a-new-wpf-app.md)
- [Aufgabe 2: Hosten des Workflow-Designers](task-2-host-the-workflow-designer.md)
