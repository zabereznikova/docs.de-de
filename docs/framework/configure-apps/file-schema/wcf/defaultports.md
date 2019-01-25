---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2c742f98315c0e497ac4117953424bae913cb5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614496"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="7b8dd-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="7b8dd-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="7b8dd-103">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="7b8dd-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7b8dd-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7b8dd-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7b8dd-105">\<behaviors></span></span>  
<span data-ttu-id="7b8dd-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="7b8dd-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="7b8dd-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7b8dd-107">\<behavior></span></span>  
<span data-ttu-id="7b8dd-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="7b8dd-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="7b8dd-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="7b8dd-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8dd-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b8dd-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b8dd-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7b8dd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b8dd-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b8dd-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="7b8dd-113">Attributes</span></span>  
 <span data-ttu-id="7b8dd-114">Keine</span><span class="sxs-lookup"><span data-stu-id="7b8dd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b8dd-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b8dd-115">Child Elements</span></span>  
  
|<span data-ttu-id="7b8dd-116">Element</span><span class="sxs-lookup"><span data-stu-id="7b8dd-116">Element</span></span>|<span data-ttu-id="7b8dd-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b8dd-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b8dd-118">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="7b8dd-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="7b8dd-119">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b8dd-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7b8dd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7b8dd-121">Element</span><span class="sxs-lookup"><span data-stu-id="7b8dd-121">Element</span></span>|<span data-ttu-id="7b8dd-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b8dd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b8dd-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="7b8dd-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="7b8dd-124">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="7b8dd-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b8dd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b8dd-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
