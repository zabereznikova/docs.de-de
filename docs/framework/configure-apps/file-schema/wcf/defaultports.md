---
title: '&lt;defaultPorts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd4fba4d7d5bcb0adc5a1a638598af2746ad4cf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="5cd95-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="5cd95-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="5cd95-103">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="5cd95-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="5cd95-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5cd95-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cd95-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5cd95-105">\<behaviors></span></span>  
<span data-ttu-id="5cd95-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5cd95-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5cd95-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="5cd95-107">\<behavior></span></span>  
<span data-ttu-id="5cd95-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="5cd95-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="5cd95-109">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5cd95-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd95-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cd95-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cd95-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5cd95-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5cd95-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5cd95-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cd95-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="5cd95-113">Attributes</span></span>  
 <span data-ttu-id="5cd95-114">Keine</span><span class="sxs-lookup"><span data-stu-id="5cd95-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5cd95-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cd95-115">Child Elements</span></span>  
  
|<span data-ttu-id="5cd95-116">Element</span><span class="sxs-lookup"><span data-stu-id="5cd95-116">Element</span></span>|<span data-ttu-id="5cd95-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cd95-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cd95-118">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5cd95-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="5cd95-119">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="5cd95-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5cd95-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5cd95-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5cd95-121">Element</span><span class="sxs-lookup"><span data-stu-id="5cd95-121">Element</span></span>|<span data-ttu-id="5cd95-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5cd95-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cd95-123">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="5cd95-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="5cd95-124">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="5cd95-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5cd95-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5cd95-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
