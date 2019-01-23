---
title: '&lt;add&gt; von &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 8b7a4730af6690616058a91cf23bb39734d81abc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54541715"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="46c98-102">&lt;add&gt; von &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="46c98-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="46c98-103">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="46c98-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="46c98-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="46c98-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="46c98-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="46c98-105">\<behaviors></span></span>  
<span data-ttu-id="46c98-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="46c98-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="46c98-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="46c98-107">\<behavior></span></span>  
<span data-ttu-id="46c98-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="46c98-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="46c98-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="46c98-109">\<defaultPorts></span></span>  
<span data-ttu-id="46c98-110">\<add></span><span class="sxs-lookup"><span data-stu-id="46c98-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46c98-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="46c98-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46c98-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="46c98-112">Attributes and Elements</span></span>  
 <span data-ttu-id="46c98-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="46c98-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46c98-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="46c98-114">Attributes</span></span>  
  
|<span data-ttu-id="46c98-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="46c98-115">Attribute</span></span>|<span data-ttu-id="46c98-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46c98-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46c98-117">Port</span><span class="sxs-lookup"><span data-stu-id="46c98-117">port</span></span>|<span data-ttu-id="46c98-118">Eine ganze Zahl, die die Nummer des Standardkommunikationsports angibt.</span><span class="sxs-lookup"><span data-stu-id="46c98-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="46c98-119">scheme</span><span class="sxs-lookup"><span data-stu-id="46c98-119">scheme</span></span>|<span data-ttu-id="46c98-120">Eine Zeichenfolge, die die Gruppe von Protokolleinstellungen angibt, die einem Kommunikationsport zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="46c98-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="46c98-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46c98-121">Child Elements</span></span>  
 <span data-ttu-id="46c98-122">Keine</span><span class="sxs-lookup"><span data-stu-id="46c98-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="46c98-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="46c98-123">Parent Elements</span></span>  
  
|<span data-ttu-id="46c98-124">Element</span><span class="sxs-lookup"><span data-stu-id="46c98-124">Element</span></span>|<span data-ttu-id="46c98-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="46c98-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46c98-126">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="46c98-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="46c98-127">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="46c98-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46c98-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46c98-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.DefaultPortElement>
