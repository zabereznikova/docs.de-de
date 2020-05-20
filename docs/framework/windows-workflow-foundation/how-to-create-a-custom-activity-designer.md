---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners'
description: In diesem Artikel wird beschrieben, wie ein benutzerdefinierter Workflow Foundation-Aktivitäts Designer erstellt wird, der über eine Ablage Zone verfügt, in der eine beliebige Aktivität platziert werden kann.
ms.date: 03/30/2017
ms.assetid: 2f3aade6-facc-44ef-9657-a407ef8b9b31
ms.openlocfilehash: 015efd1e482e2b531d28b9caec411c76116c9653
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419784"
---
# <a name="how-to-create-a-custom-activity-designer"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Aktivitätsdesigners

Benutzerdefinierte Aktivitätsdesigner werden in der Regel implementiert, um die zugehörigen Aktivitäten mit anderen Aktivitäten zusammenzusetzen, deren Designer mit ihnen auf der Entwurfsoberfläche abgelegt werden können. Diese Funktion erfordert, dass ein benutzerdefinierter Aktivitäts Designer eine "Ablage Zone" bereitstellt, in der eine beliebige Aktivität platziert werden kann, und auch die Möglichkeit, die resultierende Auflistung von Elementen auf der Entwurfs Oberfläche zu verwalten. In diesem Thema wird beschrieben, wie ein benutzerdefinierter Aktivitätsdesigner erstellt wird, der eine solche Ablagezone enthält und die Bearbeitungsfunktionen zur Verwaltung der Auflistung von Designerelementen bereitstellt.

Benutzerdefinierte Aktivitätsdesigner erben in der Regel von <xref:System.Activities.Presentation.ActivityDesigner>. Dies ist der standardmäßige Designertyp für alle Aktivitäten ohne bestimmten Designer. Dieser Typ stellt Entwurfszeitfunktionen für die Interaktion mit dem Eigenschaftenraster und die Konfiguration von grundlegenden Aspekten wie Farbe und Symbole bereit.

<xref:System.Activities.Presentation.ActivityDesigner> verwendet zwei Hilfssteuerelemente (<xref:System.Activities.Presentation.WorkflowItemPresenter> und <xref:System.Activities.Presentation.WorkflowItemsPresenter>), die das Entwickeln benutzerdefinierter Aktivitätsdesigner vereinfachen. Sie behandeln die allgemeine Funktionalität wie Ziehen und Ablegen von untergeordneten Elementen sowie Löschen, Auswählen und Hinzufügen dieser untergeordneten Elemente. Das- <xref:System.Activities.Presentation.WorkflowItemPresenter> Element ermöglicht ein einzelnes untergeordnetes Benutzeroberflächen Element in, das die "Ablage Zone" bereitstellt, während der <xref:System.Activities.Presentation.WorkflowItemsPresenter> Unterstützung für mehrere Benutzeroberflächen Elemente bereitstellen kann, einschließlich zusätzlicher Funktionen wie das Anordnen, verschieben, löschen und Hinzufügen von untergeordneten Elementen.

Der andere wichtige Teil der Story, der in der Implementierung eines benutzerdefinierten Aktivitäts Designers hervorgehoben werden muss, bezieht sich auf die Art und Weise, in der die visuellen Bearbeitungen mithilfe der WPF-Datenbindung an die Instanz gebunden werden, die im Arbeitsspeicher des Designers gespeichert ist Hierzu dient die Modellelementstruktur, die auch zur Aktivierung der Änderungsbenachrichtigung und der Nachverfolgung von Ereignissen wie Zustandsänderungen verwendet wird.

In diesem Thema werden zwei Prozeduren beschrieben.

1. Die erste Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemPresenter> erstellt wird, der die Ablagezone für andere Aktivitäten bereitstellt. Dieses Verfahren basiert auf dem Beispiel [benutzerdefinierte zusammengesetzte Designer-Workflow Element Presenter](./samples/custom-composite-designers-workflow-item-presenter.md) .

2. Die zweite Prozedur beschreibt, wie ein benutzerdefinierter Aktivitätsdesigner mit <xref:System.Activities.Presentation.WorkflowItemsPresenter> erstellt wird, der die zur Bearbeitung einer Auflistung von Elementen benötigten Funktionen bereitstellt. Dieses Verfahren basiert auf dem Beispiel [benutzerdefinierte zusammengesetzte Designer-Workflow Items Presenter](./samples/custom-composite-designers-workflow-items-presenter.md) .

## <a name="to-create-a-custom-activity-designer-with-a-drop-zone-using-workflowitempresenter"></a>So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner, der eine Ablagezone bereitstellt, mit WorkflowItemPresenter

1. Starten Sie Visual Studio 2010.

2. Zeigen Sie im Menü **Datei** auf **neu**, und wählen Sie dann **Projekt...** aus.

     Das Dialogfeld **Neues Projekt** wird angezeigt.

3. Wählen Sie im Bereich **installierte Vorlagen** in der Kategorie bevorzugte Sprache die Option **Windows** aus.

4. Wählen Sie im Bereich **Vorlagen** die Option **WPF-Anwendung**aus.

5. Geben Sie im Feld **Name den Namen** ein `UsingWorkflowItemPresenter` .

6. Geben Sie im Feld **Speicherort** das Verzeichnis ein, in dem Sie das Projekt speichern möchten, oder klicken Sie auf **Durchsuchen** , um zu diesem Verzeichnis zu navigieren.

7. Übernehmen Sie **im Feldprojekt Mappe den Standard** Wert.

8. Klicken Sie auf **OK**.

9. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die Datei " *mainwindows. XAML* ", und wählen Sie im Dialogfeld **Microsoft Visual Studio** die Option **Löschen** und **OK** bestätigen aus.

10. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.** um das Dialogfeld **Neues Element hinzufügen** aufzubringen, und wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die Kategorie **WPF** aus.

11. Wählen Sie die Vorlage **Fenster (WPF)** aus, benennen Sie Sie `RehostingWFDesigner` , und klicken Sie auf **Hinzufügen**.

12. Öffnen Sie die Datei " *rehostingwfdesigner. XAML* ", und fügen Sie den folgenden Code in die Datei ein, um die Benutzeroberfläche für die Anwendung zu definieren:

    ```xaml
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

13. Um einem Aktivitätsdesigner einen Aktivitätstyp zuzuordnen, müssen Sie den Aktivitätsdesigner im Metadatenspeicher registrieren. Fügen Sie hierzu der `RegisterMetadata`-Klasse die `RehostingWFDesigner`-Methode hinzu. Erstellen Sie innerhalb des Bereichs der `RegisterMetadata`-Methode ein <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder>-Objekt, und rufen Sie die <xref:System.Activities.Presentation.Metadata.AttributeTableBuilder.AddCustomAttributes%2A>-Methode auf, um dem Objekt die Attribute hinzuzufügen. Rufen Sie die <xref:System.Activities.Presentation.Metadata.MetadataStore.AddAttributeTable%2A>-Methode auf, um dem Metadatenspeicher das <xref:System.Activities.Presentation.Metadata.AttributeTable>-Objekt hinzuzufügen. Der folgende Code enthält die Rehosting-Logik für den Designer. Damit werden die Metadaten registriert, die `SimpleNativeActivity` wird in die Toolbox eingefügt und der Workflow wird erstellt. Fügen Sie diesen Code in die *RehostingWFDesigner.XAML.cs* -Datei ein.

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
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();
                // Add custom activity to toolbox.
                Toolbox.Categories.Add(new ToolboxCategory("Custom activities"));
                Toolbox.Categories[1].Add(new ToolboxItemWrapper(typeof(SimpleNativeActivity)));

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
                builder.AddCustomAttributes(typeof(SimpleNativeActivity), new DesignerAttribute(typeof(SimpleNativeDesigner)));
                MetadataStore.AddAttributeTable(builder.CreateTable());
            }
        }
    }
    ```

14. Klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Verzeichnis Verweise, und wählen Sie **Verweis hinzufügen aus.** , wenn das Dialogfeld **Verweis hinzufügen** angezeigt werden soll.

15. Klicken Sie auf die Registerkarte **.net** , suchen Sie die Assembly **System. Activities. Core. Presentation**, wählen Sie Sie aus, und klicken Sie auf **OK**.

16. Fügen Sie auf die gleiche Weise den folgenden Assemblys Verweise hinzu:

    1. System.Data.DataSetExtensions.dll

    2. System.Activities.Presentation.dll

    3. System.ServiceModel.Activities.dll

17. Öffnen Sie die Datei " *app. XAML* ", und ändern Sie den Wert von StartupUri in "rehostingwfdesigner. XAML".

18. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.** um das Dialogfeld **Neues Element hinzufügen** zu aktivieren, wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die **Workflow** Kategorie aus.

19. Wählen Sie die Vorlage **Aktivitäts Designer** aus, benennen Sie Sie `SimpleNativeDesigner` , und klicken Sie auf **Hinzufügen**.

20. Öffnen Sie die Datei *simplenativedesigner. XAML* , und fügen Sie den folgenden Code in die Datei ein. Beachten Sie, dass in diesem Code <xref:System.Activities.Presentation.ActivityDesigner> als Stammelement verwendet wird. Er zeigt, wie <xref:System.Activities.Presentation.WorkflowItemPresenter> mithilfe von Bindung in Ihren Designer integriert wird, sodass im zusammengesetzten Aktivitätsdesigner ein untergeordneter Typ angezeigt werden kann.

    > [!NOTE]
    > Mit dem Schema für <xref:System.Activities.Presentation.ActivityDesigner> können Sie dem benutzerdefinierten Aktivitätsdesigner nur ein untergeordnetes Element hinzufügen. Bei diesem Element kann es sich jedoch um ein `StackPanel`, ein `Grid` oder um ein anderes zusammengesetztes Benutzeroberflächenelement handeln.

    ```xaml
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

21. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt usingworkflowitempresenter, wählen Sie **Hinzufügen**und dann **Neues Element... aus.** um das Dialogfeld **Neues Element hinzufügen** zu aktivieren, wählen Sie im Abschnitt **installierte Vorlagen** auf der linken Seite die **Workflow** Kategorie aus.

22. Wählen Sie die Vorlage **Code Aktivität** aus, benennen Sie Sie `SimpleNativeActivity` , und klicken Sie auf **Hinzufügen**.

23. Implementieren Sie die- `SimpleNativeActivity` Klasse, indem Sie den folgenden Code in die *SimpleNativeActivity.cs* -Datei eingeben:

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

24. Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **Erstellen** aus.

25. Klicken Sie im Menü **Debuggen** auf **Starten ohne Debugging** , um das neu gehostete benutzerdefinierte Entwurfs Fenster zu öffnen.

### <a name="to-create-a-custom-activity-designer-using-workflowitemspresenter"></a>So erstellen Sie einen benutzerdefinierten Aktivitätsdesigner mit WorkflowItemsPresenter

1. Die Prozedur für den zweiten benutzerdefinierten Aktivitäts Designer ist der parallele der erste mit einigen Änderungen, der erste besteht darin, die zweite Anwendung zu benennen `UsingWorkflowItemsPresenter` . Außerdem wird mit dieser Anwendung keine neue benutzerdefinierte Aktivität definiert.

2. Wichtige Unterschiede sind in den Dateien " *customparalleldesigner. XAML* " und " *RehostingWFDesigner.XAML.cs* " enthalten. Im folgenden finden Sie den Code aus der Datei " *customparalleldesigner. XAML* ", die die Benutzeroberfläche definiert:

    ```xaml
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

3. Im folgenden finden Sie den Code aus der *RehostingWFDesigner.XAML.cs* -Datei, die die neuhostinglogik bereitstellt:

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
                // Register metadata.
                (new DesignerMetadata()).Register();
                RegisterCustomMetadata();

                // Create the workflow designer.
                var wd = new WorkflowDesigner();
                wd.Load(new Sequence());
                DesignerBorder.Child = wd.View;
                PropertyBorder.Child = wd.PropertyInspectorView;

            }

            void RegisterCustomMetadata()
            {
                var builder = new AttributeTableBuilder();
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
