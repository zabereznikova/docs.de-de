---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121185"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="14549-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="14549-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="14549-102">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="14549-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="14549-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="14549-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="14549-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="14549-104">\<behaviors></span></span>  
<span data-ttu-id="14549-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="14549-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="14549-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="14549-106">\<behavior></span></span>  
<span data-ttu-id="14549-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="14549-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14549-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="14549-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14549-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14549-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14549-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14549-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14549-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="14549-111">Attributes</span></span>  
 <span data-ttu-id="14549-112">Keine</span><span class="sxs-lookup"><span data-stu-id="14549-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14549-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14549-113">Child Elements</span></span>  
  
|<span data-ttu-id="14549-114">Element</span><span class="sxs-lookup"><span data-stu-id="14549-114">Element</span></span>|<span data-ttu-id="14549-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14549-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14549-116">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="14549-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="14549-117">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="14549-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14549-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14549-118">Parent Elements</span></span>  
  
|<span data-ttu-id="14549-119">Element</span><span class="sxs-lookup"><span data-stu-id="14549-119">Element</span></span>|<span data-ttu-id="14549-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14549-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14549-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="14549-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="14549-122">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="14549-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14549-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14549-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
