---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 84310d4ae5e04e76e4484f4fc606c9896239c776
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940552"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="74ce9-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="74ce9-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="74ce9-102">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="74ce9-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="74ce9-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="74ce9-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="74ce9-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="74ce9-104">\<behaviors></span></span>  
<span data-ttu-id="74ce9-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="74ce9-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="74ce9-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="74ce9-106">\<behavior></span></span>  
<span data-ttu-id="74ce9-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="74ce9-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ce9-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="74ce9-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74ce9-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="74ce9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="74ce9-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74ce9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74ce9-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="74ce9-111">Attributes</span></span>  
 <span data-ttu-id="74ce9-112">Keine</span><span class="sxs-lookup"><span data-stu-id="74ce9-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="74ce9-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74ce9-113">Child Elements</span></span>  
  
|<span data-ttu-id="74ce9-114">Element</span><span class="sxs-lookup"><span data-stu-id="74ce9-114">Element</span></span>|<span data-ttu-id="74ce9-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74ce9-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74ce9-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="74ce9-116">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="74ce9-117">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="74ce9-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="74ce9-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="74ce9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="74ce9-119">Element</span><span class="sxs-lookup"><span data-stu-id="74ce9-119">Element</span></span>|<span data-ttu-id="74ce9-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74ce9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74ce9-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="74ce9-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="74ce9-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="74ce9-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74ce9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74ce9-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
