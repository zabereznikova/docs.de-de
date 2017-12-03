---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71fce60ca658c159df11588be149cda17ad2303d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="aa5e6-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="aa5e6-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="aa5e6-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa5e6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa5e6-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa5e6-104">ID</span></span>|<span data-ttu-id="aa5e6-105">207</span><span class="sxs-lookup"><span data-stu-id="aa5e6-105">207</span></span>|  
|<span data-ttu-id="aa5e6-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="aa5e6-106">Keywords</span></span>|<span data-ttu-id="aa5e6-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa5e6-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aa5e6-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="aa5e6-108">Level</span></span>|<span data-ttu-id="aa5e6-109">Information</span><span class="sxs-lookup"><span data-stu-id="aa5e6-109">Information</span></span>|  
|<span data-ttu-id="aa5e6-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="aa5e6-110">Channel</span></span>|<span data-ttu-id="aa5e6-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aa5e6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa5e6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa5e6-112">Description</span></span>  
 <span data-ttu-id="aa5e6-113">Dieses Ereignis wird ausgegeben, nachdem ein `FaultProvider` aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa5e6-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="aa5e6-114">Message</span></span>  
 <span data-ttu-id="aa5e6-115">Der Verteiler hat einen FaultProvider vom Typ '%1' mit einer Ausnahme vom Typ '%2' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa5e6-116">Details</span><span class="sxs-lookup"><span data-stu-id="aa5e6-116">Details</span></span>  
  
|<span data-ttu-id="aa5e6-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="aa5e6-117">Data Item Name</span></span>|<span data-ttu-id="aa5e6-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="aa5e6-118">Data Item Type</span></span>|<span data-ttu-id="aa5e6-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa5e6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa5e6-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="aa5e6-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="aa5e6-121">Der CLR-FullName des aufgerufenen `FaultProvider`-Typs.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="aa5e6-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="aa5e6-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="aa5e6-123">Der CLR-FullName der Ausnahme, die der `FaultProvider` verarbeitet hat.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="aa5e6-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="aa5e6-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="aa5e6-125">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aa5e6-126">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="aa5e6-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aa5e6-127">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aa5e6-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa5e6-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aa5e6-129">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aa5e6-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
