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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e7f69da871376f83422fb330f8babd56bb1fdcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="c3131-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="c3131-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="c3131-103">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="c3131-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="c3131-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c3131-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c3131-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c3131-105">\<behaviors></span></span>  
<span data-ttu-id="c3131-106">\<ServiceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c3131-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c3131-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c3131-107">\<behavior></span></span>  
<span data-ttu-id="c3131-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="c3131-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3131-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3131-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3131-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c3131-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3131-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c3131-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3131-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="c3131-112">Attributes</span></span>  
 <span data-ttu-id="c3131-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="c3131-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c3131-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3131-114">Child Elements</span></span>  
  
|<span data-ttu-id="c3131-115">Element</span><span class="sxs-lookup"><span data-stu-id="c3131-115">Element</span></span>|<span data-ttu-id="c3131-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3131-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3131-117">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="c3131-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="c3131-118">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="c3131-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c3131-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c3131-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c3131-120">Element</span><span class="sxs-lookup"><span data-stu-id="c3131-120">Element</span></span>|<span data-ttu-id="c3131-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c3131-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3131-122">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="c3131-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c3131-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="c3131-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3131-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3131-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
