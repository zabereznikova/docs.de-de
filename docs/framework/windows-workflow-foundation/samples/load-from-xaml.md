---
title: Laden von XAML
ms.date: 03/30/2017
ms.assetid: 1f103ef6-7bed-4f16-ae52-9e665c5a43d7
ms.openlocfilehash: 3344f8d35400835ed022ba507954f7f962ff75c8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418112"
---
# <a name="load-from-xaml"></a><span data-ttu-id="d7bb3-102">Laden von XAML</span><span class="sxs-lookup"><span data-stu-id="d7bb3-102">Load From XAML</span></span>
<span data-ttu-id="d7bb3-103">In diesem Beispiel wird veranschaulicht, wie ein XAML-Workflow dynamisch geladen wird, ohne das XamlBuildTask-Tool ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-103">This sample demonstrates how to dynamically load a XAML workflow without having to run the XamlBuildTask tool.</span></span> <span data-ttu-id="d7bb3-104">Im Beispiel wird stattdessen die <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-104">Instead, the sample calls the <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="d7bb3-105">Im Beispiel ist eine Windows Presentation Foundation (WPF)-Clientanwendung, die mithilfe von XAML-Workflows lädt die <xref:System.Activities.XamlIntegration.ActivityXamlServices> Klasse und ausführt.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-105">The sample is a Windows Presentation Foundation (WPF) client application that loads XAML workflows using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class and executes them.</span></span> <span data-ttu-id="d7bb3-106">Nach dem Laden mit der <xref:System.Activities.XamlIntegration.ActivityXamlServices>-Klasse wird eine <xref:System.Activities.DynamicActivity%601> zurückgegeben, die ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-106">After they have been loaded using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> class, a <xref:System.Activities.DynamicActivity%601> is returned that can be executed.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="d7bb3-107">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7bb3-107">To use this sample</span></span>  
  
1.  <span data-ttu-id="d7bb3-108">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "LoadFromXAML.sln".</span><span class="sxs-lookup"><span data-stu-id="d7bb3-108">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LoadFromXAML.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d7bb3-109">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-109">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d7bb3-110">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-110">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7bb3-111">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-111">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7bb3-112">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-112">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7bb3-113">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-113">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7bb3-114">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d7bb3-114">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\DynamicActivity\LoadFromXAML`