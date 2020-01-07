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
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="5f0d0-102">Benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation</span><span class="sxs-lookup"><span data-stu-id="5f0d0-102">Custom Composite Designers - Workflow Item Presenter</span></span>

<span data-ttu-id="5f0d0-103">Der <xref:System.Activities.Presentation.WorkflowItemPresenter> ist ein Schlüsseltyp im WF-Designer-Programmiermodell, das die Erstellung einer "Drop Zone" ermöglicht, in der eine beliebige Aktivität platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="5f0d0-104">In diesem Beispiel wird gezeigt, wie ein Aktivitäts Designer erstellt wird, der eine solche "Ablage Zone" aufweist.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>

<span data-ttu-id="5f0d0-105">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5f0d0-105">This sample demonstrates:</span></span>

- <span data-ttu-id="5f0d0-106">Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

- <span data-ttu-id="5f0d0-107">Registrieren des benutzerdefinierten Designers mithilfe des Metadatenspeichers.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-107">Registering the custom designer using the metadata store.</span></span>

- <span data-ttu-id="5f0d0-108">Deklaratives und imperatives Programmieren der neu gehosteten Toolbox.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-108">Programming the rehosted toolbox declaratively and imperatively.</span></span>

## <a name="sample-details"></a><span data-ttu-id="5f0d0-109">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="5f0d0-109">Sample Details</span></span>

<span data-ttu-id="5f0d0-110">Der Code für dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5f0d0-110">The code for this sample shows:</span></span>

- <span data-ttu-id="5f0d0-111">Der benutzerdefinierte Aktivitätsdesigner wird für die `SimpleNativeActivity`-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-111">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>

- <span data-ttu-id="5f0d0-112">Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-112">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>

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

 <span data-ttu-id="5f0d0-113">Beachten Sie die Verwendung der WPF-Datenbindung, um eine Bindung an `ModelItem.Body` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-113">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="5f0d0-114">`ModelItem` ist die Eigenschaft auf <xref:System.Activities.Presentation.ActivityDesigner>, die auf das zugrunde liegende Objekt verweist, für das der Designer verwendet wird, in diesem Fall **SimpleNativeActivity**.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-114">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>

## <a name="set-up-build-and-run-the-sample"></a><span data-ttu-id="5f0d0-115">Einrichten, erstellen und Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="5f0d0-115">Set up, build, and run the sample</span></span>

1. <span data-ttu-id="5f0d0-116">Öffnen Sie die Lösung in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-116">Open the solution in Visual Studio.</span></span>

2. <span data-ttu-id="5f0d0-117">Drücken Sie **F5** , um die Anwendung zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-117">Press **F5** to compile and run the application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f0d0-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5f0d0-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-119">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="5f0d0-120">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5f0d0-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5f0d0-121">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a><span data-ttu-id="5f0d0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f0d0-122">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [<span data-ttu-id="5f0d0-123">Entwickeln von Anwendungen mit dem Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="5f0d0-123">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
