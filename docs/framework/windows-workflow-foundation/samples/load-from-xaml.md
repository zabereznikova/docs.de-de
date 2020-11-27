---
title: Laden von XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: ebf6ebe1001773768d8da318a0d6b68d50c7848c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283561"
---
# <a name="load-from-xaml"></a><span data-ttu-id="76448-102">Laden von XAML</span><span class="sxs-lookup"><span data-stu-id="76448-102">Load From XAML</span></span>

<span data-ttu-id="76448-103">In diesem Beispiel wird veranschaulicht, wie ein XAML-Workflow dynamisch geladen wird, ohne das XamlBuildTask-Tool ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="76448-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="76448-104">Im Beispiel wird stattdessen die <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="76448-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="76448-105">Bei dem Beispiel handelt es sich um eine WPF-Client Anwendung (Windows Presentation Foundation), die XAML-Workflows mithilfe der <xref:System.Activities.XamlIntegration.ActivityXamlServices> -Klasse lädt und ausführt.</span><span class="sxs-lookup"><span data-stu-id="76448-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="76448-106">Nach dem Laden mit der <xref:System.Activities.XamlIntegration.ActivityXamlServices>-Klasse wird eine <xref:System.Activities.DynamicActivity%601> zurückgegeben, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="76448-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="76448-107">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="76448-107">To use this sample</span></span>

1. <span data-ttu-id="76448-108">Öffnen Sie mit Visual Studio 2010 die Projektmappendatei "loadfromxaml. sln".</span><span class="sxs-lookup"><span data-stu-id="76448-108">Using Visual Studio 2010, open the LoadFromXAML.sln solution file.</span></span>

2. <span data-ttu-id="76448-109">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="76448-109">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="76448-110">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="76448-110">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76448-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="76448-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="76448-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="76448-112">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="76448-113">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="76448-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="76448-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="76448-114">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`
