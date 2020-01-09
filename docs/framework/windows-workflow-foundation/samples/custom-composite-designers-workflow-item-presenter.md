---
title: Benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: d1047b8be35545e83eaa8788b53751b6b0056984
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338043"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation

Der <xref:System.Activities.Presentation.WorkflowItemPresenter> ist ein Schlüsseltyp im WF-Designer-Programmiermodell, das die Erstellung einer "Drop Zone" ermöglicht, in der eine beliebige Aktivität platziert werden kann. In diesem Beispiel wird gezeigt, wie ein Aktivitäts Designer erstellt wird, der eine solche "Ablage Zone" aufweist.

Dieses Beispiel veranschaulicht Folgendes:

- Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.

- Registrieren des benutzerdefinierten Designers mithilfe des Metadatenspeichers.

- Deklaratives und imperatives Programmieren der neu gehosteten Toolbox.

## <a name="sample-details"></a>Beispieldetails

Der Code für dieses Beispiel zeigt Folgendes:

- Der benutzerdefinierte Aktivitätsdesigner wird für die `SimpleNativeActivity`-Klasse erstellt.

- Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
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

 Beachten Sie die Verwendung der WPF-Datenbindung, um eine Bindung an `ModelItem.Body` auszuführen. `ModelItem` ist die Eigenschaft auf <xref:System.Activities.Presentation.ActivityDesigner>, die auf das zugrunde liegende Objekt verweist, für das der Designer verwendet wird, in diesem Fall **SimpleNativeActivity**.

## <a name="set-up-build-and-run-the-sample"></a>Einrichten, erstellen und Ausführen des Beispiels

1. Öffnen Sie die Lösung in Visual Studio.

2. Drücken Sie **F5** , um die Anwendung zu kompilieren und auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a>Siehe auch

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [Entwickeln von Anwendungen mit dem Workflow-Designer](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
