---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398073"
---
# <a name="defaultports"></a><span data-ttu-id="3040d-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="3040d-101">\<defaultPorts></span></span>
<span data-ttu-id="3040d-102">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="3040d-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="3040d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3040d-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3040d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3040d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceverhaltens>** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3040d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3040d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="3040d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="3040d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultports >**</span><span class="sxs-lookup"><span data-stu-id="3040d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3040d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="3040d-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3040d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3040d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3040d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3040d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3040d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="3040d-113">Attributes</span></span>  
 <span data-ttu-id="3040d-114">Keine</span><span class="sxs-lookup"><span data-stu-id="3040d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3040d-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3040d-115">Child Elements</span></span>  
  
|<span data-ttu-id="3040d-116">Element</span><span class="sxs-lookup"><span data-stu-id="3040d-116">Element</span></span>|<span data-ttu-id="3040d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3040d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3040d-118">\<Fügen Sie > \<von defaultports hinzu ></span><span class="sxs-lookup"><span data-stu-id="3040d-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="3040d-119">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="3040d-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3040d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3040d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3040d-121">Element</span><span class="sxs-lookup"><span data-stu-id="3040d-121">Element</span></span>|<span data-ttu-id="3040d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3040d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3040d-123">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="3040d-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="3040d-124">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="3040d-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3040d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3040d-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
