---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399204"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="9b0d1-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="9b0d1-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="9b0d1-102">Ermöglicht das Abrufen von Metadatenadressinformationen aus Anforderungsnachrichtenheadern.</span><span class="sxs-lookup"><span data-stu-id="9b0d1-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="9b0d1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b0d1-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9b0d1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="9b0d1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="9b0d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="9b0d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useRequestHeadersForMetadataAddress >**</span><span class="sxs-lookup"><span data-stu-id="9b0d1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0d1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b0d1-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b0d1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9b0d1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9b0d1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9b0d1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b0d1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b0d1-112">Attributes</span></span>  
 <span data-ttu-id="9b0d1-113">Keine</span><span class="sxs-lookup"><span data-stu-id="9b0d1-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b0d1-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b0d1-114">Child Elements</span></span>  
  
|<span data-ttu-id="9b0d1-115">Element</span><span class="sxs-lookup"><span data-stu-id="9b0d1-115">Element</span></span>|<span data-ttu-id="9b0d1-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b0d1-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b0d1-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="9b0d1-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="9b0d1-118">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="9b0d1-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b0d1-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9b0d1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9b0d1-120">Element</span><span class="sxs-lookup"><span data-stu-id="9b0d1-120">Element</span></span>|<span data-ttu-id="9b0d1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b0d1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b0d1-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="9b0d1-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="9b0d1-123">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="9b0d1-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b0d1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b0d1-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
