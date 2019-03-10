---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners'
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: e455d00ebd128c37eacb19df0e7f864505df04e0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716828"
---
# <a name="how-to-create-a-custom-activity-designer"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners

Benutzerdefinierte Aktivitätsdesigner werden in der Regel implementiert, um die zugehörigen Aktivitäten mit anderen Aktivitäten zusammenzusetzen, deren Designer mit ihnen auf der Entwurfsoberfläche abgelegt werden können. Diese Funktionalität erfordert, dass ein benutzerdefinierter Aktivitätsdesigner bereitstellen, eine "Ablagezone", in denen eine beliebige Aktivität platziert werden kann, sowie die Möglichkeit, die resultierende Auflistung von Elementen auf der Entwurfsoberfläche zu verwalten. In diesem Thema wird beschrieben, wie ein benutzerdefinierter Aktivitätsdesigner erstellt wird, der eine solche Ablagezone enthält und die Bearbeitungsfunktionen zur Verwaltung der Auflistung von Designerelementen bereitstellt.

Benutzerdefinierte Aktivitätsdesigner erben in der Regel von <xref:System.Activities.Presentation.ActivityDesigner>. Dies ist der standardmäßige Designertyp für alle Aktivitäten ohne bestimmten Designer. Dieser Typ stellt Entwurfszeitfunktionen für die Interaktion mit dem Eigenschaftenraster und die Konfiguration von grundlegenden Aspekten wie Farbe und Symbole bereit.

<xref:System.Activities.Presentation.ActivityDesigner> verwendet zwei Hilfssteuerelemente (<xref:System.Activities.Presentation.WorkflowItemPresenter> und <xref:System.Activities.Presentation.WorkflowItemsPresenter>), die das Entwickeln benutzerdefinierter Aktivitätsdesigner vereinfachen. Sie behandeln die allgemeine Funktionalität wie Ziehen und Ablegen von untergeordneten Elementen sowie Löschen, Auswählen und Hinzufügen dieser untergeordneten Elemente. Die <xref:System.Activities.Presentation.WorkflowItemPresenter> unterstützt ein einzelnes untergeordnetes Benutzeroberflächenelement, die "Ablagezone" Bereitstellen während der <xref:System.Activities.Presentation.WorkflowItemsPresenter> unterstützt mehrere Benutzeroberflächenelemente, darunter zusätzliche Funktionalität z. B. zum Sortieren, verschieben, löschen und Hinzufügen von untergeordneten Elementen.

Der zweite Hauptaspekt bei der Implementierung eines benutzerdefinierten Aktivitätsdesigners betrifft die Methode zur Bindung der grafischen Bearbeitungen an die Instanz der im Designer bearbeiteten Objekte im Arbeitsspeicher mit der [!INCLUDE[avalon2](../../../includes/avalon2-md.md)]-Datenbindung. Hierzu dient die Modellelementstruktur, die auch zur Aktivierung der Änderungsbenachrichtigung und der Nachverfolgung von Ereignissen wie Zustandsänderungen verwendet wird.

In diesem Thema werden zwei Prozeduren beschrieben.

1. Die erste Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemPresenter> erstellt wird, der die Ablagezone für andere Aktivitäten bereitstellt. Dieses Verfahren basiert auf der [benutzerdefinierte zusammengesetzte Designer - Workflow-Element-Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) Beispiel.

2. Die zweite Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemsPresenter> erstellt wird, der die zur Bearbeitung einer Auflistung von Elementen benötigten Funktionen bereitstellt. Dieses Verfahren basiert auf der [benutzerdefinierte zusammengesetzte Designer: Workflowelementpräsentation](./samples/custom-composite-designers-workflow-items-presenter.md) Beispiel.

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a>So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner, der eine Ablagezone bereitstellt, mit WorkflowItemPresenter

1. Starten Sie Visual Studio 2010.

2. Auf der **Datei** Startmenü **neu**, und wählen Sie dann **Projekt...** .

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. In der **installierte Vorlagen** wählen Sie im Bereich **Windows** von Ihnen bevorzugten Sprachkategorie.

4. In der **Vorlagen** wählen Sie im Bereich **WPF-Anwendung**.

5. In der **Namen** geben `UsingWorkflowItemPresenter`.

6. In der **Speicherort** Geben Sie das Verzeichnis, in dem Sie das Projekt speichern, oder klicken Sie auf möchten **Durchsuchen** dorthin navigieren.

7. In der **Lösung** Feld aus, übernehmen Sie den Standardwert.

8. Klicken Sie auf **OK**.

9. Mit der rechten Maustaste in der Datei "MainWindows.xaml" in der **Projektmappen-Explorer**Option **löschen** und vergewissern Sie sich **OK** in die **Microsoft Visual Studio**Dialogfeld.

10. Mit der rechten Maustaste in des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...** um die **neues Element hinzufügen** Dialogfeld, und wählen Sie die **WPF** Kategorie aus der **installierte Vorlagen** Abschnitt auf der linken Seite.

11. Wählen Sie die **Fenster (WPF)** Vorlage, nennen Sie sie `RehostingWFDesigner`, und klicken Sie auf **hinzufügen**.

12. Öffnen Sie die Datei "RehostingWFDesigner.xaml", und fügen Sie den folgenden Code ein, um die Benutzeroberfläche für die Anwendung zu definieren.

    ```xml
    <Window x:Class=" UsingWorkflowItemPresenter.RehostingWFDesigner"
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
            xmlns:sapt="clr-namespace:System.Activities.Presentation.Toolbox;assembly=System.Activities.Presentation"
            xmlns:sys="clr-namespace:System;assembly=mscorlib"
            Title="Window1" Height="600" Width="900">
        <Window.Resources>
            <sys:String x:Key="AssemblyName">System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35</sys:String>
        </Window.Resources>
        <Grid>
            <Grid.ColumnDefinitions>
                <ColumnDefinition Width="2*"/>
                <ColumnDefinition Width="7*"/>
                <ColumnDefinition Width="3*"/>
            </Grid.ColumnDefinitions>
            <Border Grid.Column="0">
                <sapt:ToolboxControl Name="Toolbox">
                    <sapt:ToolboxCategory CategoryName="Basic">
                        <sapt:ToolboxItemWrapper AssemblyName="{StaticResource AssemblyName}" >
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.Sequence
                            </sapt:ToolboxItemWrapper.ToolName>
                           </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.WriteLine
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.If
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                        <sapt:ToolboxItemWrapper  AssemblyName="{StaticResource AssemblyName}">
                            <sapt:ToolboxItemWrapper.ToolName>
                                System.Activities.Statements.While
                            </sapt:ToolboxItemWrapper.ToolName>

                        </sapt:ToolboxItemWrapper>
                    </sapt:ToolboxCategory>
                </sapt:ToolboxControl>
            </Border>
            <Border Grid.Column="1" Name="DesignerBorder"/>
            <Border Grid.Column="2" Name="PropertyBorder"/>
        </Grid>
    </Window>
    ```

13. Um einem Aktivitätsdesigner einen Aktivitätstyp zuzuordnen, müssen Sie den Aktivitätsdesigner im Metadatenspeicher registrieren. Fügen Sie hierzu der `RegisterMetadata`-Klasse die `RehostingWFDesigner`-Methode hinzu. Erstellen Sie innerhalb des Bereichs der `RegisterMetadata`-Methode ein <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder>-Objekt, und rufen Sie die <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>-Methode auf, um dem Objekt die Attribute hinzuzufügen. Rufen Sie die <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>-Methode auf, um dem Metadatenspeicher das <xref:System.Activities.Presentation.Metadata.AttributeTable>-Objekt hinzuzufügen. Der folgende Code enthält die Rehosting-Logik für den Designer. Damit werden die Metadaten registriert, die `SimpleNativeActivity` wird in die Toolbox eingefügt und der Workflow wird erstellt. Fügen Sie diesen Code in die Datei "RehostingWFDesigner.xaml.cs" ein.

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Presentation.Toolbox;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespace UsingWorkflowItemPresenter
    {
        // Interaction logic for RehostingWFDesigner.xaml
        public partial class RehostingWFDesigner
        {
            public RehostingWFDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // register metadata
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // add custom activity to toolbox
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // create the workflow designer
                WorkflowDesigner wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                AttributeTableBuilder builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. Mit der rechten Maustaste in das Verzeichnis "Verweise" im Projektmappen-Explorer, und wählen Sie **Verweis hinzufügen...** um die **Verweis hinzufügen** Dialogfeld.

15. Klicken Sie auf die **.NET** Registerkarte, suchen Sie die Assembly mit dem Namen **System.Activities.Core.Presentation**, wählen Sie ihn, und klicken Sie auf **OK**.

16. Fügen Sie auf die gleiche Weise den folgenden Assemblys Verweise hinzu:

    1. System.Data.DataSetExtensions.dll

    2. System.Activities.Presentation.dll

    3. System.ServiceModel.Activities.dll

17. Öffnen Sie die Datei "App.xaml", und ändern Sie den Wert, der den "StartupUri" in "RehostingWFDesigner.xaml".

18. Mit der rechten Maustaste in des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...** um die **neues Element hinzufügen** Dialogfeld, und wählen Sie die **Workflow** Kategorie Form der **installierte Vorlagen** Abschnitt auf der linken Seite.

19. Wählen Sie die **Aktivitäts-Designer** Vorlage, nennen Sie sie `SimpleNativeDesigner`, und klicken Sie auf **hinzufügen**.

20. Öffnen Sie die Datei "SimpleNativeDesigner.xaml", und fügen Sie den folgenden Code ein. Beachten Sie, dass in diesem Code <xref:System.Activities.Presentation.ActivityDesigner> als Stammelement verwendet wird. Er zeigt, wie <xref:System.Activities.Presentation.WorkflowItemPresenter> mithilfe von Bindung in Ihren Designer integriert wird, sodass im zusammengesetzten Aktivitätsdesigner ein untergeordneter Typ angezeigt werden kann.

    > [!NOTE]
    > Mit dem Schema für <xref:System.Activities.Presentation.ActivityDesigner> können Sie dem benutzerdefinierten Aktivitätsdesigner nur ein untergeordnetes Element hinzufügen. Bei diesem Element kann es sich jedoch um ein `StackPanel`, ein `Grid` oder um ein anderes zusammengesetztes Benutzeroberflächenelement handeln.

    ```xml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemPresenter.SimpleNativeDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <StackPanel>
                    <TextBlock>This is the collapsed view</TextBlock>
                </StackPanel>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock>Custom Text</TextBlock>
                    <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                            HintText="Please drop an activity here" />
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
        </Grid>
    </sap:ActivityDesigner>
    ```

21. Mit der rechten Maustaste in des Projekts "UsingWorkflowItemPresenter" im **Projektmappen-Explorer**Option **hinzufügen**, klicken Sie dann **neues Element...** um die **neues Element hinzufügen** Dialogfeld, und wählen Sie die **Workflow** Kategorie Form der **installierte Vorlagen** Abschnitt auf der linken Seite.

22. Wählen Sie die **Codeaktivität** Vorlage, nennen Sie sie `SimpleNativeActivity`, und klicken Sie auf **hinzufügen**.

23. Implementieren Sie die `SimpleNativeActivity`-Klasse, indem Sie den folgenden Code in die Datei "SimpleNativeActivity.cs" einfügen.

    ```csharp
    using System.Activities;

    namespace UsingWorkflowItemPresenter
    {
        public sealed class SimpleNativeActivity : NativeActivity
        {
            // this property contains an activity that will be scheduled in the execute method
            // the WorkflowItemPresenter in the designer is bound to this to enable editing
            // of the value
            public Activity Body { get; set; }

            protected override void CacheMetadata(NativeActivityMetadata metadata)
            {
               metadata.AddChild(Body);
               base.CacheMetadata(metadata);

            }

            protected override void Execute(NativeActivityContext context)
            {
                context.ScheduleActivity(Body);
            }
        }
    }
    ```

24. Wählen Sie **Projektmappe** aus der **erstellen** Menü.

25. Wählen Sie **Starten ohne Debugging** aus der **Debuggen** Menü, um das neu gehostete benutzerdefinierte Entwurfsfenster zu öffnen.

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a>So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner mit WorkflowItemsPresenter

1. Die Prozedur für den zweiten benutzerdefinierten Aktivitätsdesigner ist die erste mit einigen Änderungen der erste besteht darin, benennen Sie die zweite Anwendung `UsingWorkflowItemsPresenter`. Außerdem wird mit dieser Anwendung keine neue benutzerdefinierte Aktivität definiert.

2. Die Hauptunterschiede sind in den Dateien "CustomParallelDesigner.xaml" und "RehostingWFDesigner.xaml.cs" enthalten. Hier ist der Code aus der "customparalleldesigner.xaml"-Datei, die die Benutzeroberfläche definiert.

    ```xml
    <sap:ActivityDesigner x:Class=" UsingWorkflowItemsPresenter.CustomParallelDesigner"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
        xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
        <sap:ActivityDesigner.Resources>
            <DataTemplate x:Key="Collapsed">
                <TextBlock>This is the Collapsed View</TextBlock>
            </DataTemplate>
            <DataTemplate x:Key="Expanded">
                <StackPanel>
                    <TextBlock HorizontalAlignment="Center">This is the</TextBlock>
                    <TextBlock HorizontalAlignment="Center">extended view</TextBlock>
                    <sap:WorkflowItemsPresenter HintText="Drop Activities Here"
                                        Items="{Binding Path=ModelItem.Branches}">
                        <sap:WorkflowItemsPresenter.SpacerTemplate>
                            <DataTemplate>
                                <Ellipse Width="10" Height="10" Fill="Black"/>
                            </DataTemplate>
                        </sap:WorkflowItemsPresenter.SpacerTemplate>
                        <sap:WorkflowItemsPresenter.ItemsPanel>
                            <ItemsPanelTemplate>
                                <StackPanel Orientation="Horizontal"/>
                            </ItemsPanelTemplate>
                        </sap:WorkflowItemsPresenter.ItemsPanel>
                    </sap:WorkflowItemsPresenter>
                </StackPanel>
            </DataTemplate>
            <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
                <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
                <Style.Triggers>
                    <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                        <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                    </DataTrigger>
                </Style.Triggers>
            </Style>
        </sap:ActivityDesigner.Resources>
        <Grid>
            <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
        </Grid>
    </sap:ActivityDesigner>
    ```

3. Hier stammt der Code aus der Datei "RehostingWFDesigner.xaml.cs" zur Bereitstellung der Rehosting-Logik.

    ```csharp
    using System;
    using System.Activities.Core.Presentation;
    using System.Activities.Presentation;
    using System.Activities.Presentation.Metadata;
    using System.Activities.Statements;
    using System.ComponentModel;
    using System.Windows;

    namespaceUsingWorkflowItemsPresenter
    {
        public partial class RehostingWfDesigner : Window
        {
            public RehostingWfDesigner()
            {
                InitializeComponent();
            }

            protected override void OnInitialized(EventArgs e)
            {
                base.OnInitialized(e);
                // register metadata
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // create the workflow designer
                WorkflowDesigner wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                AttributeTableBuilder builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Presentation.ActivityDesigner>
- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- <xref:System.Activities.Presentation.WorkflowViewElement>
- <xref:System.Activities.Presentation.Model.ModelItem>
- [Anpassen des Workflowentwurfsvorgangs](customizing-the-workflow-design-experience.md)
