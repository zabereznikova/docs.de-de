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
ms.openlocfilehash: 64dcdb3a928d2ec05cd7dac557b6db10cb4a6511
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="aa6f2-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="aa6f2-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="aa6f2-103">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa6f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa6f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="aa6f2-104">ID</span></span>|<span data-ttu-id="aa6f2-105">212</span><span class="sxs-lookup"><span data-stu-id="aa6f2-105">212</span></span>|  
|<span data-ttu-id="aa6f2-106">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="aa6f2-106">Keywords</span></span>|<span data-ttu-id="aa6f2-107">Troubleshooting, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="aa6f2-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="aa6f2-108">Ebene</span><span class="sxs-lookup"><span data-stu-id="aa6f2-108">Level</span></span>|<span data-ttu-id="aa6f2-109">Information</span><span class="sxs-lookup"><span data-stu-id="aa6f2-109">Information</span></span>|  
|<span data-ttu-id="aa6f2-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="aa6f2-110">Channel</span></span>|<span data-ttu-id="aa6f2-111">Microsoft-Windows-Application Server-Applications/Analytic</span><span class="sxs-lookup"><span data-stu-id="aa6f2-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="aa6f2-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa6f2-112">Description</span></span>  
 <span data-ttu-id="aa6f2-113">Dieses Ereignis wird ausgegeben, nachdem das Dienstmodell die `BeforeCall`-Methode auf einem `ParameterInspector` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="aa6f2-114">Meldung</span><span class="sxs-lookup"><span data-stu-id="aa6f2-114">Message</span></span>  
 <span data-ttu-id="aa6f2-115">Der Verteiler hat 'BeforeCall' auf einem ParameterInspector vom Typ '%1' aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="aa6f2-116">Details</span><span class="sxs-lookup"><span data-stu-id="aa6f2-116">Details</span></span>  
  
|<span data-ttu-id="aa6f2-117">Datenelementname</span><span class="sxs-lookup"><span data-stu-id="aa6f2-117">Data Item Name</span></span>|<span data-ttu-id="aa6f2-118">Datenelementtyp</span><span class="sxs-lookup"><span data-stu-id="aa6f2-118">Data Item Type</span></span>|<span data-ttu-id="aa6f2-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa6f2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="aa6f2-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="aa6f2-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="aa6f2-121">Der CLR-FullName für den Typ des aufgerufenen Inspektors.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="aa6f2-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="aa6f2-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="aa6f2-123">Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="aa6f2-124">Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ".</span><span class="sxs-lookup"><span data-stu-id="aa6f2-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="aa6f2-125">Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="aa6f2-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="aa6f2-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="aa6f2-127">Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aa6f2-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
