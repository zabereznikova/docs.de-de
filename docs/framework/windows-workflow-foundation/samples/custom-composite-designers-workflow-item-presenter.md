---
title: "Benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bba89e9da78fd96d0cd7d61e825e4792729bae5b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-composite-designers---workflow-item-presenter"></a><span data-ttu-id="8c970-102">Benutzerdefinierte zusammengesetzte Designer - Workflowelementpräsentation</span><span class="sxs-lookup"><span data-stu-id="8c970-102">Custom Composite Designers - Workflow Item Presenter</span></span>
<span data-ttu-id="8c970-103">Die <xref:System.Activities.Presentation.WorkflowItemPresenter> ist ein Schlüsseltyp im WF-Designer-Programmiermodell, die es die Erstellung einer "Ablagezone ermöglicht", in denen eine beliebige Aktivität platziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8c970-103">The <xref:System.Activities.Presentation.WorkflowItemPresenter> is a key type in the WF designer programming model that allows for the creation of a "drop zone" where an arbitrary activity can be placed.</span></span> <span data-ttu-id="8c970-104">In diesem Beispiel wird gezeigt, wie einem Aktivitätsdesigner erstellt wird, Flächen solche "Ablagezone."</span><span class="sxs-lookup"><span data-stu-id="8c970-104">This sample shows how to build an activity designer that surfaces such a "drop zone."</span></span>  
  
 <span data-ttu-id="8c970-105">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8c970-105">This sample demonstrates:</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="8c970-106">Veranschaulicht</span><span class="sxs-lookup"><span data-stu-id="8c970-106">Demonstrates</span></span>  
  
-   <span data-ttu-id="8c970-107">Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="8c970-107">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
-   <span data-ttu-id="8c970-108">Registrieren des benutzerdefinierten Designers mithilfe des Metadatenspeichers.</span><span class="sxs-lookup"><span data-stu-id="8c970-108">Registering the custom designer using the metadata store.</span></span>  
  
-   <span data-ttu-id="8c970-109">Deklaratives und imperatives Programmieren der neu gehosteten Toolbox.</span><span class="sxs-lookup"><span data-stu-id="8c970-109">Programming the rehosted toolbox declaratively and imperatively.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="8c970-110">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="8c970-110">Sample Details</span></span>  
 <span data-ttu-id="8c970-111">Der Code für dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8c970-111">The code for this sample shows:</span></span>  
  
-   <span data-ttu-id="8c970-112">Der benutzerdefinierte Aktivitätsdesigner wird für die `SimpleNativeActivity`-Klasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="8c970-112">The custom activity designer is built for the `SimpleNativeActivity` class.</span></span>  
  
-   <span data-ttu-id="8c970-113">Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span><span class="sxs-lookup"><span data-stu-id="8c970-113">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemPresenter>.</span></span>  
  
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
  
 <span data-ttu-id="8c970-114">Beachten Sie die Verwendung der WPF-Datenbindung, um eine Bindung an `ModelItem.Body` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c970-114">Note the use of WPF data binding to bind to `ModelItem.Body`.</span></span> <span data-ttu-id="8c970-115">`ModelItem`ist die Eigenschaft im <xref:System.Activities.Presentation.ActivityDesigner> , die auf das zugrunde liegende Objekt, das der Designer wird, in diesem Fall verwendet wird verweist **SimpleNativeActivity**.</span><span class="sxs-lookup"><span data-stu-id="8c970-115">`ModelItem` is the property on <xref:System.Activities.Presentation.ActivityDesigner> that refers to the underlying object the designer is being used for, in this case, **SimpleNativeActivity**.</span></span>  
  
#### <a name="to-setup-build-and-run-the-sample"></a><span data-ttu-id="8c970-116">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="8c970-116">To setup, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8c970-117">Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c970-117">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="8c970-118">Drücken Sie F5, um die Anwendung zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c970-118">Press F5 to compile and run the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c970-119">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8c970-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8c970-120">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8c970-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8c970-121">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="8c970-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8c970-122">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8c970-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="8c970-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c970-123">See Also</span></span>  
 <xref:System.Activities.Presentation.WorkflowItemPresenter>  
 [<span data-ttu-id="8c970-124">Entwickeln von Anwendungen mit dem Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="8c970-124">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
