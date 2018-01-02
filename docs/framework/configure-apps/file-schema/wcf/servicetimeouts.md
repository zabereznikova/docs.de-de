---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d8bfde535eb417614eee4ec6a2db7985152be33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="6d2e0-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="6d2e0-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="6d2e0-103">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="6d2e0-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="6d2e0-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6d2e0-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-105">\<behaviors></span></span>  
<span data-ttu-id="6d2e0-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6d2e0-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-107">\<behavior></span></span>  
<span data-ttu-id="6d2e0-108">\<ServiceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2e0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d2e0-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="6d2e0-110">Typ</span><span class="sxs-lookup"><span data-stu-id="6d2e0-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d2e0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6d2e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6d2e0-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d2e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d2e0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6d2e0-113">Attributes</span></span>  
  
|<span data-ttu-id="6d2e0-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6d2e0-114">Attribute</span></span>|<span data-ttu-id="6d2e0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d2e0-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="6d2e0-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="6d2e0-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="6d2e0-117">Die Standardeinstellung ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="6d2e0-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d2e0-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d2e0-118">Child Elements</span></span>  
 <span data-ttu-id="6d2e0-119">Keine</span><span class="sxs-lookup"><span data-stu-id="6d2e0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d2e0-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d2e0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6d2e0-121">Element</span><span class="sxs-lookup"><span data-stu-id="6d2e0-121">Element</span></span>|<span data-ttu-id="6d2e0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d2e0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d2e0-123">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6d2e0-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6d2e0-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="6d2e0-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6d2e0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d2e0-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
