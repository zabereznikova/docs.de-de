---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130623"
---
# <a name="defaultports"></a><span data-ttu-id="f3217-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f3217-101">\<defaultPorts></span></span>
<span data-ttu-id="f3217-102">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="f3217-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="f3217-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f3217-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="f3217-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f3217-104">\<behaviors></span></span>  
<span data-ttu-id="f3217-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f3217-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="f3217-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f3217-106">\<behavior></span></span>  
<span data-ttu-id="f3217-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f3217-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="f3217-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="f3217-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3217-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3217-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3217-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f3217-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3217-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f3217-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3217-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="f3217-112">Attributes</span></span>  
 <span data-ttu-id="f3217-113">Keine</span><span class="sxs-lookup"><span data-stu-id="f3217-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f3217-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f3217-114">Child Elements</span></span>  
  
|<span data-ttu-id="f3217-115">Element</span><span class="sxs-lookup"><span data-stu-id="f3217-115">Element</span></span>|<span data-ttu-id="f3217-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3217-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3217-117">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="f3217-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="f3217-118">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="f3217-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f3217-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f3217-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f3217-120">Element</span><span class="sxs-lookup"><span data-stu-id="f3217-120">Element</span></span>|<span data-ttu-id="f3217-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f3217-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3217-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="f3217-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="f3217-123">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="f3217-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f3217-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3217-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
