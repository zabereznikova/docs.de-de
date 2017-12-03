---
title: '&lt;webHttpEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee055be8c4d2e53dc22a101529e5521add9b54a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltwebhttpendpointgt"></a><span data-ttu-id="af63d-102">&lt;webHttpEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="af63d-102">&lt;webHttpEndpoint&gt;</span></span>
<span data-ttu-id="af63d-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt automatisch Bindung, die [ \<WebHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="af63d-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<webHttp>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) behavior.</span></span> <span data-ttu-id="af63d-104">Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.</span><span class="sxs-lookup"><span data-stu-id="af63d-104">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="af63d-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="af63d-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="af63d-106">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="af63d-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af63d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="af63d-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webHttpEndpoint>
      <standardEndpoint automaticFormatSelectionEnabled="String" 
                        defaultOutgoingResponseFormat="Xml/Json" 
                        helpEnabled="Boolean" 
                        webEndpointType="String"/>
    </webHttpEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af63d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af63d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="af63d-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af63d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af63d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="af63d-110">Attributes</span></span>  
  
|<span data-ttu-id="af63d-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="af63d-111">Attribute</span></span>|<span data-ttu-id="af63d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af63d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af63d-113">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="af63d-113">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="af63d-114">Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="af63d-114">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="af63d-115">Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="af63d-115">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="af63d-116">Wenn der `Accept`-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="af63d-116">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="af63d-117">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="af63d-117">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="af63d-118">Ein Attribut mit dem Standardformat für ausgehende Antworten.</span><span class="sxs-lookup"><span data-stu-id="af63d-118">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="af63d-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="af63d-119">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="af63d-120">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="af63d-120">helpEnabled</span></span>|<span data-ttu-id="af63d-121">Ein boolescher Wert, der angibt, ob die HTTP-Hilfeseite für den Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="af63d-121">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="af63d-122">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="af63d-122">webEndpointType</span></span>|<span data-ttu-id="af63d-123">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="af63d-123">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af63d-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af63d-124">Child Elements</span></span>  
 <span data-ttu-id="af63d-125">Keine</span><span class="sxs-lookup"><span data-stu-id="af63d-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af63d-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af63d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="af63d-127">Element</span><span class="sxs-lookup"><span data-stu-id="af63d-127">Element</span></span>|<span data-ttu-id="af63d-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af63d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af63d-129">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="af63d-129">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="af63d-130">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="af63d-130">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af63d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af63d-131">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>  
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
