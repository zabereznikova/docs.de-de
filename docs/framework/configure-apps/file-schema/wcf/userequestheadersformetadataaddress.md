---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 6c03057fca23b037702c702b9a574045ebb302b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656626"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="8b24b-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="8b24b-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="8b24b-103">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="8b24b-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="8b24b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8b24b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8b24b-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8b24b-105">\<behaviors></span></span>  
<span data-ttu-id="8b24b-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8b24b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="8b24b-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8b24b-107">\<behavior></span></span>  
<span data-ttu-id="8b24b-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="8b24b-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b24b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b24b-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b24b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8b24b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8b24b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b24b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b24b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8b24b-112">Attributes</span></span>  
 <span data-ttu-id="8b24b-113">Keine</span><span class="sxs-lookup"><span data-stu-id="8b24b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8b24b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b24b-114">Child Elements</span></span>  
  
|<span data-ttu-id="8b24b-115">Element</span><span class="sxs-lookup"><span data-stu-id="8b24b-115">Element</span></span>|<span data-ttu-id="8b24b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b24b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b24b-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="8b24b-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="8b24b-118">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="8b24b-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b24b-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8b24b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8b24b-120">Element</span><span class="sxs-lookup"><span data-stu-id="8b24b-120">Element</span></span>|<span data-ttu-id="8b24b-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8b24b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b24b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8b24b-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="8b24b-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="8b24b-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b24b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b24b-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
