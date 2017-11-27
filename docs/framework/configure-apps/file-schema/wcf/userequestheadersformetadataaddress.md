---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c538939a97e43239048853b5d6c32251d557d7e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="12ff5-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="12ff5-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="12ff5-103">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="12ff5-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="12ff5-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="12ff5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="12ff5-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="12ff5-105">\<behaviors></span></span>  
<span data-ttu-id="12ff5-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="12ff5-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="12ff5-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="12ff5-107">\<behavior></span></span>  
<span data-ttu-id="12ff5-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="12ff5-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12ff5-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="12ff5-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="12ff5-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="12ff5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="12ff5-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="12ff5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="12ff5-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="12ff5-112">Attributes</span></span>  
 <span data-ttu-id="12ff5-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="12ff5-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="12ff5-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12ff5-114">Child Elements</span></span>  
  
|<span data-ttu-id="12ff5-115">Element</span><span class="sxs-lookup"><span data-stu-id="12ff5-115">Element</span></span>|<span data-ttu-id="12ff5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12ff5-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12ff5-117">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="12ff5-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="12ff5-118">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="12ff5-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="12ff5-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="12ff5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="12ff5-120">Element</span><span class="sxs-lookup"><span data-stu-id="12ff5-120">Element</span></span>|<span data-ttu-id="12ff5-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="12ff5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="12ff5-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="12ff5-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="12ff5-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="12ff5-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="12ff5-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12ff5-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
