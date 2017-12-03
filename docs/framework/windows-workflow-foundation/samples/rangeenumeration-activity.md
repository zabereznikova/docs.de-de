---
title: "RangeEnumeration-Aktivität"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca5b78f4-94fa-4aa7-830d-26039ac422c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0327ca08764f35550be47c4efa111b00d16b0b5d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="rangeenumeration-activity"></a><span data-ttu-id="2a33d-102">RangeEnumeration-Aktivität</span><span class="sxs-lookup"><span data-stu-id="2a33d-102">RangeEnumeration Activity</span></span>
<span data-ttu-id="2a33d-103">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die eine Auflistung von Zahlen durchläuft. In der folgenden Tabelle sind die wichtigsten in dem Beispiel enthaltenen Dateien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2a33d-103">This sample demonstrates how to create a custom activity that iterates over a collection of numbers.The following table details the main files included in the sample.</span></span>  
  
|<span data-ttu-id="2a33d-104">Dateiname</span><span class="sxs-lookup"><span data-stu-id="2a33d-104">File name</span></span>|<span data-ttu-id="2a33d-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a33d-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a33d-106">RangeEnumeration.cs</span><span class="sxs-lookup"><span data-stu-id="2a33d-106">RangeEnumeration.cs</span></span>|<span data-ttu-id="2a33d-107">Definiert eine benutzerdefinierte Aktivität mit dem Namen `RangeEnumeration`, die die<xref:System.Activities.NativeActivity>-Klasse überschreibt und eine Reihe von Zahlen durchläuft.</span><span class="sxs-lookup"><span data-stu-id="2a33d-107">Defines a custom activity named `RangeEnumeration` that overrides the <xref:System.Activities.NativeActivity> class and loops through a series of numbers.</span></span>|  
|<span data-ttu-id="2a33d-108">RangeEnumerationSample.cs</span><span class="sxs-lookup"><span data-stu-id="2a33d-108">RangeEnumerationSample.cs</span></span>|<span data-ttu-id="2a33d-109">Eine Clientanwendung, die die `RangeEnumeration`-Aktivität verwendet, um eine Auflistung von Zahlen zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="2a33d-109">A client application that uses the `RangeEnumeration` activity to iterate over a collection of numbers.</span></span>|  
  
 <span data-ttu-id="2a33d-110">In der folgenden Tabelle sind die Eigenschaften der `RangeEnumeration`-Aktivität aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2a33d-110">The following table details the properties of the `RangeEnumeration` activity.</span></span>  
  
|<span data-ttu-id="2a33d-111">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2a33d-111">Property</span></span>|<span data-ttu-id="2a33d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a33d-112">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="2a33d-113">Starten</span><span class="sxs-lookup"><span data-stu-id="2a33d-113">Start</span></span>|<span data-ttu-id="2a33d-114">Die Ganzzahl, bei der die Schleife gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2a33d-114">The integer to start the loop from.</span></span>|  
|<span data-ttu-id="2a33d-115">Stop</span><span class="sxs-lookup"><span data-stu-id="2a33d-115">Stop</span></span>|<span data-ttu-id="2a33d-116">Die Ganzzahl, bei der die Schleife beendet wird.</span><span class="sxs-lookup"><span data-stu-id="2a33d-116">The integer to stop the loop at.</span></span>|  
|<span data-ttu-id="2a33d-117">Schritt</span><span class="sxs-lookup"><span data-stu-id="2a33d-117">Step</span></span>|<span data-ttu-id="2a33d-118">Gibt den Umfang für jedes Durchlaufen an.</span><span class="sxs-lookup"><span data-stu-id="2a33d-118">Specifies how much to iterate each time.</span></span>|  
|<span data-ttu-id="2a33d-119">Body</span><span class="sxs-lookup"><span data-stu-id="2a33d-119">Body</span></span>|<span data-ttu-id="2a33d-120">Gibt den während jeder Iteration auszuführenden Code an.</span><span class="sxs-lookup"><span data-stu-id="2a33d-120">Specifies the code to execute during each iteration.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="2a33d-121">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="2a33d-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="2a33d-122">Öffnen Sie die Projektmappendatei "RangeEnumeration.sln" in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a33d-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the RangeEnumeration.sln solution file.</span></span>  
  
2.  <span data-ttu-id="2a33d-123">Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2a33d-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="2a33d-124">Drücken Sie STRG+F5, um die Projektmappe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2a33d-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a33d-125">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="2a33d-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2a33d-126">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2a33d-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2a33d-127">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="2a33d-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2a33d-128">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2a33d-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\RangeEnumeration`