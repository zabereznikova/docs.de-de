---
title: Benutzerdefinierte zusammengesetzte Designer – Workflowelementpräsentation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: 542440d6bf9d6809abee1ec37c85c44ce72fd132
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715155"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a>Benutzerdefinierte zusammengesetzte Designer – Workflowelementpräsentation

<xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> ist ein Haupttyp im WF-Designer-Programmiermodell, der die Bearbeitung einer Auflistung enthaltener Elemente zulässt. In dem Beispiel wird veranschaulicht, wie ein Aktivitätsdesigner erstellt wird, der eine solche bearbeitbare Auflistung aufweist.

Dieses Beispiel veranschaulicht Folgendes:

- Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.

- Erstellen eines Aktivitäts Designers mit einer "reduzierten" und "erweiterten" Ansicht.

- Überschreiben eines standardmäßigen Designers in einer neu gehosteten Anwendung.

### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Öffnen Sie die Beispiel Projekt **Mappe "usingworkflowitemspree Senter. sln** " für C# oder für VB in Visual Studio 2010.

2. Erstellen Sie die Projektmappe, und führen Sie sie aus. Eine neu gehostete Workflow-Designer-Anwendung sollte geöffnet werden, und Sie können Aktivitäten auf den Zeichenbereich ziehen.

## <a name="sample-highlights"></a>Das Wichtigste zum Beispiel

Der Code für dieses Beispiel zeigt Folgendes:

- Die Aktivität, für die ein Designer erstellt wird: `Parallel`

- Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>. Einige wichtige Punkte:

  - Beachten Sie die Verwendung der WPF-Datenbindung, um eine Bindung an `ModelItem.Branches` auszuführen. `ModelItem` ist die Eigenschaft im `WorkflowElementDesigner`, die auf das zugrunde liegende Objekt verweist, für das der Designer verwendet wird; in diesem Fall `Parallel`.

  - <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> kann verwendet werden, um ein visuelle Trennung festzulegen, die zwischen den einzelnen Elementen in der Auflistung angezeigt werden soll.

  - <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> ist eine Vorlage, die bereitgestellt werden kann, um das Layout der Elemente in der Auflistung zu bestimmen. In diesem Fall wird ein horizontaler Stapelbereich verwendet.

  Dies wird im folgenden Codebeispiel gezeigt.

  ```xaml
  <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                Items="{Binding Path=ModelItem.Branches}">
      <sad:WorkflowItemsPresenter.SpacerTemplate>
        <DataTemplate>
          <Ellipse Width="10" Height="10" Fill="Black"/>
        </DataTemplate>
      </sad:WorkflowItemsPresenter.SpacerTemplate>
      <sad:WorkflowItemsPresenter.ItemsPanel>
        <ItemsPanelTemplate>
          <StackPanel Orientation="Horizontal"/>
        </ItemsPanelTemplate>
      </sad:WorkflowItemsPresenter.ItemsPanel>
    </sad:WorkflowItemsPresenter>
  ```

- Führen Sie eine Zuordnung von `DesignerAttribute` zum `Parallel`-Typ aus, und geben Sie dann die gemeldeten Attribute aus.

  - Registrieren Sie zuerst alle standardmäßigen Designer.

    Nachfolgend ist das Codebeispiel angegeben.

    ```csharp
    // register metadata
    (new DesignerMetadata()).Register();
    RegisterCustomMetadata();
    ```

    ```vb
    ' register metadata
    Dim metadata = New DesignerMetadata()
    metadata.Register()
    ' register custom metadata
    RegisterCustomMetadata()
    ```

  - Überschreiben Sie dann "Parallel" in der `RegisterCustomMetadata`-Methode.

    Im folgenden Code wird dies in C# und Visual Basic veranschaulicht.

    ```csharp
    void RegisterCustomMetadata()
    {
          AttributeTableBuilder builder = new AttributeTableBuilder();
          builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
          MetadataStore.AddAttributeTable(builder.CreateTable());
    }
    ```

    ```vb
    Sub RegisterCustomMetadata()
       Dim builder As New AttributeTableBuilder()
       builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
       MetadataStore.AddAttributeTable(builder.CreateTable())
    End Sub
    ```

- Beachten Sie schließlich die Verwendung unterschiedlicher Datenvorlagen und Trigger, um die entsprechende Vorlage auf Grundlage der `IsRootDesigner`-Eigenschaft auszuwählen.

  Nachfolgend ist das Codebeispiel angegeben.

  ```xaml
  <sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
      xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
    <sad:ActivityDesigner.Resources>
      <DataTemplate x:Key="Expanded">
        <StackPanel>
          <TextBlock>This is the Expanded View</TextBlock>
          <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                      Items="{Binding Path=ModelItem.Branches}">
            <sad:WorkflowItemsPresenter.SpacerTemplate>
              <DataTemplate>
                <Ellipse Width="10" Height="10" Fill="Black"/>
              </DataTemplate>
            </sad:WorkflowItemsPresenter.SpacerTemplate>
            <sad:WorkflowItemsPresenter.ItemsPanel>
              <ItemsPanelTemplate>
                <StackPanel Orientation="Horizontal"/>
              </ItemsPanelTemplate>
            </sad:WorkflowItemsPresenter.ItemsPanel>
          </sad:WorkflowItemsPresenter>
        </StackPanel>
      </DataTemplate>
      <DataTemplate x:Key="Collapsed">
        <TextBlock>This is the Collapsed View</TextBlock>
      </DataTemplate>
      <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
        <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
        <Style.Triggers>
          <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
            <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
          </DataTrigger>
        </Style.Triggers>
      </Style>
    </sad: ActivityDesigner.Resources>
    <Grid>
      <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
    </Grid>
  </sad: ActivityDesigner>
  ```

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [Entwickeln von Anwendungen mit dem Workflow-Designer](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
