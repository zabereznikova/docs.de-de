---
title: 'Aufgabe 2: Hosten des Workflow-Designers'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 15fa4372f4a110577f055d0e3c22977d0f5417bb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="task-2-host-the-workflow-designer"></a><span data-ttu-id="c9dd0-102">Aufgabe 2: Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="c9dd0-102">Task 2: Host the Workflow Designer</span></span>
<span data-ttu-id="c9dd0-103">In diesem Thema wird beschrieben, die Prozedur zum Hosten einer Instanz von der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in einer Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-103">This topic describes the procedure for hosting an instance of the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in a Windows Presentation Foundation (WPF) application.</span></span>  
  
 <span data-ttu-id="c9dd0-104">Das Verfahren konfiguriert die **Raster** Steuerelement, das den Designer enthält erstellt programmgesteuert eine Instanz der <xref:System.Activities.Presentation.WorkflowDesigner> , enthält den Standardwert <xref:System.Activities.Statements.Sequence> Aktivität, registriert die Designermetadaten bereitstellen designerunterstützung für alle integrierten Aktivitäten und Hosts die [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in die [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-104">The procedure configures the **Grid** control that contains the designer, programmatically creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner> that contains a default <xref:System.Activities.Statements.Sequence> activity, registers the designer metadata to provide designer support for all built-in activities, and hosts the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in the [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] application.</span></span>  
  
### <a name="to-host-the-workflow-designer"></a><span data-ttu-id="c9dd0-105">So hosten Sie den Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="c9dd0-105">To host the workflow designer</span></span>  
  
1.  <span data-ttu-id="c9dd0-106">Öffnen der HostingApplication Projekt erstellten [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).</span><span class="sxs-lookup"><span data-stu-id="c9dd0-106">Open the HostingApplication project you created in [Task 1: Create a New Windows Presentation Foundation Application](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md).</span></span>  
  
2.  <span data-ttu-id="c9dd0-107">Passen Sie die Fenstergröße an, um die Verwendung des [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] einfacher zu machen.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-107">Adjust the size of the window to make it easier to use the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="c9dd0-108">Zu diesem Zweck wählen **MainWindow** im Designer, drücken Sie F4, um die **Eigenschaften** Fenster, und in der **Layout** Abschnitt vorhanden, legen Sie die **Breite** auf einen Wert von 600 und die **Höhe** auf einen Wert von 350.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-108">To do this, select **MainWindow** in the designer, press F4 to display the **Properties** window, and, in the **Layout** section there, set the **Width** to a value of 600 and the **Height** to a value of 350.</span></span>  
  
3.  <span data-ttu-id="c9dd0-109">Legen Sie den rasternamen, indem Sie auswählen der **Raster** Bereich im Designer (klicken Sie auf das Feld innerhalb der **MainWindow**) verwendet wird und die **Namen** Eigenschaft am oberen Rand der  **Eigenschaften** Fenster auf "grid1".</span><span class="sxs-lookup"><span data-stu-id="c9dd0-109">Set the grid name by selecting the **Grid** panel in the designer (click the box inside the **MainWindow**) and setting the **Name** property at the top of the **Properties** window to "grid1".</span></span>  
  
4.  <span data-ttu-id="c9dd0-110">In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte (**...** ) neben der `ColumnDefinitions` Eigenschaft so öffnen die **Auflistungs-Editor** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c9dd0-110">In the **Properties** window, click the ellipsis (**…**) next to the `ColumnDefinitions` property to open the **Collection Editor** dialog box.</span></span>  
  
5.  <span data-ttu-id="c9dd0-111">In der **Auflistungs-Editor** (Dialogfeld), klicken Sie auf die **hinzufügen** Schaltfläche dreimal so fügen Sie drei Spalten in das Layout.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-111">In the **Collection Editor** dialog box, click the **Add** button three times to insert three columns into the layout.</span></span> <span data-ttu-id="c9dd0-112">Die erste Spalte enthält die **Toolbox**, die zweite Spalte die [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], und die dritte Spalte die Eigenschaftenanalyse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-112">The first column will contain the **Toolbox**, the second column will host the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], and the third column will be used for the property inspector.</span></span>  
  
6.  <span data-ttu-id="c9dd0-113">Legen Sie die `Width` -Eigenschaft der mittleren Spalte auf den Wert "4 \*".</span><span class="sxs-lookup"><span data-stu-id="c9dd0-113">Set the `Width` property of the middle column to the value "4\*".</span></span>  
  
7.  <span data-ttu-id="c9dd0-114">Klicken Sie auf **OK** um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-114">Click **OK** to save the changes.</span></span> <span data-ttu-id="c9dd0-115">Der Datei "MainWindow.xaml" wird der folgende XAML-Code hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="c9dd0-115">The following XAML is added to your MainWindow.xaml file:</span></span>  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8.  <span data-ttu-id="c9dd0-116">In **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei "MainWindow.xaml", und wählen Sie **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-116">In **Solution Explorer**, right-click MainWindow.xaml and select **View Code**.</span></span> <span data-ttu-id="c9dd0-117">Ändern Sie den Code, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9dd0-117">Modify the code by following these steps:</span></span>  
  
    1.  <span data-ttu-id="c9dd0-118">Fügen Sie die folgenden Namespaces hinzu:</span><span class="sxs-lookup"><span data-stu-id="c9dd0-118">Add the following namespaces:</span></span>  
  
        ```csharp  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
        ```  
  
    2.  <span data-ttu-id="c9dd0-119">Um ein privates Memberfeld zu deklarieren, das eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> enthalten soll, fügen Sie der `MainWindow`-Klasse den folgenden Code hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-119">To declare a private member field to hold an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, add the following code to the `MainWindow` class.</span></span>  
  
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
  
    3.  <span data-ttu-id="c9dd0-120">Fügen Sie die folgende `AddDesigner`-Methode zu der `MainWindow`-Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-120">Add the following `AddDesigner` method to the `MainWindow` class.</span></span> <span data-ttu-id="c9dd0-121">Die Implementierung erstellt eine Instanz der <xref:System.Activities.Presentation.WorkflowDesigner>, fügt eine <xref:System.Activities.Statements.Sequence> -Aktivität hinzu und platziert sie in der mittleren Spalte "grid1" **Raster**.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-121">The implementation creates an instance of the <xref:System.Activities.Presentation.WorkflowDesigner>, adds a <xref:System.Activities.Statements.Sequence> activity to it, and places it in middle column of the grid1 **Grid**.</span></span>  
  
        ```csharp  
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
        ```  
  
    4.  <span data-ttu-id="c9dd0-122">Registrieren Sie die Designer-Metadaten, um Designerunterstützung für alle integrierten Aktivitäten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-122">Register the designer metadata to add designer support for all the  built-in activities.</span></span> <span data-ttu-id="c9dd0-123">Dies ermöglicht Ihnen, Aktivitäten aus der Toolbox auf der ursprünglichen <xref:System.Activities.Statements.Sequence>-Aktivität im [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] abzulegen.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-123">This enables you to drop activities from the toolbox onto the original <xref:System.Activities.Statements.Sequence> activity in the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)].</span></span> <span data-ttu-id="c9dd0-124">Fügen Sie hierzu der `RegisterMetadata`-Klasse die `MainWindow`-Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-124">To do this, add the `RegisterMetadata` method to the `MainWindow` class.</span></span>  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="c9dd0-125"> Registrieren die Aktivitäts-Designer, finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c9dd0-125"> registering activity designers, see [How to: Create a Custom Activity Designer](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-activity-designer.md).</span></span>  
  
    5.  <span data-ttu-id="c9dd0-126">Fügen Sie im `MainWindow`-Klassenkonstruktor den zuvor deklarierten Methoden Aufrufe hinzu, um die Metadaten für die Designerunterstützung zu registrieren und das <xref:System.Activities.Presentation.WorkflowDesigner>-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-126">In the `MainWindow` class constructor, add calls to the methods declared previously to register the metadata for designer support and to create the <xref:System.Activities.Presentation.WorkflowDesigner>.</span></span>  
  
        ```csharp  
        public MainWindow()  
        {  
            InitializeComponent();  
  
            // Register the metadata  
            RegisterMetadata();  
  
            // Add the WFF Designer  
            AddDesigner();  
        }  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="c9dd0-127">Die `RegisterMetadata`-Methode registriert die Designer-Metadaten integrierter Aktivitäten, einschließlich der <xref:System.Activities.Statements.Sequence>-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-127">The `RegisterMetadata` method registers the designer metadata of built-in activities including the <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="c9dd0-128">Da die `AddDesigner`-Methode die <xref:System.Activities.Statements.Sequence>-Aktivität verwendet, muss die `RegisterMetadata`-Methode zuerst aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-128">Because the `AddDesigner` method uses the <xref:System.Activities.Statements.Sequence> activity, the `RegisterMetadata` method must be called first.</span></span>  
  
9. <span data-ttu-id="c9dd0-129">Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-129">Press F5 to build and run the solution.</span></span>  
  
10. <span data-ttu-id="c9dd0-130">Finden Sie unter [Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) Informationen zum Hinzufügen **Toolbox** und **PropertyGrid** dem neu gehosteten Workflow-Designer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9dd0-130">See [Task 3: Create the Toolbox and PropertyGrid Panes](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md) to learn how to add **Toolbox** and **PropertyGrid** support to your rehosted workflow designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9dd0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9dd0-131">See Also</span></span>  
 [<span data-ttu-id="c9dd0-132">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="c9dd0-132">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 [<span data-ttu-id="c9dd0-133">Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung</span><span class="sxs-lookup"><span data-stu-id="c9dd0-133">Task 1: Create a New Windows Presentation Foundation Application</span></span>](../../../docs/framework/windows-workflow-foundation/task-1-create-a-new-wpf-app.md)  
 [<span data-ttu-id="c9dd0-134">Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche</span><span class="sxs-lookup"><span data-stu-id="c9dd0-134">Task 3: Create the Toolbox and PropertyGrid Panes</span></span>](../../../docs/framework/windows-workflow-foundation/task-3-create-the-toolbox-and-propertygrid-panes.md)
