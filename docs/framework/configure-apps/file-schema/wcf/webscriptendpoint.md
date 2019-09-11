---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b4bc33cf8ff4e703973efe7df49e9f1d2189302e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854814"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="14206-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="14206-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="14206-102">Dieses Konfigurationselement definiert einen Standard Endpunkt mit einem fixierten [ \<WebHttpBinding->](webhttpbinding.md) Bindung, der automatisch das [ \<> Verhalten von enableWebScript](enablewebscript.md) hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="14206-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="14206-103">Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="14206-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="14206-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="14206-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="14206-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="14206-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="14206-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="14206-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="14206-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<WebScriptEndpoint->**</span><span class="sxs-lookup"><span data-stu-id="14206-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webScriptEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14206-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="14206-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14206-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14206-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14206-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14206-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14206-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="14206-111">Attributes</span></span>  
  
|<span data-ttu-id="14206-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="14206-112">Attribute</span></span>|<span data-ttu-id="14206-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14206-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14206-114">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="14206-114">webEndpointType</span></span>|<span data-ttu-id="14206-115">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="14206-115">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14206-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14206-116">Child Elements</span></span>  
 <span data-ttu-id="14206-117">Keine</span><span class="sxs-lookup"><span data-stu-id="14206-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14206-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14206-118">Parent Elements</span></span>  
  
|<span data-ttu-id="14206-119">Element</span><span class="sxs-lookup"><span data-stu-id="14206-119">Element</span></span>|<span data-ttu-id="14206-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14206-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14206-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="14206-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="14206-122">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="14206-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14206-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14206-123">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
