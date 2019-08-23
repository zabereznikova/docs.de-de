---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925889"
---
# <a name="defaultports"></a><span data-ttu-id="86852-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="86852-101">\<defaultPorts></span></span>
<span data-ttu-id="86852-102">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="86852-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="86852-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="86852-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="86852-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="86852-104">\<behaviors></span></span>  
<span data-ttu-id="86852-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="86852-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="86852-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="86852-106">\<behavior></span></span>  
<span data-ttu-id="86852-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="86852-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="86852-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="86852-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86852-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="86852-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86852-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="86852-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86852-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="86852-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86852-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="86852-112">Attributes</span></span>  
 <span data-ttu-id="86852-113">Keine</span><span class="sxs-lookup"><span data-stu-id="86852-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="86852-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86852-114">Child Elements</span></span>  
  
|<span data-ttu-id="86852-115">Element</span><span class="sxs-lookup"><span data-stu-id="86852-115">Element</span></span>|<span data-ttu-id="86852-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86852-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86852-117">\<Fügen Sie > \<von defaultports hinzu ></span><span class="sxs-lookup"><span data-stu-id="86852-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="86852-118">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="86852-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="86852-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="86852-119">Parent Elements</span></span>  
  
|<span data-ttu-id="86852-120">Element</span><span class="sxs-lookup"><span data-stu-id="86852-120">Element</span></span>|<span data-ttu-id="86852-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86852-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86852-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="86852-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="86852-123">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="86852-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86852-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86852-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
