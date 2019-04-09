---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 6fb31fca6ac38f6cb92ef087cc277a4d5066521c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182454"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="451f4-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="451f4-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="451f4-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt Bindung, die automatisch die [ \<WebHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="451f4-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="451f4-103">Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.</span><span class="sxs-lookup"><span data-stu-id="451f4-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="451f4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="451f4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="451f4-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="451f4-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451f4-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="451f4-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String"
                        defaultOutgoingResponseFormat="Xml/Json"
                        helpEnabled="Boolean"
                        webEndpointType="String" />
    </webHttpEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="451f4-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="451f4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="451f4-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="451f4-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="451f4-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="451f4-109">Attributes</span></span>  
  
|<span data-ttu-id="451f4-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="451f4-110">Attribute</span></span>|<span data-ttu-id="451f4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="451f4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="451f4-112">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="451f4-112">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="451f4-113">Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="451f4-113">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="451f4-114">Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="451f4-114">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="451f4-115">Wenn der `Accept`-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="451f4-115">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="451f4-116">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="451f4-116">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="451f4-117">Ein Attribut mit dem Standardformat für ausgehende Antworten.</span><span class="sxs-lookup"><span data-stu-id="451f4-117">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="451f4-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="451f4-118">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="451f4-119">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="451f4-119">helpEnabled</span></span>|<span data-ttu-id="451f4-120">Ein boolescher Wert, der angibt, ob die HTTP-Hilfeseite für den Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="451f4-120">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="451f4-121">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="451f4-121">webEndpointType</span></span>|<span data-ttu-id="451f4-122">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="451f4-122">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="451f4-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="451f4-123">Child Elements</span></span>  
 <span data-ttu-id="451f4-124">Keine</span><span class="sxs-lookup"><span data-stu-id="451f4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="451f4-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="451f4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="451f4-126">Element</span><span class="sxs-lookup"><span data-stu-id="451f4-126">Element</span></span>|<span data-ttu-id="451f4-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="451f4-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="451f4-128">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="451f4-128">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="451f4-129">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="451f4-129">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="451f4-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="451f4-130">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
