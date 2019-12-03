---
title: 'Aufgabe 2: Hosten des Workflow-Designers'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 8e4c17ed182cec7748b9a1f11f76ff90aa60c39e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715791"
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="e97c5-102">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="e97c5-102">Task 2: Host the Workflow Designer</span></span>

<span data-ttu-id="e97c5-103">In diesem Thema wird das Verfahren zum Hosting einer Instanz des Windows-Workflow-Designer in einer Windows Presentation Foundation (WPF)-Anwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e97c5-103">This topic describes the procedure for hosting an instance of the Windows Workflow Designer in a Windows Presentation Foundation (WPF) application.</span></span>

<span data-ttu-id="e97c5-104">Die Prozedur konfiguriert das **Raster** Steuerelement, das den Designer enthält, erstellt Programm gesteuert eine Instanz der <xref:System.Activities.Presentation.WorkflowDesigner>, die eine standardmäßige <xref:System.Activities.Statements.Sequence> Aktivität enthält, registriert die Designer Metadaten, um Designer Unterstützung für alle integrierten Aktivitäten bereitzustellen, und hostet die Workflow-Designer in der WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e97c5-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the Workflow Designer in the WPF application.</span></span>

## <a name="to-host-the-workflow-designer"></a><span data-ttu-id="e97c5-105">So hosten Sie den Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="e97c5-105">To host the workflow designer</span></span>

1. <span data-ttu-id="e97c5-106">Öffnen Sie das HostingApplication-Projekt, das Sie in [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation Anwendung](task-1-create-a-new-wpf-app.md)erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e97c5-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](task-1-create-a-new-wpf-app.md).</span></span>

2. <span data-ttu-id="e97c5-107">Passen Sie die Größe des Fensters an, um die Verwendung des Workflow-Designer zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-107">Adjust the size of the window to make it easier to use the Workflow Designer.</span></span> <span data-ttu-id="e97c5-108">Wählen Sie hierzu im Designer **MainWindow** , drücken Sie F4, um das **Eigenschaften** Fenster anzuzeigen, und legen Sie im Abschnitt **Layout** die **Breite** auf den Wert 600 und die **Höhe** auf 350 fest.</span><span class="sxs-lookup"><span data-stu-id="e97c5-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>

3. <span data-ttu-id="e97c5-109">Legen Sie den Raster Namen fest, indem Sie im Designer den **Raster** Bereich auswählen (Klicken Sie auf das Feld im **MainWindow**), und legen Sie die **Name** -Eigenschaft oben im **Eigenschaften** Fenster auf "grid1" fest.</span><span class="sxs-lookup"><span data-stu-id="e97c5-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>

4. <span data-ttu-id="e97c5-110">Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte ( **...** ) neben der `ColumnDefinitions`-Eigenschaft, um das Dialogfeld Auflistungs- **Editor** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>

5. <span data-ttu-id="e97c5-111">Klicken Sie im Dialogfeld Auflistungs- **Editor** drei Mal auf die Schaltfläche **Hinzufügen** , um drei Spalten in das Layout einzufügen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="e97c5-112">Die erste Spalte enthält die **Toolbox**, die zweite Spalte hostet die Workflow-Designer, und die dritte Spalte wird für die Eigenschaften Analyse verwendet.</span><span class="sxs-lookup"><span data-stu-id="e97c5-112">The first column will contain the **Toolbox**, the second column will host the Workflow Designer, and the third column will be used for the property inspector.</span></span>

6. <span data-ttu-id="e97c5-113">Legen Sie die `Width`-Eigenschaft der mittleren Spalte auf den Wert "4 \*" fest.</span><span class="sxs-lookup"><span data-stu-id="e97c5-113">Set the `Width` property of the middle column to the value "4\*".</span></span>

7. <span data-ttu-id="e97c5-114">Klicken Sie auf **OK** , um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e97c5-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="e97c5-115">Der folgenden XAML-Code wird der Datei " *MainWindow. XAML* " hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e97c5-115">The following XAML is added to your *MainWindow.xaml* file:</span></span>

    ```xaml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. <span data-ttu-id="e97c5-116">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf *MainWindow. XAML* , und wählen Sie **Code anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="e97c5-116">In **Solution Explorer**, right-click *MainWindow.xaml* and select **View Code**.</span></span> <span data-ttu-id="e97c5-117">Ändern Sie den Code, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e97c5-117">Modify the code by following these steps:</span></span>

    1. <span data-ttu-id="e97c5-118">Fügen Sie die folgenden Namespaces hinzu:</span><span class="sxs-lookup"><span data-stu-id="e97c5-118">Add the following namespaces:</span></span>

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. <span data-ttu-id="e97c5-119">Fügen Sie der `MainWindow`-Klasse den folgenden Code hinzu, um ein privates Member-Feld zu deklarieren, das eine Instanz des <xref:System.Activities.Presentation.WorkflowDesigner>enthalten soll:</span><span class="sxs-lookup"><span data-stu-id="e97c5-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class:</span></span>

        ```csharp
        public partial class MainWindow : Window
        {
            private WorkflowDesigner wd;

            public MainWindow()
            {
                InitializeComponent();
            }
        }
        ```

    3. <span data-ttu-id="e97c5-120">Fügen Sie die folgende `AddDesigner`-Methode zu der `MainWindow`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="e97c5-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="e97c5-121">Die-Implementierung erstellt eine Instanz des <xref:System.Activities.Presentation.WorkflowDesigner>, fügt ihr eine <xref:System.Activities.Statements.Sequence>-Aktivität hinzu und platziert Sie in der mittleren Spalte des grid1- **Rasters**.</span><span class="sxs-lookup"><span data-stu-id="e97c5-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>

        ```csharp
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
        ```

    4. <span data-ttu-id="e97c5-122">Registrieren Sie die Designer-Metadaten, um Designerunterstützung für alle integrierten Aktivitäten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="e97c5-123">Auf diese Weise können Sie Aktivitäten aus der Toolbox auf die ursprüngliche <xref:System.Activities.Statements.Sequence> Aktivität in der Workflow-Designer ablegen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the Workflow Designer.</span></span> <span data-ttu-id="e97c5-124">Fügen Sie zu diesem Zweck der `MainWindow`-Klasse die `RegisterMetadata`-Methode hinzu:</span><span class="sxs-lookup"><span data-stu-id="e97c5-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class:</span></span>

        ```csharp
        private void RegisterMetadata()
        {
            var dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        <span data-ttu-id="e97c5-125">Weitere Informationen zum Registrieren von Aktivitäts Designern finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten Aktivitäts Designers](how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e97c5-125">For more information about registering activity designers, see [How to: Create a Custom Activity Designer](how-to-create-a-custom-activity-designer.md).</span></span>

    5. <span data-ttu-id="e97c5-126">Fügen Sie im `MainWindow`-Klassenkonstruktor den zuvor deklarierten Methoden Aufrufe hinzu, um die Metadaten für die Designerunterstützung zu registrieren und das <xref:System.Activities.Presentation.WorkflowDesigner>-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>

        ```csharp
        public MainWindow()
        {
            InitializeComponent();

            // Register the metadata.
            RegisterMetadata();

            // Add the WFF Designer.
            AddDesigner();
        }
        ```

        > [!NOTE]
        > <span data-ttu-id="e97c5-127">Die `RegisterMetadata`-Methode registriert die Designer-Metadaten integrierter Aktivitäten, einschließlich der <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="e97c5-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="e97c5-128">Da die `AddDesigner`-Methode die <xref:System.Activities.Statements.Sequence>-Aktivität verwendet, muss die `RegisterMetadata`-Methode zuerst aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e97c5-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>

9. <span data-ttu-id="e97c5-129">Drücken Sie <kbd>F5</kbd> , um die Projekt Mappe zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e97c5-129">Press <kbd>F5</kbd> to build and run the solution.</span></span>

10. <span data-ttu-id="e97c5-130">Weitere Informationen zum Hinzufügen von **Toolbox** -und **PropertyGrid** -Unterstützung zu Ihrem neu gehosteten Workflow-Designer finden Sie unter [Aufgabe 3: Erstellen der Toolbox-und PropertyGrid-](task-3-create-the-toolbox-and-propertygrid-panes.md) Bereiche.</span><span class="sxs-lookup"><span data-stu-id="e97c5-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="e97c5-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e97c5-131">See also</span></span>

- [<span data-ttu-id="e97c5-132">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="e97c5-132">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)
- [<span data-ttu-id="e97c5-133">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e97c5-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](task-1-create-a-new-wpf-app.md)
- [<span data-ttu-id="e97c5-134">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="e97c5-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](task-3-create-the-toolbox-and-propertygrid-panes.md)
