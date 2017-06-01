---
title: "Aufgabe 2: Hosten des Workflow-Designers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Aufgabe 2: Hosten des Workflow-Designers
In diesem Thema wird die Prozedur zum Hosten einer Instanz von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in einer [!INCLUDE[avalon1](../../../includes/avalon1-md.md)]\-Anwendung beschrieben.  
  
 Die Prozedur konfiguriert das **Raster**\-Steuerelement, das den Designer enthält, erstellt programmgesteuert eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> mit einer standardmäßigen <xref:System.Activities.Statements.Sequence>\-Aktivität, registriert die Designermetadaten, um Designerunterstützung für alle integrierten Aktivitäten zu bieten, und hostet den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in der [!INCLUDE[avalon2](../../../includes/avalon2-md.md)]\-Anwendung.  
  
### So hosten Sie den Workflow\-Designer  
  
1.  Öffnen Sie das HostingApplication\-Projekt, das Sie in [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation\-Anwendung](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md) erstellt haben.  
  
2.  Passen Sie die Fenstergröße an, um die Verwendung des [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] einfacher zu machen.Wählen Sie hierzu im Designer **MainWindow**, drücken Sie F4, um das Fenster **Eigenschaften** zu öffnen, und legen Sie im Abschnitt **Layout** in diesem Fenster die **Breite** auf 600 und die **Höhe** auf 350 fest.  
  
3.  Definieren Sie den Rasternamen, indem Sie im Designer auf den **Raster**\-Bereich klicken \(das Feld innerhalb von **MainWindow**\) und die Eigenschaft **Name** oben im Fenster **Eigenschaften** auf "grid1" festlegen.  
  
4.  Klicken Sie im Fenster **Eigenschaften** neben der `ColumnDefinitions`\-Eigenschaft auf die Auslassungspunkte \(**…**\), um das Dialogfeld **Auflistungs\-Editor** zu öffnen.  
  
5.  Klicken Sie im Dialogfeld **Auflistungs\-Editor** drei Mal auf die Schaltfläche **Hinzufügen**, um drei Spalten in das Layout einzufügen.Die erste Spalte enthält die **Toolbox**, die zweite Spalte den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] und die dritte Spalte die Eigenschaftenanalyse.  
  
6.  Legen Sie die `Width`\-Eigenschaft der mittleren Spalte auf den Wert "4\*" fest.  
  
7.  Klicken Sie auf **OK**, um die Änderungen zu speichern.Der Datei "MainWindow.xaml" wird der folgende XAML\-Code hinzugefügt:  
  
    ```  
  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
  
    ```  
  
8.  Klicken Sie im **Projektmappen\-Explorer** mit der rechten Maustaste auf MainWindow.xaml, und wählen Sie **Code anzeigen**.Ändern Sie den Code, indem Sie folgende Schritte ausführen:  
  
    1.  Fügen Sie die folgenden Namespaces hinzu:  
  
        ```csharp  
  
        using System.Activities;  
        using System.Activities.Core.Presentation;  
        using System.Activities.Presentation;  
        using System.Activities.Presentation.Metadata;  
        using System.Activities.Presentation.Toolbox;  
        using System.Activities.Statements;  
        using System.ComponentModel;  
  
        ```  
  
    2.  Um ein privates Memberfeld zu deklarieren, das eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> enthalten soll, fügen Sie der `MainWindow`\-Klasse den folgenden Code hinzu.  
  
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
  
    3.  Fügen Sie die folgende `AddDesigner`\-Methode zu der `MainWindow`\-Klasse hinzu.Die Implementierung erstellt eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner>, fügt dieser eine <xref:System.Activities.Statements.Sequence>\-Aktivität hinzu und platziert sie in der mittleren Spalte im **Raster** "grid1".  
  
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
  
    4.  Registrieren Sie die Designer\-Metadaten, um Designerunterstützung für alle integrierten Aktivitäten hinzuzufügen.Dies ermöglicht Ihnen, Aktivitäten aus der Toolbox auf der ursprünglichen <xref:System.Activities.Statements.Sequence>\-Aktivität im [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] abzulegen.Fügen Sie hierzu der `MainWindow`\-Klasse die `RegisterMetadata`\-Methode hinzu.  
  
        ```csharp  
  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
  
        ```  
  
         [!INCLUDE[crabout](../../../includes/crabout-md.md)] zum Registrieren von Aktivitätsdesignern finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners](../../../docs/framework/windows-workflow-foundation//how-to-create-a-custom-activity-designer.md).  
  
    5.  Fügen Sie im `MainWindow`\-Klassenkonstruktor den zuvor deklarierten Methoden Aufrufe hinzu, um die Metadaten für die Designerunterstützung zu registrieren und das <xref:System.Activities.Presentation.WorkflowDesigner>\-Objekt zu erstellen.  
  
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
        >  Die `RegisterMetadata`\-Methode registriert die Designer\-Metadaten integrierter Aktivitäten, einschließlich der <xref:System.Activities.Statements.Sequence>\-Aktivität.Da die `AddDesigner`\-Methode die <xref:System.Activities.Statements.Sequence>\-Aktivität verwendet, muss die `RegisterMetadata`\-Methode zuerst aufgerufen werden.  
  
9. Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.  
  
10. In [Aufgabe 3: Erstellen der Toolbox\- und PropertyGrid\-Bereiche](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md) erfahren Sie, wie Sie Ihrem neu gehosteten Workflow\-Designer **Toolbox**\- und **PropertyGrid**\-Unterstützung hinzufügen.  
  
## Siehe auch  
 [Erneutes Hosten des Workflow\-Designers](../../../docs/framework/windows-workflow-foundation//rehosting-the-workflow-designer.md)   
 [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation\-Anwendung](../../../docs/framework/windows-workflow-foundation//task-1-create-a-new-wpf-app.md)   
 [Aufgabe 3: Erstellen der Toolbox\- und PropertyGrid\-Bereiche](../../../docs/framework/windows-workflow-foundation//task-3-create-the-toolbox-and-propertygrid-panes.md)