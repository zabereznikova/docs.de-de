---
title: <webScriptEndpoint>
ms.date: 03/30/2017
ms.assetid: 85cb5ecf-351b-45f3-aa29-aa2e4b64bcdd
ms.openlocfilehash: cc69029d9830fd12df5a4070f11847fadf4c60bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940410"
---
# <a name="webscriptendpoint"></a><span data-ttu-id="fa01b-101">\<webScriptEndpoint></span><span class="sxs-lookup"><span data-stu-id="fa01b-101">\<webScriptEndpoint></span></span>
<span data-ttu-id="fa01b-102">Dieses Konfigurationselement definiert einen Standard Endpunkt mit einem fixierten [ \<WebHttpBinding->](webhttpbinding.md) Bindung, der automatisch das [ \<> Verhalten von enableWebScript](enablewebscript.md) hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="fa01b-102">This configuration element defines a standard endpoint with a fixed [\<webHttpBinding>](webhttpbinding.md) binding that automatically adds the [\<enableWebScript>](enablewebscript.md) behavior.</span></span> <span data-ttu-id="fa01b-103">Verwenden Sie diesen Endpunkt, wenn Sie einen Dienst schreiben, der von einer ASP.NET AJAX-Anwendung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fa01b-103">Use this endpoint when you are writing a service that is called from an ASP.NET AJAX application.</span></span>  
  
<span data-ttu-id="fa01b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fa01b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fa01b-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fa01b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa01b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa01b-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint webEndpointType="String" />
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa01b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa01b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fa01b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa01b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa01b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa01b-109">Attributes</span></span>  
  
|<span data-ttu-id="fa01b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa01b-110">Attribute</span></span>|<span data-ttu-id="fa01b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa01b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa01b-112">webEndpointType</span><span class="sxs-lookup"><span data-stu-id="fa01b-112">webEndpointType</span></span>|<span data-ttu-id="fa01b-113">Eine Zeichenfolge, die den Typ des Endpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="fa01b-113">A string that specifies the type of the endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa01b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa01b-114">Child Elements</span></span>  
 <span data-ttu-id="fa01b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="fa01b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa01b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa01b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fa01b-117">Element</span><span class="sxs-lookup"><span data-stu-id="fa01b-117">Element</span></span>|<span data-ttu-id="fa01b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa01b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa01b-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="fa01b-119">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="fa01b-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="fa01b-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa01b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa01b-121">See also</span></span>

- <xref:System.ServiceModel.Description.WebScriptEndpoint>
- <xref:System.ServiceModel.Configuration.WebScriptEndpointElement>
