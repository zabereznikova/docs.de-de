---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854800"
---
# <a name="webhttpendpoint"></a><span data-ttu-id="8fbb4-101">\<webHttpEndpoint></span><span class="sxs-lookup"><span data-stu-id="8fbb4-101">\<webHttpEndpoint></span></span>
<span data-ttu-id="8fbb4-102">Dieses Konfigurationselement definiert einen Standard Endpunkt mit einem fixierten [ \<WebHttpBinding->](webhttpbinding.md) Bindung, die das [ \<webHttp->](webhttp.md) Verhalten automatisch hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="8fbb4-103">Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-103">Use this endpoint when writing a REST service.</span></span>  
  
<span data-ttu-id="8fbb4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fbb4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fbb4-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8fbb4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8fbb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8fbb4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8fbb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<webhttpdpoint->**</span><span class="sxs-lookup"><span data-stu-id="8fbb4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fbb4-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fbb4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fbb4-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8fbb4-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fbb4-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fbb4-111">Attributes</span></span>  
  
|<span data-ttu-id="8fbb4-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="8fbb4-112">Attribute</span></span>|<span data-ttu-id="8fbb4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbb4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fbb4-114">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="8fbb4-114">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="8fbb4-115">Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-115">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="8fbb4-116">Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-116">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="8fbb4-117">Wenn der `Accept`-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-117">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="8fbb4-118">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="8fbb4-118">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="8fbb4-119">Ein Attribut mit dem Standardformat für ausgehende Antworten.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-119">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="8fbb4-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-120">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="8fbb4-121">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="8fbb4-121">helpEnabled</span></span>|<span data-ttu-id="8fbb4-122">Ein boolescher Wert, der angibt, ob die HTTP-Hilfeseite für den Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-122">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="8fbb4-123">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8fbb4-123">webEndpointType</span></span>|<span data-ttu-id="8fbb4-124">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-124">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fbb4-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb4-125">Child Elements</span></span>  
 <span data-ttu-id="8fbb4-126">Keine</span><span class="sxs-lookup"><span data-stu-id="8fbb4-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fbb4-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb4-127">Parent Elements</span></span>  
  
|<span data-ttu-id="8fbb4-128">Element</span><span class="sxs-lookup"><span data-stu-id="8fbb4-128">Element</span></span>|<span data-ttu-id="8fbb4-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbb4-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fbb4-130">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8fbb4-130">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8fbb4-131">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8fbb4-131">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fbb4-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fbb4-132">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
