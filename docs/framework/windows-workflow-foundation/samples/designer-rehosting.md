---
title: Erneutes Hosten von Designern
ms.date: 03/30/2017
ms.assetid: b676ad31-5f64-4d84-9a36-b4d7113a2f4d
ms.openlocfilehash: 1901df62ccdeec3f75ce0d8cd85484f46fac4541
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404099"
---
# <a name="designer-rehosting"></a><span data-ttu-id="af4e1-102">Erneutes Hosten von Designern</span><span class="sxs-lookup"><span data-stu-id="af4e1-102">Designer ReHosting</span></span>
<span data-ttu-id="af4e1-103">Das erneute Hosten des Designers ist ein allgemeines Szenario, das sich auf das Hosting des Entwurfszeichnungsbereichs des Workflows in einer benutzerdefinierten Anwendung bezieht.</span><span class="sxs-lookup"><span data-stu-id="af4e1-103">Designer rehosting is a common scenario that refers to hosting the workflow design canvas inside of a custom application.</span></span> <span data-ttu-id="af4e1-104">Die Hostinganwendung, mit der die meisten Personen vertraut sind, ist Visual Studio, es gibt jedoch eine Reihe von Szenarien, in denen das Anzeigen des Workflow-Designers in einer Anwendung hilfreich sein kann:</span><span class="sxs-lookup"><span data-stu-id="af4e1-104">The hosting application most people are familiar with is Visual Studio, however there are a number of scenarios where showing the workflow designer in an application may be useful:</span></span>  
  
-   <span data-ttu-id="af4e1-105">Das Überwachen von Anwendungen (die Schaffung von Möglichkeiten für einen Endbenutzer, den Prozess sowie Laufzeitdaten zum Prozess, z. B. die gerade aktiven Zustände, die kombinierten Ausführungszeitdaten oder andere Informationen zu einer Instanz des Workflows, visuell darzustellen).</span><span class="sxs-lookup"><span data-stu-id="af4e1-105">Monitoring applications (allowing an end user to visualize the process, as well as runtime data about the process such as the currently active state, aggregate execution time data, or other information about an instance of the workflow).</span></span>  
  
-   <span data-ttu-id="af4e1-106">Anwendungen, die es einem Benutzer ermöglichen, den Prozess mit einem beschränkten Satz von Aktivitäten anzupassen.</span><span class="sxs-lookup"><span data-stu-id="af4e1-106">Applications that allow a user to customize the process with a limited set of activities.</span></span>  
  
 <span data-ttu-id="af4e1-107">Zur Unterstützung dieser Anwendungstypen wird der Workflow-Designer als Bestandteil von .NET Framework ausgeliefert und kann in einer WPF-Anwendung oder in einer WinForms-Anwendung mit dem entsprechenden WPF-Hostingcode gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="af4e1-107">To support these types of applications, the workflow designer ships inside the .NET Framework, and can be hosted inside a WPF application, or in a WinForms application with the appropriate WPF hosting code.</span></span> <span data-ttu-id="af4e1-108">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="af4e1-108">This sample demonstrates:</span></span>  
  
-   <span data-ttu-id="af4e1-109">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="af4e1-109">Rehosting the WF designer.</span></span>  
  
-   <span data-ttu-id="af4e1-110">Verwenden der neu gehosteten Toolbox und auch des Eigenschaftenrasters.</span><span class="sxs-lookup"><span data-stu-id="af4e1-110">Using the rehosted toolbox and property grid as well.</span></span>  
  
## <a name="rehosting-the-designer"></a><span data-ttu-id="af4e1-111">Erneutes Hosten des Workflow-Designers</span><span class="sxs-lookup"><span data-stu-id="af4e1-111">Rehosting the designer</span></span>  
 <span data-ttu-id="af4e1-112">In diesem Beispiel wird veranschaulicht, wie das WPF-Layout so erstellt wird, dass es den Designer enthält, wie im folgenden Rasterlayout dargestellt (der Toolboxcode wurde aus Platzgründen weggelassen).</span><span class="sxs-lookup"><span data-stu-id="af4e1-112">This sample shows how to create the WPF layout to contain the designer, seen in the following grid layout (Toolbox code omitted for space concerns).</span></span> <span data-ttu-id="af4e1-113">Beachten Sie die Benennung der Rahmen, die den Designer und das Eigenschaftenraster enthalten.</span><span class="sxs-lookup"><span data-stu-id="af4e1-113">Note the naming of the borders which contain the designer and property grid.</span></span>  
  
```xaml  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition Width="2*"/>  
        <ColumnDefinition Width="7*"/>  
        <ColumnDefinition Width="3*"/>  
    </Grid.ColumnDefinitions>  
    <Border Grid.Column="0">  
        <sapt:ToolboxControl>...</sapt:ToolboxControl>  
    </Border>  
    <Border Grid.Column="1" Name="DesignerBorder"/>  
    <Border Grid.Column="2" Name="PropertyBorder"/>  
</Grid>  
```  
  
 <span data-ttu-id="af4e1-114">Im Beispiel wird dann der Designer erstellt und seine primäre <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> und <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> dem entsprechenden Container in der Benutzeroberfläche zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="af4e1-114">Next the sample creates the designer, and associates its primary <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> with the appropriate container in the user interface.</span></span> <span data-ttu-id="af4e1-115">Im folgenden Beispiel gibt es einige zusätzliche Codezeilen, die einer Erläuterung bedürfen.</span><span class="sxs-lookup"><span data-stu-id="af4e1-115">There are a few additional lines of code in the following example that merit some explanation.</span></span> <span data-ttu-id="af4e1-116">Der <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A>-Aufruf ist erforderlich, um die Standardaktivitätsdesigner für die Aktivitäten zuzuordnen, die im Lieferumfang von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="af4e1-116">The <xref:System.Activities.Core.Presentation.DesignerMetadata.Register%2A> call is required to associate the default activity designers for the activities shipped with [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="af4e1-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> wird aufgerufen, um das zu bearbeitende WF-Element zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="af4e1-117"><xref:System.Activities.Presentation.WorkflowDesigner.Load%2A> is called to pass in the WF item to be edited.</span></span> <span data-ttu-id="af4e1-118">Schließlich werden die <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primärer Zeichnungsbereich) und die <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (Eigenschaftenraster) auf der Benutzeroberfläche platziert.</span><span class="sxs-lookup"><span data-stu-id="af4e1-118">Finally, the <xref:System.Activities.Presentation.WorkflowDesigner.View%2A> (primary canvas) and <xref:System.Activities.Presentation.WorkflowDesigner.PropertyInspectorView%2A> (property grid) are placed onto the user interface surface.</span></span>  
  
```csharp  
protected override void OnInitialized(EventArgs e)  
{  
   base.OnInitialized(e);  
   // register metadata  
   (new DesignerMetadata()).Register();  
  
   // create the workflow designer  
   WorkflowDesigner wd = new WorkflowDesigner();  
   wd.Load(new Sequence());  
   DesignerBorder.Child = wd.View;  
   PropertyBorder.Child = wd.PropertyInspectorView;  
}  
```  
  
## <a name="using-the-rehosted-toolbox"></a><span data-ttu-id="af4e1-119">Verwenden der neu gehosteten Toolbox</span><span class="sxs-lookup"><span data-stu-id="af4e1-119">Using the rehosted toolbox</span></span>  
 <span data-ttu-id="af4e1-120">In diesem Beispiel wird das neu gehostete Toolboxsteuerelement deklarativ in XAML verwendet.</span><span class="sxs-lookup"><span data-stu-id="af4e1-120">This sample uses the rehosted toolbox control declaratively in XAML.</span></span> <span data-ttu-id="af4e1-121">Beachten Sie, dass in Code ein Typ an den <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper>-Konstruktor übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="af4e1-121">Note that in code, one can pass a type to the <xref:System.Activities.Presentation.Toolbox.ToolboxItemWrapper> constructor.</span></span>  
  
```xaml  
<!-- Copyright (c) Microsoft Corporation. All rights reserved-->  
<Window x:Class="Microsoft.Samples.DesignerRehosting.RehostingWfDesigner"  
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
            <sapt:ToolboxControl>  
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
  
#### <a name="using-the-sample"></a><span data-ttu-id="af4e1-122">Verwenden des Beispiels</span><span class="sxs-lookup"><span data-stu-id="af4e1-122">Using the sample</span></span>  
  
1.  <span data-ttu-id="af4e1-123">Öffnen Sie die Projektmappe DesignerRehosting.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af4e1-123">Open the DesignerRehosting.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="af4e1-124">Drücken Sie F5, um die Anwendung zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af4e1-124">Press F5 to compile and run the application.</span></span>  
  
3.  <span data-ttu-id="af4e1-125">Eine WPF-Anwendung beginnt mit einem neu gehosteten Designer.</span><span class="sxs-lookup"><span data-stu-id="af4e1-125">A WPF application starts with a rehosted designer.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="af4e1-126">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="af4e1-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="af4e1-127">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="af4e1-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="af4e1-128">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="af4e1-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="af4e1-129">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="af4e1-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\DesignerRehosting\Basic`