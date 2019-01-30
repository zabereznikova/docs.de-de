---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 595970a56e05c4fc1c9b2c0eb669ec3b3a120fe1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262380"
---
# <a name="defaultports"></a><span data-ttu-id="dde99-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="dde99-101">\<defaultPorts></span></span>
<span data-ttu-id="dde99-102">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="dde99-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="dde99-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dde99-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dde99-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="dde99-104">\<behaviors></span></span>  
<span data-ttu-id="dde99-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="dde99-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="dde99-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="dde99-106">\<behavior></span></span>  
<span data-ttu-id="dde99-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="dde99-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="dde99-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="dde99-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde99-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="dde99-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dde99-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dde99-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dde99-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dde99-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dde99-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="dde99-112">Attributes</span></span>  
 <span data-ttu-id="dde99-113">Keine</span><span class="sxs-lookup"><span data-stu-id="dde99-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dde99-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dde99-114">Child Elements</span></span>  
  
|<span data-ttu-id="dde99-115">Element</span><span class="sxs-lookup"><span data-stu-id="dde99-115">Element</span></span>|<span data-ttu-id="dde99-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dde99-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde99-117">\<Hinzufügen > der \<DefaultPorts ></span><span class="sxs-lookup"><span data-stu-id="dde99-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="dde99-118">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="dde99-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dde99-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dde99-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dde99-120">Element</span><span class="sxs-lookup"><span data-stu-id="dde99-120">Element</span></span>|<span data-ttu-id="dde99-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dde99-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde99-122">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="dde99-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="dde99-123">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="dde99-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dde99-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dde99-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
