---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 7e661570f8b94b979595a615b3f6819d41ed5e35
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766698"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="6645f-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="6645f-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="6645f-103">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="6645f-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="6645f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6645f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6645f-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="6645f-105">\<behaviors></span></span>  
<span data-ttu-id="6645f-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6645f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6645f-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="6645f-107">\<behavior></span></span>  
<span data-ttu-id="6645f-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="6645f-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6645f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="6645f-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6645f-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6645f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6645f-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6645f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6645f-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="6645f-112">Attributes</span></span>  
 <span data-ttu-id="6645f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="6645f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6645f-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6645f-114">Child Elements</span></span>  
  
|<span data-ttu-id="6645f-115">Element</span><span class="sxs-lookup"><span data-stu-id="6645f-115">Element</span></span>|<span data-ttu-id="6645f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6645f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6645f-117">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="6645f-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="6645f-118">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="6645f-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6645f-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6645f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6645f-120">Element</span><span class="sxs-lookup"><span data-stu-id="6645f-120">Element</span></span>|<span data-ttu-id="6645f-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6645f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6645f-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6645f-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6645f-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="6645f-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6645f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6645f-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
