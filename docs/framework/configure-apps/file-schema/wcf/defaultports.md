---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130623"
---
# <a name="defaultports"></a><span data-ttu-id="20936-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="20936-101">\<defaultPorts></span></span>
<span data-ttu-id="20936-102">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="20936-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="20936-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="20936-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="20936-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="20936-104">\<behaviors></span></span>  
<span data-ttu-id="20936-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="20936-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="20936-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="20936-106">\<behavior></span></span>  
<span data-ttu-id="20936-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="20936-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="20936-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="20936-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20936-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="20936-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20936-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="20936-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20936-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20936-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20936-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="20936-112">Attributes</span></span>  
 <span data-ttu-id="20936-113">Keine</span><span class="sxs-lookup"><span data-stu-id="20936-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20936-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20936-114">Child Elements</span></span>  
  
|<span data-ttu-id="20936-115">Element</span><span class="sxs-lookup"><span data-stu-id="20936-115">Element</span></span>|<span data-ttu-id="20936-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20936-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20936-117">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="20936-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="20936-118">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="20936-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20936-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20936-119">Parent Elements</span></span>  
  
|<span data-ttu-id="20936-120">Element</span><span class="sxs-lookup"><span data-stu-id="20936-120">Element</span></span>|<span data-ttu-id="20936-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20936-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20936-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="20936-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="20936-123">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="20936-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20936-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20936-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
