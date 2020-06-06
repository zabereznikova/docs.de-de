---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 8d4f55fd5b51ea77839b7fdbb930e937f5700417
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854800"
---
# \<webHttpEndpoint>
<span data-ttu-id="637f3-101">Dieses Konfigurationselement definiert einen Standard Endpunkt mit einer Fixed- [\<webHttpBinding>](webhttpbinding.md) Bindung, die das-Verhalten automatisch hinzufügt [\<webHttp>](webhttp.md) .</span><span class="sxs-lookup"><span data-stu-id="637f3-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="637f3-102">Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.</span><span class="sxs-lookup"><span data-stu-id="637f3-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="637f3-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="637f3-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="637f3-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="637f3-104">Attributes and Elements</span></span>  
 <span data-ttu-id="637f3-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="637f3-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="637f3-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="637f3-106">Attributes</span></span>  
  
|<span data-ttu-id="637f3-107">attribute</span><span class="sxs-lookup"><span data-stu-id="637f3-107">Attribute</span></span>|<span data-ttu-id="637f3-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="637f3-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="637f3-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="637f3-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="637f3-110">Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="637f3-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="637f3-111">Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="637f3-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="637f3-112">Wenn der `Accept`-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="637f3-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="637f3-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="637f3-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="637f3-114">Ein Attribut mit dem Standardformat für ausgehende Antworten.</span><span class="sxs-lookup"><span data-stu-id="637f3-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="637f3-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="637f3-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="637f3-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="637f3-116">helpEnabled</span></span>|<span data-ttu-id="637f3-117">Ein boolescher Wert, der angibt, ob die HTTP-Hilfeseite für den Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="637f3-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="637f3-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="637f3-118">webEndpointType</span></span>|<span data-ttu-id="637f3-119">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="637f3-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="637f3-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="637f3-120">Child Elements</span></span>  
 <span data-ttu-id="637f3-121">Keine</span><span class="sxs-lookup"><span data-stu-id="637f3-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="637f3-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="637f3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="637f3-123">Element</span><span class="sxs-lookup"><span data-stu-id="637f3-123">Element</span></span>|<span data-ttu-id="637f3-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="637f3-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="637f3-125">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="637f3-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="637f3-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="637f3-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
