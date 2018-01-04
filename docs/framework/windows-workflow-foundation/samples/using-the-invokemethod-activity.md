---
title: "Verwenden der InvokeMethod-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d3f6734f9d6a3b0e2279b2bb6cca71141c8f5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="d68b9-102">Verwenden der InvokeMethod-Aktivität</span><span class="sxs-lookup"><span data-stu-id="d68b9-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="d68b9-103">Dieses Beispiel veranschaulicht, wie die <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Aktivität, um öffentliche Methoden in öffentlichen Klassen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="d68b9-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="d68b9-104">Die <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) -Aktivität ermöglicht einem Workflow, Methoden für Objekte aufzurufen, Parameter zu übergeben, den Rückgabewert abzurufen, Typen für generische Methoden anzugeben und anzugeben, ob die Methode synchron ist oder asynchrone.</span><span class="sxs-lookup"><span data-stu-id="d68b9-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="d68b9-105">Ist eine nicht generische Version der der <xref:System.Activities.Statements.InvokeMethod> Aktivität, die der Rückgabewert auf festgelegt ist, die <xref:System.Activities.Statements.InvokeMethod.Result%2A> -Eigenschaft und eine generische Version von der <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) Aktivität, die der Rückgabewert zurückgegeben, über die <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) Eigenschaft vom Typ `TResult`.</span><span class="sxs-lookup"><span data-stu-id="d68b9-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="d68b9-106">In diesem Beispiel wird veranschaulicht, wie verschiedene Methodentypen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d68b9-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="d68b9-107">In der folgenden Liste sind die in diesem Beispiel veranschaulichten Methodentypen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d68b9-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="d68b9-108">Rufen Sie eine Instanzmethode ohne Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="d68b9-109">Rufen Sie eine Instanzmethode mit zwei Parametern (System.String und System.Int32) auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="d68b9-110">Rufen Sie eine Instanzmethode mit zwei Parametern (System.String und System.Int32) und einem Parameterarray vom Typ System.String[] auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="d68b9-111">Rufen Sie eine Instanzmethode mit zwei Parametern (zwei System.Int32-Nummern) und einem Ergebnis vom Typ System.Int32 auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="d68b9-112">Der Rückgabewert ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d68b9-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="d68b9-113">Rufen Sie eine statische Methode mit zwei Parametern (System.String und System.Int32) auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="d68b9-114">Rufen Sie eine Instanzmethode mit einem generischen Parameter (System.String) auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="d68b9-115">Rufen Sie eine statische Methode mit zwei generischen Parametern (System.String und System.Int32) auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="d68b9-116">Rufen Sie eine Instanzmethode auf, bei der ein Parameter als Verweis übergeben wird (System.String).</span><span class="sxs-lookup"><span data-stu-id="d68b9-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="d68b9-117">Der Parameter, auf den verwiesen wird, ist an eine Variable gebunden und wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d68b9-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="d68b9-118">Rufen Sie eine asynchrone Instanzmethode auf.</span><span class="sxs-lookup"><span data-stu-id="d68b9-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="d68b9-119">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="d68b9-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="d68b9-120">Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei InvokeMethodUsage.sln.</span><span class="sxs-lookup"><span data-stu-id="d68b9-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="d68b9-121">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d68b9-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="d68b9-122">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d68b9-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d68b9-123">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d68b9-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d68b9-124">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d68b9-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d68b9-125">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="d68b9-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d68b9-126">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d68b9-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`