---
title: 'Aufgabe 2: Hosten des Workflow-Designers'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 3f7964e907fe513679e60c18292f07c84128590b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299266"
---
# <a name="task-2-host-the-workflow-designer"></a>Aufgabe 2: Hosten des Workflow-Designers
Dieses Thema beschreibt das Verfahren zum Hosten einer Instanz von der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] in einer Windows Presentation Foundation (WPF)-Anwendung.  
  
 Die Prozedur konfiguriert das **Raster** -Steuerelement, das den Designer enthält erstellt programmgesteuert eine Instanz des der <xref:System.Activities.Presentation.WorkflowDesigner> , die einen Standardbefehl enthält <xref:System.Activities.Statements.Sequence> -Aktivität, registriert die Designermetadaten bereitstellen designerunterstützung für alle integrierten Aktivitäten und -Hosts die [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in die [!INCLUDE[avalon2](../../../includes/avalon2-md.md)] Anwendung.  
  
### <a name="to-host-the-workflow-designer"></a>So hosten Sie den Workflow-Designer  
  
1. Öffnen der HostingApplication-Projekt, die Sie in erstellt [Aufgabe 1: Erstellen eine neuen Windows Presentation Foundation-Anwendung](task-1-create-a-new-wpf-app.md).  
  
2. Passen Sie die Fenstergröße an, um die Verwendung des [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] einfacher zu machen. Zu diesem Zweck wählen **MainWindow-Element** im Designer, drücken Sie F4, um die **Eigenschaften** Fenster, und aktivieren Sie in der **Layout** Abschnitt vorhanden, legen Sie die **Breite** auf einen Wert von 600 und die **Höhe** auf einen Wert von 350.  
  
3. Legen Sie den rasternamen durch Auswahl der **Raster** Bereich im Designer (klicken Sie auf das Feld innerhalb der **MainWindow**) und Einstellung der **Namen** Eigenschaft am oberen Rand der  **Eigenschaften** Fenster auf "grid1".  
  
4. In der **Eigenschaften** Fenster, klicken Sie auf die Auslassungspunkte (**...** ) neben der `ColumnDefinitions` Eigenschaft zum Öffnen der **Auflistungs-Editor** Dialogfeld.  
  
5. In der **Auflistungs-Editor** Dialogfeld klicken Sie auf die **hinzufügen** Schaltfläche dreimal, um drei Spalten in das Layout einzufügen. Die erste Spalte enthält die **Toolbox**, die zweite Spalte die [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], und die dritte Spalte für die Eigenschaftenanalyse verwendet werden.  
  
6. Legen Sie die `Width` -Eigenschaft der mittleren Spalte auf den Wert "4 *".  
  
7. Klicken Sie auf **OK** um die Änderungen zu speichern. Der Datei "MainWindow.xaml" wird der folgende XAML-Code hinzugefügt:  
  
    ```xml  
    <Grid Name="grid1">  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition />  
            <ColumnDefinition Width="4*" />  
            <ColumnDefinition />  
        </Grid.ColumnDefinitions>  
    </Grid>  
    ```  
  
8. In **Projektmappen-Explorer**mit der rechten Maustaste auf "MainWindow.xaml", und wählen Sie **Ansichtscode**. Ändern Sie den Code, indem Sie folgende Schritte ausführen:  
  
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
  
    2.  Um ein privates Memberfeld zu deklarieren, das eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> enthalten soll, fügen Sie der `MainWindow`-Klasse den folgenden Code hinzu.  
  
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
  
    3.  Fügen Sie die folgende `AddDesigner`-Methode zu der `MainWindow`-Klasse hinzu. Die Implementierung erstellt eine Instanz der <xref:System.Activities.Presentation.WorkflowDesigner>, fügt ein <xref:System.Activities.Statements.Sequence> -Aktivität hinzu und platziert sie in der mittleren Spalte grid1 **Raster**.  
  
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
  
    4.  Registrieren Sie die Designer-Metadaten, um Designerunterstützung für alle integrierten Aktivitäten hinzuzufügen. Dies ermöglicht Ihnen, Aktivitäten aus der Toolbox auf der ursprünglichen <xref:System.Activities.Statements.Sequence>-Aktivität im [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] abzulegen. Fügen Sie hierzu der `RegisterMetadata`-Klasse die `MainWindow`-Methode hinzu.  
  
        ```csharp  
        private void RegisterMetadata()  
        {               
            DesignerMetadata dm = new DesignerMetadata();  
            dm.Register();  
        }  
        ```  
  
         Weitere Informationen zum Registrieren von Aktivitätsdesignern finden Sie unter [Vorgehensweise: Erstellen ein benutzerdefinierten Aktivitätsdesigners](how-to-create-a-custom-activity-designer.md).  
  
    5.  Fügen Sie im `MainWindow`-Klassenkonstruktor den zuvor deklarierten Methoden Aufrufe hinzu, um die Metadaten für die Designerunterstützung zu registrieren und das <xref:System.Activities.Presentation.WorkflowDesigner>-Objekt zu erstellen.  
  
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
        >  Die `RegisterMetadata`-Methode registriert die Designer-Metadaten integrierter Aktivitäten, einschließlich der <xref:System.Activities.Statements.Sequence>-Aktivität. Da die `AddDesigner`-Methode die <xref:System.Activities.Statements.Sequence>-Aktivität verwendet, muss die `RegisterMetadata`-Methode zuerst aufgerufen werden.  
  
9. Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.  
  
10. Finden Sie unter [Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche](task-3-create-the-toolbox-and-propertygrid-panes.md) erfahren, wie hinzufügen **Toolbox** und **PropertyGrid** zu Ihrem neu gehosteten Workflow-Designer unterstützt.  
  
## <a name="see-also"></a>Siehe auch

- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation-Anwendung](task-1-create-a-new-wpf-app.md)
- [Aufgabe 3: Erstellen der Toolbox- und PropertyGrid-Bereiche](task-3-create-the-toolbox-and-propertygrid-panes.md)
