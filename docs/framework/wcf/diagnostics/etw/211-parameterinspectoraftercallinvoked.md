---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69a9b6fe30a4ffa7f72e70b5aef740b2b772dd69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="7e5af-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="7e5af-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="7e5af-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7e5af-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e5af-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e5af-104">ID</span></span>|<span data-ttu-id="7e5af-105">211</span><span class="sxs-lookup"><span data-stu-id="7e5af-105">211</span></span>|  
|<span data-ttu-id="7e5af-106">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7e5af-106">Keywords</span></span>|<span data-ttu-id="7e5af-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7e5af-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7e5af-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7e5af-108">Level</span></span>|<span data-ttu-id="7e5af-109">Information</span><span class="sxs-lookup"><span data-stu-id="7e5af-109">Information</span></span>|  
|<span data-ttu-id="7e5af-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7e5af-110">Channel</span></span>|<span data-ttu-id="7e5af-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7e5af-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e5af-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e5af-112">Description</span></span>  
 <span data-ttu-id="7e5af-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `AfterCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="7e5af-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e5af-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7e5af-114">Message</span></span>  
 <span data-ttu-id="7e5af-115">Der Verteiler hat 'AfterCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7e5af-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e5af-116">Details</span><span class="sxs-lookup"><span data-stu-id="7e5af-116">Details</span></span>  
  
|<span data-ttu-id="7e5af-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7e5af-117">Data Item Name</span></span>|<span data-ttu-id="7e5af-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7e5af-118">Data Item Type</span></span>|<span data-ttu-id="7e5af-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e5af-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e5af-120">Typname</span><span class="sxs-lookup"><span data-stu-id="7e5af-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="7e5af-121">Der CLR-FullName des aufgerufenen `ParameterInspector`-Typs.</span><span class="sxs-lookup"><span data-stu-id="7e5af-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="7e5af-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="7e5af-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="7e5af-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="7e5af-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7e5af-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="7e5af-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7e5af-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="7e5af-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7e5af-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e5af-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7e5af-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7e5af-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
