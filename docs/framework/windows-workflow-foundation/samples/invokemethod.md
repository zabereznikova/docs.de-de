---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b90ebec929b310442cde2be8d96386e016a9bbb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="invokemethod"></a><span data-ttu-id="58130-102">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="58130-102">InvokeMethod</span></span>
<span data-ttu-id="58130-103">In diesem Beispiel werden die verschiedenen Möglichkeiten zum Aufrufen von Methoden einer Klasse mit der <xref:System.Activities.Statements.InvokeMethod>-Aktivität veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="58130-103">This sample shows the different ways of using the <xref:System.Activities.Statements.InvokeMethod> activity to invoke methods of a class.</span></span>  
  
 <span data-ttu-id="58130-104">Eine Methode gehört zu einer Klasse und stellt eine in sich abgeschlossene Gruppe von Vorgängen dar.</span><span class="sxs-lookup"><span data-stu-id="58130-104">A method belongs to a class and represents a contained set of operations.</span></span> <span data-ttu-id="58130-105">Mit der <xref:System.Activities.Statements.InvokeMethod>-Aktivität können Sie Methoden für Objekte oder Typen aufrufen, Parameter übergeben und den Rückgabewert abrufen.</span><span class="sxs-lookup"><span data-stu-id="58130-105">The <xref:System.Activities.Statements.InvokeMethod> activity gives you the ability to call methods against objects or types, pass in parameters, and get the return value.</span></span> <span data-ttu-id="58130-106">Methoden können synchron oder asynchron aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="58130-106">Methods can be invoked synchronously or asynchronously.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="58130-107">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="58130-107">Sample Details</span></span>  
 <span data-ttu-id="58130-108">In diesem Beispiel werden die folgenden Szenarios mit der <xref:System.Activities.Statements.InvokeMethod>-Aktivität ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="58130-108">This sample uses the <xref:System.Activities.Statements.InvokeMethod> activity to perform the following scenarios:</span></span>  
  
1.  <span data-ttu-id="58130-109">Rufen Sie eine Instanzmethode ohne Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="58130-109">Invoke an instance method without parameters.</span></span>  
  
2.  <span data-ttu-id="58130-110">Aufrufen einer Instanzmethode mit zwei Parametern (<xref:System.String> und <xref:System.Int32>).</span><span class="sxs-lookup"><span data-stu-id="58130-110">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>).</span></span>  
  
3.  <span data-ttu-id="58130-111">Aufrufen einer Instanzmethode mit zwei Parametern (<xref:System.String> und <xref:System.Int32>) und einem Parameterarray vom Typ <xref:System.String>[].</span><span class="sxs-lookup"><span data-stu-id="58130-111">Invoke an instance method with two parameters (<xref:System.String> and <xref:System.Int32>) and a parameter array of type <xref:System.String>[].</span></span>  
  
4.  <span data-ttu-id="58130-112">Aufrufen einer Instanzmethode mit zwei Parametern vom Typ <xref:System.Int32> und einem Ergebnis vom Typ <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="58130-112">Invoke an instance method with two parameters of type <xref:System.Int32> and a result of type <xref:System.Int32>.</span></span> <span data-ttu-id="58130-113">In diesem Szenario wird der Ergebniswert an eine Variable gebunden und in einer anderen Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="58130-113">In this scenario, the result value is bound to a variable and used in another activity.</span></span> <span data-ttu-id="58130-114">Der Wert wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58130-114">It is displayed in the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
5.  <span data-ttu-id="58130-115">Aufrufen einer statischen Methode mit zwei Parametern vom Typ <xref:System.String> und <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="58130-115">Invoke a static method with two parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
6.  <span data-ttu-id="58130-116">Aufrufen einer Instanzmethode mit einem generischen Parameter vom Typ <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="58130-116">Invoke an instance method with one generic parameter of type <xref:System.String>.</span></span>  
  
7.  <span data-ttu-id="58130-117">Aufrufen einer statischen Methode mit zwei generischen Parametern vom Typ <xref:System.String> und <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="58130-117">Invoke a static method with two generic parameters of type <xref:System.String> and <xref:System.Int32>.</span></span>  
  
8.  <span data-ttu-id="58130-118">Aufrufen einer Instanzmethode mit einem als Verweis übergebenen Parameter vom Typ <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="58130-118">Invoke an instance method that has one parameter passed by reference of type <xref:System.String>.</span></span> <span data-ttu-id="58130-119">In diesem Szenario wird der Verweisparameter an eine Variable (`outParam`) gebunden und in einer anderen Aktivität verwendet.</span><span class="sxs-lookup"><span data-stu-id="58130-119">In this scenario, the reference parameter is bound to a variable (`outParam`) and used in another activity.</span></span> <span data-ttu-id="58130-120">Der Wert wird mit der <xref:System.Activities.Statements.WriteLine>-Aktivität in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58130-120">It is displayed on the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
9. <span data-ttu-id="58130-121">Rufen Sie eine asynchrone Instanzmethode auf.</span><span class="sxs-lookup"><span data-stu-id="58130-121">Invoke an asynchronous instance method.</span></span>  
  
10. <span data-ttu-id="58130-122">Aufrufen von zwei unterschiedlichen Methoden für dieselbe Instanz eines Objekts mit zwei <xref:System.Activities.Statements.InvokeMethod>-Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="58130-122">Invoke two different methods on the same instance of an object using two <xref:System.Activities.Statements.InvokeMethod> activities.</span></span>  
  
11. <span data-ttu-id="58130-123">Speichern eines Werts in einer Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="58130-123">Store a value in an instance of an object.</span></span>  
  
12. <span data-ttu-id="58130-124">Abrufen eines Werts aus einer Objektinstanz.</span><span class="sxs-lookup"><span data-stu-id="58130-124">Retrieve a value from an instance of an object.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="58130-125">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="58130-125">To use this sample</span></span>  
 <span data-ttu-id="58130-126">Dieses Beispiel wird in zwei Versionen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="58130-126">This sample is provided in two versions.</span></span> <span data-ttu-id="58130-127">Die erste Version dieses Beispiels veranschaulicht die Verwendung von <xref:System.Activities.Statements.InvokeMethod> mit C#-Code und dem [!INCLUDE[wf](../../../../includes/wf-md.md)]-Programmiermodell und befindet sich im Ordner "CodedWorkflow\CS".</span><span class="sxs-lookup"><span data-stu-id="58130-127">The first version of this sample demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> through C# code using the [!INCLUDE[wf](../../../../includes/wf-md.md)] programming model and can be found under the CodedWorkflow\CS folder.</span></span> <span data-ttu-id="58130-128">Die zweite Version veranschaulicht die Verwendung von <xref:System.Activities.Statements.InvokeMethod> mit XAML und befindet sich im Ordner "DesignerWorkflow\CS".</span><span class="sxs-lookup"><span data-stu-id="58130-128">The second version demonstrates the usage of <xref:System.Activities.Statements.InvokeMethod> using XAML and can be found under the DesignerWorkflow\CS folder.</span></span>  
  
#### <a name="to-run-the-coded-workflow-sample"></a><span data-ttu-id="58130-129">So führen Sie das Codebeispiel aus</span><span class="sxs-lookup"><span data-stu-id="58130-129">To run the coded workflow sample</span></span>  
  
1.  <span data-ttu-id="58130-130">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InvokeMethodUsage.sln" im Ordner "CodedWorkflow\CS".</span><span class="sxs-lookup"><span data-stu-id="58130-130">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the CodedWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="58130-131">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58130-131">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="58130-132">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58130-132">To run the solution, press CTRL+F5.</span></span>  
  
#### <a name="to-run-the-designer-workflow-sample"></a><span data-ttu-id="58130-133">So führen Sie das XAML-Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="58130-133">To run the designer workflow sample</span></span>  
  
1.  <span data-ttu-id="58130-134">Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "InvokeMethodUsage.sln" im Ordner "DesignerWorkflow\CS".</span><span class="sxs-lookup"><span data-stu-id="58130-134">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file in the DesignerWorkflow\CS folder.</span></span>  
  
2.  <span data-ttu-id="58130-135">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="58130-135">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="58130-136">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58130-136">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="58130-137">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="58130-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="58130-138">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="58130-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="58130-139">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="58130-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="58130-140">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="58130-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`