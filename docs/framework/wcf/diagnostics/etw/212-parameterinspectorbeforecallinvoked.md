---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c428c9057e1538cfadb2b02bd05e2d61b4566399
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="7599f-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="7599f-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="7599f-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7599f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7599f-104">Id</span><span class="sxs-lookup"><span data-stu-id="7599f-104">ID</span></span>|<span data-ttu-id="7599f-105">212</span><span class="sxs-lookup"><span data-stu-id="7599f-105">212</span></span>|  
|<span data-ttu-id="7599f-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="7599f-106">Keywords</span></span>|<span data-ttu-id="7599f-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7599f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="7599f-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="7599f-108">Level</span></span>|<span data-ttu-id="7599f-109">Information</span><span class="sxs-lookup"><span data-stu-id="7599f-109">Information</span></span>|  
|<span data-ttu-id="7599f-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="7599f-110">Channel</span></span>|<span data-ttu-id="7599f-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="7599f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7599f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7599f-112">Description</span></span>  
 <span data-ttu-id="7599f-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="7599f-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7599f-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="7599f-114">Message</span></span>  
 <span data-ttu-id="7599f-115">Der Verteiler hat 'BeforeCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7599f-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7599f-116">Details</span><span class="sxs-lookup"><span data-stu-id="7599f-116">Details</span></span>  
  
|<span data-ttu-id="7599f-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="7599f-117">Data Item Name</span></span>|<span data-ttu-id="7599f-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="7599f-118">Data Item Type</span></span>|<span data-ttu-id="7599f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7599f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7599f-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="7599f-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="7599f-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="7599f-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="7599f-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="7599f-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="7599f-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="7599f-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="7599f-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="7599f-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="7599f-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="7599f-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="7599f-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7599f-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="7599f-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7599f-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
