---
title: '&lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 7ddfddaa13778ce98bd93b6d8029438377fc7e94
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145184"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="9fcf7-102">&lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="9fcf7-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="9fcf7-103">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="9fcf7-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="9fcf7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9fcf7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9fcf7-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="9fcf7-105">\<behaviors></span></span>  
<span data-ttu-id="9fcf7-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9fcf7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9fcf7-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="9fcf7-107">\<behavior></span></span>  
<span data-ttu-id="9fcf7-108">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="9fcf7-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="9fcf7-109">\<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="9fcf7-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcf7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fcf7-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fcf7-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcf7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9fcf7-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9fcf7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fcf7-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="9fcf7-113">Attributes</span></span>  
 <span data-ttu-id="9fcf7-114">Keine</span><span class="sxs-lookup"><span data-stu-id="9fcf7-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9fcf7-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcf7-115">Child Elements</span></span>  
  
|<span data-ttu-id="9fcf7-116">Element</span><span class="sxs-lookup"><span data-stu-id="9fcf7-116">Element</span></span>|<span data-ttu-id="9fcf7-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fcf7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fcf7-118">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="9fcf7-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="9fcf7-119">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="9fcf7-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fcf7-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9fcf7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9fcf7-121">Element</span><span class="sxs-lookup"><span data-stu-id="9fcf7-121">Element</span></span>|<span data-ttu-id="9fcf7-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9fcf7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fcf7-123">\<UseRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="9fcf7-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="9fcf7-124">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="9fcf7-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fcf7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fcf7-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
