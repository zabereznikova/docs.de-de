---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: 3d95624c82388ed6219fc567dd2d3c17bedad7a1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255288"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="8fbb2-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="8fbb2-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="8fbb2-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt Bindung, die automatisch die [ \<EnableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="8fbb2-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="8fbb2-103">Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8fbb2-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="8fbb2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8fbb2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8fbb2-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8fbb2-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fbb2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fbb2-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fbb2-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8fbb2-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8fbb2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fbb2-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="8fbb2-109">Attributes</span></span>  
  
|<span data-ttu-id="8fbb2-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="8fbb2-110">Attribute</span></span>|<span data-ttu-id="8fbb2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbb2-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8fbb2-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="8fbb2-112">webEndpointType</span></span>|<span data-ttu-id="8fbb2-113">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="8fbb2-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fbb2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb2-114">Child Elements</span></span>  
 <span data-ttu-id="8fbb2-115">Keine</span><span class="sxs-lookup"><span data-stu-id="8fbb2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fbb2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8fbb2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="8fbb2-117">Element</span><span class="sxs-lookup"><span data-stu-id="8fbb2-117">Element</span></span>|<span data-ttu-id="8fbb2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fbb2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fbb2-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8fbb2-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8fbb2-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8fbb2-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8fbb2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fbb2-121">See also</span></span>
- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
