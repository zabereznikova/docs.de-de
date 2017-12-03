---
title: 223 - OperationFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0428d90135823761e7b8a12f560786e34e12734
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="223---operationfaulted"></a><span data-ttu-id="328ce-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="328ce-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="328ce-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="328ce-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="328ce-104">ID</span><span class="sxs-lookup"><span data-stu-id="328ce-104">ID</span></span>|<span data-ttu-id="328ce-105">223</span><span class="sxs-lookup"><span data-stu-id="328ce-105">223</span></span>|  
|<span data-ttu-id="328ce-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="328ce-106">Keywords</span></span>|<span data-ttu-id="328ce-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="328ce-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="328ce-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="328ce-108">Level</span></span>|<span data-ttu-id="328ce-109">Warnung</span><span class="sxs-lookup"><span data-stu-id="328ce-109">Warning</span></span>|  
|<span data-ttu-id="328ce-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="328ce-110">Channel</span></span>|<span data-ttu-id="328ce-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="328ce-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="328ce-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="328ce-112">Description</span></span>  
 <span data-ttu-id="328ce-113">Dieses Ereignis wird ausgegeben, wenn beim Aufrufen der Methode der standardmäßige `OperationInvoker` des Dienstmodells auf eine Ausnahme gestoßen ist, die von `FaultException` abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="328ce-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="328ce-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="328ce-114">Message</span></span>  
 <span data-ttu-id="328ce-115">Die '%1'-Methode hat beim Aufrufen von OperationInvoker eine FaultException ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="328ce-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="328ce-116">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="328ce-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="328ce-117">Details</span><span class="sxs-lookup"><span data-stu-id="328ce-117">Details</span></span>  
  
|<span data-ttu-id="328ce-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="328ce-118">Data Item Name</span></span>|<span data-ttu-id="328ce-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="328ce-119">Data Item Type</span></span>|<span data-ttu-id="328ce-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="328ce-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="328ce-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="328ce-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="328ce-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="328ce-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="328ce-123">Dauer</span><span class="sxs-lookup"><span data-stu-id="328ce-123">Duration</span></span>|`xs:long`|<span data-ttu-id="328ce-124">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="328ce-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="328ce-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="328ce-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="328ce-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="328ce-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="328ce-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="328ce-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="328ce-128">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="328ce-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="328ce-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="328ce-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="328ce-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="328ce-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
