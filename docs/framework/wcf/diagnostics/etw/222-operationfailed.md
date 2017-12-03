---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="44abf-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="44abf-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="44abf-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="44abf-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="44abf-104">ID</span><span class="sxs-lookup"><span data-stu-id="44abf-104">ID</span></span>|<span data-ttu-id="44abf-105">222</span><span class="sxs-lookup"><span data-stu-id="44abf-105">222</span></span>|  
|<span data-ttu-id="44abf-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="44abf-106">Keywords</span></span>|<span data-ttu-id="44abf-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="44abf-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="44abf-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="44abf-108">Level</span></span>|<span data-ttu-id="44abf-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="44abf-109">Warning</span></span>|  
|<span data-ttu-id="44abf-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="44abf-110">Channel</span></span>|<span data-ttu-id="44abf-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="44abf-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="44abf-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44abf-112">Description</span></span>  
 <span data-ttu-id="44abf-113">Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells beim Aufrufen der Methode auf eine Ausnahme gestoßen ist.</span><span class="sxs-lookup"><span data-stu-id="44abf-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="44abf-114">Beachten Sie, dass von `FaultException` abgeleitete Ausnahmen bewirken, dass dieses Ereignis nicht ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="44abf-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="44abf-115">Meldung</span><span class="sxs-lookup"><span data-stu-id="44abf-115">Message</span></span>  
 <span data-ttu-id="44abf-116">Die '%1'-Methode hat beim Aufrufen durch den OperationInvoker eine nicht behandelte Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="44abf-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="44abf-117">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="44abf-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="44abf-118">Details</span><span class="sxs-lookup"><span data-stu-id="44abf-118">Details</span></span>  
  
|<span data-ttu-id="44abf-119">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="44abf-119">Data Item Name</span></span>|<span data-ttu-id="44abf-120">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="44abf-120">Data Item Type</span></span>|<span data-ttu-id="44abf-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44abf-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="44abf-122">Methodenname</span><span class="sxs-lookup"><span data-stu-id="44abf-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="44abf-123">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="44abf-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="44abf-124">Dauer</span><span class="sxs-lookup"><span data-stu-id="44abf-124">Duration</span></span>|`xs:long`|<span data-ttu-id="44abf-125">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="44abf-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="44abf-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="44abf-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="44abf-127">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="44abf-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="44abf-128">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="44abf-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="44abf-129">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="44abf-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="44abf-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="44abf-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="44abf-131">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="44abf-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
