---
title: Verwenden der WorkflowInvoker-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="7354a-102">Verwenden der WorkflowInvoker-Klasse</span><span class="sxs-lookup"><span data-stu-id="7354a-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="7354a-103">Dieses Beispiel veranschaulicht, wie die <xref:System.Activities.WorkflowInvoker>-Klasse verwendet wird, um eine Aktivität wie eine Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7354a-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="7354a-104">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="7354a-104">Sample Details</span></span>  
 <span data-ttu-id="7354a-105">Die Verwendung der <xref:System.Activities.WorkflowInvoker>-Klasse ist die einfachste Möglichkeit, eine Aktivität auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7354a-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="7354a-106">Damit kann eine Aktivität direkt ausgeführt werden, als ob es sich um einen Methodenaufruf handeln würde.</span><span class="sxs-lookup"><span data-stu-id="7354a-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="7354a-107">Dabei handelt es sich um eine schlanke, leistungsstarke und benutzerfreundliche API, die für Szenarios verwendet werden kann, in denen die Ausführung einer Aktivität nicht die von anderen Hostingvarianten bereitgestellte Steuerungsinfrastruktur erfordert.</span><span class="sxs-lookup"><span data-stu-id="7354a-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="7354a-108">Das Beispiel verwendet eine benutzerdefinierte Aktivität, die abgeleitet <xref:System.Activities.CodeActivity%601>< Int32\> mit dem Namen `Add` , addiert zwei <xref:System.Activities.InArgument%601>, `X` und `Y`, und gibt eine `Result` <xref:System.Activities.OutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="7354a-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="7354a-109">(<xref:System.Activities.CodeActivity%601>\<T > leitet sich von <xref:System.Activities.Activity%601>< T\>, verfügt über eine <xref:System.Activities.OutArgument%601> \<T > mit dem Namen `Result`.) Ein `Dictionary` \<string, object > wird verwendet, um die Übergabe von Argumenten in einer Aktivität aufgerufen wird, über <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="7354a-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="7354a-110">Der Schlüssel des Wörterbuchs entspricht dem Namen eines Arguments für die aufgerufene Aktivität.</span><span class="sxs-lookup"><span data-stu-id="7354a-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="7354a-111">Der einem bestimmten Schlüssel zugeordnete Wert wird an das durch den Schlüssel identifizierte Argument gebunden.</span><span class="sxs-lookup"><span data-stu-id="7354a-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="7354a-112">Im Beispiel wird <xref:System.Activities.WorkflowInvoker.Invoke%2A> aufgerufen und ein Wörterbuch übergeben, das Werte für `X` und `Y` enthält.</span><span class="sxs-lookup"><span data-stu-id="7354a-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="7354a-113">Die <xref:System.Activities.WorkflowInvoker>-Klasse bindet diese Werte an die Argumente der `Add`-Aktivität, führt die Aktivität aus und gibt das Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="7354a-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7354a-114">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="7354a-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="7354a-115">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "Invoker.sln".</span><span class="sxs-lookup"><span data-stu-id="7354a-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="7354a-116">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7354a-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="7354a-117">Drücken Sie F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7354a-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7354a-118">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7354a-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7354a-119">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7354a-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7354a-120">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7354a-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7354a-121">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7354a-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`