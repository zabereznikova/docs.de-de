---
title: '&lt;webScriptEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: b53b7cc3ce812b72830c0ad83c5cc2b42bfc25a7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755304"
---
# <a name="ltwebscriptendpointgt"></a><span data-ttu-id="6328f-102">&lt;webScriptEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="6328f-102">&lt;webScriptEndpoint&gt;</span></span>
<span data-ttu-id="6328f-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einer festen [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) fügt automatisch Bindung, die [ \<EnableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) Verhalten.</span><span class="sxs-lookup"><span data-stu-id="6328f-103">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior.</span></span> <span data-ttu-id="6328f-104">Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6328f-104">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="6328f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6328f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6328f-106">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6328f-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6328f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="6328f-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String"/>
    </webScriptEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6328f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6328f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6328f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6328f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6328f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6328f-110">Attributes</span></span>  
  
|<span data-ttu-id="6328f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="6328f-111">Attribute</span></span>|<span data-ttu-id="6328f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6328f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6328f-113">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="6328f-113">webEndpointType</span></span>|<span data-ttu-id="6328f-114">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="6328f-114">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6328f-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6328f-115">Child Elements</span></span>  
 <span data-ttu-id="6328f-116">Keine</span><span class="sxs-lookup"><span data-stu-id="6328f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6328f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6328f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6328f-118">Element</span><span class="sxs-lookup"><span data-stu-id="6328f-118">Element</span></span>|<span data-ttu-id="6328f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6328f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6328f-120">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="6328f-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="6328f-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6328f-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6328f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6328f-122">See Also</span></span>  
 <xref:System.ServiceModel.Description.WebScriptEndpoint>  
 <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
