---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398073"
---
# \<defaultPorts>
<span data-ttu-id="4fea8-101">Eine Auflistung von Standardports mit den Standardkommunikationsendpunkten, die von der Clientanwendung überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="4fea8-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="4fea8-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fea8-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fea8-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4fea8-103">Attributes and Elements</span></span>  
 <span data-ttu-id="4fea8-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4fea8-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fea8-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="4fea8-105">Attributes</span></span>  
 <span data-ttu-id="4fea8-106">Keine</span><span class="sxs-lookup"><span data-stu-id="4fea8-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4fea8-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fea8-107">Child Elements</span></span>  
  
|<span data-ttu-id="4fea8-108">Element</span><span class="sxs-lookup"><span data-stu-id="4fea8-108">Element</span></span>|<span data-ttu-id="4fea8-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4fea8-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fea8-110">\<add>Natürlich\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="4fea8-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="4fea8-111">Ein Standardkommunikationsendpunkt, den die Clientanwendung überwacht.</span><span class="sxs-lookup"><span data-stu-id="4fea8-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fea8-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4fea8-112">Parent Elements</span></span>  
  
|<span data-ttu-id="4fea8-113">Element</span><span class="sxs-lookup"><span data-stu-id="4fea8-113">Element</span></span>|<span data-ttu-id="4fea8-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4fea8-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="4fea8-115">Eine Liste von Standardports.</span><span class="sxs-lookup"><span data-stu-id="4fea8-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4fea8-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fea8-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
