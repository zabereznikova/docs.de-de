---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09a8dc1994da30c0f0c180640e3f66c8806e4528
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="1e694-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="1e694-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="1e694-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e694-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e694-104">ID</span><span class="sxs-lookup"><span data-stu-id="1e694-104">ID</span></span>|<span data-ttu-id="1e694-105">214</span><span class="sxs-lookup"><span data-stu-id="1e694-105">214</span></span>|  
|<span data-ttu-id="1e694-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="1e694-106">Keywords</span></span>|<span data-ttu-id="1e694-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1e694-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1e694-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="1e694-108">Level</span></span>|<span data-ttu-id="1e694-109">Information</span><span class="sxs-lookup"><span data-stu-id="1e694-109">Information</span></span>|  
|<span data-ttu-id="1e694-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="1e694-110">Channel</span></span>|<span data-ttu-id="1e694-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="1e694-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1e694-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e694-112">Description</span></span>  
 <span data-ttu-id="1e694-113">Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells das Aufrufen einer Methode abgeschlossen hat, ohne dass diese Methode eine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="1e694-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1e694-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="1e694-114">Message</span></span>  
 <span data-ttu-id="1e694-115">Ein OperationInvoker hat den Aufruf der '%1'-Methode abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1e694-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="1e694-116">Die Methodenaufrufdauer betrug '%2' ms.</span><span class="sxs-lookup"><span data-stu-id="1e694-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1e694-117">Details</span><span class="sxs-lookup"><span data-stu-id="1e694-117">Details</span></span>  
  
|<span data-ttu-id="1e694-118">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="1e694-118">Data Item Name</span></span>|<span data-ttu-id="1e694-119">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="1e694-119">Data Item Type</span></span>|<span data-ttu-id="1e694-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1e694-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1e694-121">Methodenname</span><span class="sxs-lookup"><span data-stu-id="1e694-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="1e694-122">Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="1e694-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="1e694-123">Dauer</span><span class="sxs-lookup"><span data-stu-id="1e694-123">Duration</span></span>|`xs:long`|<span data-ttu-id="1e694-124">Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.</span><span class="sxs-lookup"><span data-stu-id="1e694-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="1e694-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="1e694-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="1e694-126">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="1e694-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1e694-127">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="1e694-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1e694-128">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1e694-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1e694-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1e694-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1e694-130">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1e694-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
