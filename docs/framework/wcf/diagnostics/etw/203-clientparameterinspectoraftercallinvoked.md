---
title: 203 - ClientParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9592212-07e2-43e0-8b00-affd195cf55a
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1173aaa4bf01b324c8cd6088cd5646bc67f08c72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="203---clientparameterinspectoraftercallinvoked"></a><span data-ttu-id="f0b3b-102">203 - ClientParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="f0b3b-102">203 - ClientParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="f0b3b-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0b3b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0b3b-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0b3b-104">ID</span></span>|<span data-ttu-id="f0b3b-105">203</span><span class="sxs-lookup"><span data-stu-id="f0b3b-105">203</span></span>|  
|<span data-ttu-id="f0b3b-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f0b3b-106">Keywords</span></span>|<span data-ttu-id="f0b3b-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0b3b-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f0b3b-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="f0b3b-108">Level</span></span>|<span data-ttu-id="f0b3b-109">Information</span><span class="sxs-lookup"><span data-stu-id="f0b3b-109">Information</span></span>|  
|<span data-ttu-id="f0b3b-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="f0b3b-110">Channel</span></span>|<span data-ttu-id="f0b3b-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="f0b3b-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0b3b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b3b-112">Description</span></span>  
 <span data-ttu-id="f0b3b-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem Clientparameterinspektor aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a client parameter inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0b3b-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="f0b3b-114">Message</span></span>  
 <span data-ttu-id="f0b3b-115">Der Verteiler hat 'AfterCall' auf einem ClientParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-115">The Dispatcher invoked 'AfterCall' on a ClientParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0b3b-116">Details</span><span class="sxs-lookup"><span data-stu-id="f0b3b-116">Details</span></span>  
  
|<span data-ttu-id="f0b3b-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="f0b3b-117">Data Item Name</span></span>|<span data-ttu-id="f0b3b-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="f0b3b-118">Data Item Type</span></span>|<span data-ttu-id="f0b3b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0b3b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0b3b-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="f0b3b-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="f0b3b-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="f0b3b-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="f0b3b-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="f0b3b-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f0b3b-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="f0b3b-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f0b3b-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f0b3b-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0b3b-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f0b3b-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f0b3b-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
