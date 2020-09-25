---
title: <webHttpEndpoint>
ms.date: 03/30/2017
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
ms.openlocfilehash: 3282871bf8dbd25726ada7003d3066b9a42e2366
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177981"
---
# \<webHttpEndpoint>

<span data-ttu-id="6ac96-101">Dieses Konfigurationselement definiert einen Standard Endpunkt mit einer Fixed- [\<webHttpBinding>](webhttpbinding.md) Bindung, die das-Verhalten automatisch hinzufügt [\<webHttp>](webhttp.md) .</span><span class="sxs-lookup"><span data-stu-id="6ac96-101">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<webHttp>](webhttp.md) behavior.</span></span> <span data-ttu-id="6ac96-102">Verwenden Sie diesen Endpunkt, wenn Sie einen REST-Dienst schreiben.</span><span class="sxs-lookup"><span data-stu-id="6ac96-102">Use this endpoint when writing a REST service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webHttpEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="6ac96-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ac96-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ac96-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ac96-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6ac96-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ac96-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ac96-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ac96-106">Attributes</span></span>  
  
|<span data-ttu-id="6ac96-107">attribute</span><span class="sxs-lookup"><span data-stu-id="6ac96-107">Attribute</span></span>|<span data-ttu-id="6ac96-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ac96-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6ac96-109">automaticFormatSelectionEnabled</span><span class="sxs-lookup"><span data-stu-id="6ac96-109">automaticFormatSelectionEnabled</span></span>|<span data-ttu-id="6ac96-110">Ein boolescher Wert, der angibt, ob die automatische Formatauswahl aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6ac96-110">A Boolean value that indicates whether automatic format selection is enabled.</span></span><br /><br /> <span data-ttu-id="6ac96-111">Wenn die automatische Formatauswahl aktiviert ist, analysiert die Infrastruktur den `Accept`-Header der Anforderungsnachricht und bestimmt das geeignetste Antwortformat.</span><span class="sxs-lookup"><span data-stu-id="6ac96-111">When automatic format selection is enabled, the infrastructure parses the `Accept` header of the request message and determines the most appropriate response format.</span></span> <span data-ttu-id="6ac96-112">Wenn der `Accept`-Header kein geeignetes Antwortformat angibt, verwendet die Infrastruktur das `Content-Type`-Element der Anforderungsnachricht oder das Standardantwortformat des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="6ac96-112">If the `Accept` header does not specify a suitable response format, the infrastructure uses the `Content-Type` of the request message or the default response format of the operation.</span></span>|  
|<span data-ttu-id="6ac96-113">defaultOutgoingResponseFormat</span><span class="sxs-lookup"><span data-stu-id="6ac96-113">defaultOutgoingResponseFormat</span></span>|<span data-ttu-id="6ac96-114">Ein Attribut mit dem Standardformat für ausgehende Antworten.</span><span class="sxs-lookup"><span data-stu-id="6ac96-114">An attribute that specifies the default outgoing response format.</span></span> <span data-ttu-id="6ac96-115">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Web.WebMessageFormat>.</span><span class="sxs-lookup"><span data-stu-id="6ac96-115">This attribute is of the <xref:System.ServiceModel.Web.WebMessageFormat> type</span></span>|  
|<span data-ttu-id="6ac96-116">helpEnabled</span><span class="sxs-lookup"><span data-stu-id="6ac96-116">helpEnabled</span></span>|<span data-ttu-id="6ac96-117">Ein boolescher Wert, der angibt, ob die HTTP-Hilfeseite für den Endpunkt aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6ac96-117">A Boolean value that indicates whether the HTTP help page is enabled for the endpoint.</span></span>|  
|<span data-ttu-id="6ac96-118">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="6ac96-118">webEndpointType</span></span>|<span data-ttu-id="6ac96-119">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="6ac96-119">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ac96-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ac96-120">Child Elements</span></span>  

 <span data-ttu-id="6ac96-121">Keine</span><span class="sxs-lookup"><span data-stu-id="6ac96-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6ac96-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ac96-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6ac96-123">Element</span><span class="sxs-lookup"><span data-stu-id="6ac96-123">Element</span></span>|<span data-ttu-id="6ac96-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ac96-124">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6ac96-125">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6ac96-125">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6ac96-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ac96-126">See also</span></span>

- <xref:System.ServiceModel.Description.WebHttpEndpoint>
- <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>
