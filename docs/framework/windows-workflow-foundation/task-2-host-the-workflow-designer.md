---
title: 'Aufgabe 2: Hosten des Workflow-Designers'
ms.date: 03/30/2017
ms.assetid: 0a29b138-270d-4846-b78e-2b875e34e501
ms.openlocfilehash: 92c5fa347cc7a2c0088ab8f4fbdfddf25ffb83c1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70037861"
---
# <a name="task-2-host-the-workflow-designer"></a>Aufgabe 2: Hosten des Workflow-Designers

[!INCLUDE[wfd1](../../../includes/wfd1-md.md)] In diesem Thema wird das Verfahren zum Hosting einer Instanz von in einer Windows Presentation Foundation-Anwendung (WPF) beschrieben.

Die Prozedur konfiguriert das **Raster** Steuerelement, das den Designer enthält, erstellt Programm gesteuert eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> , die eine Standard <xref:System.Activities.Statements.Sequence> Aktivität enthält, registriert die Designer Metadaten, um Designer Unterstützung für alle bereitzustellen. Integrierte Aktivitäten und hosten [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in der WPF-Anwendung.

### <a name="to-host-the-workflow-designer"></a>So hosten Sie den Workflow-Designer

1. Öffnen Sie das HostingApplication-Projekt, [das Sie in Aufgabe 1 erstellt haben: Erstellen Sie eine neue Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)Anwendung.

2. Passen Sie die Fenstergröße an, um die Verwendung des [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] einfacher zu machen. Wählen Sie hierzu im Designer **MainWindow** , drücken Sie F4, um das **Eigenschaften** Fenster anzuzeigen, und legen Sie im Abschnitt **Layout** die **Breite** auf den Wert 600 und die **Höhe** auf 350 fest.

3. Legen Sie den Raster Namen fest, indem Sie im Designer den **Raster** Bereich auswählen (Klicken Sie auf das Feld im **MainWindow**), und legen Sie die **Name** -Eigenschaft oben im **Eigenschaften** Fenster auf "grid1" fest.

4. Klicken Sie im **Eigenschaften** Fenster auf die Auslassungs Punkte ( **...** ) neben der `ColumnDefinitions` -Eigenschaft, um das Dialogfeld Auflistungs- **Editor** zu öffnen.

5. Klicken Sie im Dialogfeld Auflistungs- **Editor** drei Mal auf die Schaltfläche **Hinzufügen** , um drei Spalten in das Layout einzufügen. Die erste Spalte enthält die **Toolbox**, die zweite Spalte hostet [!INCLUDE[wfd2](../../../includes/wfd2-md.md)], und die dritte Spalte wird für die Eigenschaften Analyse verwendet.

6. Legen Sie `Width` die-Eigenschaft der mittleren Spalte auf den Wert "4 *" fest.

7. Klicken Sie zum Speichern der Änderungen auf **OK** . Der Datei "MainWindow.xaml" wird der folgende XAML-Code hinzugefügt:

    ```xml
    <Grid Name="grid1">
        <Grid.ColumnDefinitions>
            <ColumnDefinition />
            <ColumnDefinition Width="4*" />
            <ColumnDefinition />
        </Grid.ColumnDefinitions>
    </Grid>
    ```

8. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf MainWindow. XAML, und wählen Sie **Code anzeigen**aus. Ändern Sie den Code, indem Sie folgende Schritte ausführen:

    1. Fügen Sie die folgenden Namespaces hinzu:

        ```csharp
        using System.Activities;
        using System.Activities.Core.Presentation;
        using System.Activities.Presentation;
        using System.Activities.Presentation.Metadata;
        using System.Activities.Presentation.Toolbox;
        using System.Activities.Statements;
        using System.ComponentModel;
        ```

    2. Um ein privates Memberfeld zu deklarieren, das eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner> enthalten soll, fügen Sie der `MainWindow`-Klasse den folgenden Code hinzu.

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

    3. Fügen Sie die folgende `AddDesigner`-Methode zu der `MainWindow`-Klasse hinzu. Die-Implementierung erstellt eine Instanz von <xref:System.Activities.Presentation.WorkflowDesigner>, fügt ihr <xref:System.Activities.Statements.Sequence> eine-Aktivität hinzu und platziert Sie in der mittleren Spalte des grid1- **Rasters**.

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

    4. Registrieren Sie die Designer-Metadaten, um Designerunterstützung für alle integrierten Aktivitäten hinzuzufügen. Dies ermöglicht Ihnen, Aktivitäten aus der Toolbox auf der ursprünglichen <xref:System.Activities.Statements.Sequence>-Aktivität im [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] abzulegen. Fügen Sie hierzu der `RegisterMetadata`-Klasse die `MainWindow`-Methode hinzu.

        ```csharp
        private void RegisterMetadata()
        {
            DesignerMetadata dm = new DesignerMetadata();
            dm.Register();
        }
        ```

        Weitere Informationen zum Registrieren von Aktivitäts Designern finden [Sie unter Gewusst wie: Erstellen Sie einen benutzerdefinierten](how-to-create-a-custom-activity-designer.md)Aktivitäts Designer.

    5. Fügen Sie im `MainWindow`-Klassenkonstruktor den zuvor deklarierten Methoden Aufrufe hinzu, um die Metadaten für die Designerunterstützung zu registrieren und das <xref:System.Activities.Presentation.WorkflowDesigner>-Objekt zu erstellen.

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
        > Die `RegisterMetadata`-Methode registriert die Designer-Metadaten integrierter Aktivitäten, einschließlich der <xref:System.Activities.Statements.Sequence>-Aktivität. Da die `AddDesigner`-Methode die <xref:System.Activities.Statements.Sequence>-Aktivität verwendet, muss die `RegisterMetadata`-Methode zuerst aufgerufen werden.

9. Drücken Sie F5, um die Projektmappe zu erstellen und auszuführen.

10. Siehe [Aufgabe 3: Erstellen Sie den Bereich Toolbox und PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md) , um zu erfahren, wie Sie dem neu gehosteten Workflow-Designer **Toolbox** -und **PropertyGrid** -Unterstützung hinzufügen.

## <a name="see-also"></a>Siehe auch

- [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)
- [Aufgabe 1: Erstellen einer neuen Windows Presentation Foundation Anwendung](task-1-create-a-new-wpf-app.md)
- [Aufgabe 3: Erstellen der Toolbox-und PropertyGrid-Bereiche](task-3-create-the-toolbox-and-propertygrid-panes.md)
