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
ms.openlocfilehash: f6d2940a4c4615a922efcc74802a82adbe10267c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="772c7-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="772c7-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="772c7-103">Gibt den Timeout für einen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="772c7-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="772c7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="772c7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="772c7-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="772c7-105">\<behaviors></span></span>  
<span data-ttu-id="772c7-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="772c7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="772c7-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="772c7-107">\<behavior></span></span>  
<span data-ttu-id="772c7-108">\<ServiceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="772c7-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772c7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="772c7-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="772c7-110">Typ</span><span class="sxs-lookup"><span data-stu-id="772c7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="772c7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="772c7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="772c7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="772c7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="772c7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="772c7-113">Attributes</span></span>  
  
|<span data-ttu-id="772c7-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="772c7-114">Attribute</span></span>|<span data-ttu-id="772c7-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="772c7-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="772c7-116">Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall angibt, in dem eine Transaktion vom Client an den Server weitergegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="772c7-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="772c7-117">Die Standardeinstellung ist "00: 00:00".</span><span class="sxs-lookup"><span data-stu-id="772c7-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="772c7-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="772c7-118">Child Elements</span></span>  
 <span data-ttu-id="772c7-119">Keine</span><span class="sxs-lookup"><span data-stu-id="772c7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="772c7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="772c7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="772c7-121">Element</span><span class="sxs-lookup"><span data-stu-id="772c7-121">Element</span></span>|<span data-ttu-id="772c7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="772c7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="772c7-123">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="772c7-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="772c7-124">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="772c7-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="772c7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="772c7-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
