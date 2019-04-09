---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: b2cdd29cda7f82ce555b0f6c1a963567b41ff81b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212998"
---
# <a name="enablewebscript"></a><span data-ttu-id="38f71-101">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="38f71-101">\<enableWebScript></span></span>
<span data-ttu-id="38f71-102">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="38f71-102">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="38f71-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="38f71-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="38f71-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="38f71-104">\<behaviors></span></span>  
<span data-ttu-id="38f71-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="38f71-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="38f71-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="38f71-106">\<behavior></span></span>  
<span data-ttu-id="38f71-107">\<enableWebScript></span><span class="sxs-lookup"><span data-stu-id="38f71-107">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38f71-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="38f71-108">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38f71-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38f71-109">Attributes and Elements</span></span>  
 <span data-ttu-id="38f71-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38f71-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38f71-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="38f71-111">Attributes</span></span>  
 <span data-ttu-id="38f71-112">Keine</span><span class="sxs-lookup"><span data-stu-id="38f71-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="38f71-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38f71-113">Child Elements</span></span>  
 <span data-ttu-id="38f71-114">Keine</span><span class="sxs-lookup"><span data-stu-id="38f71-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38f71-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38f71-115">Parent Elements</span></span>  
  
|<span data-ttu-id="38f71-116">Element</span><span class="sxs-lookup"><span data-stu-id="38f71-116">Element</span></span>|<span data-ttu-id="38f71-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38f71-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38f71-118">\<behavior></span><span class="sxs-lookup"><span data-stu-id="38f71-118">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="38f71-119">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="38f71-119">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38f71-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38f71-120">Remarks</span></span>  
 <span data-ttu-id="38f71-121">Dieses Verhalten sollte nur verwendet werden, in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung oder dem [ \<WebMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) Binding-Element.</span><span class="sxs-lookup"><span data-stu-id="38f71-121">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="38f71-122">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="38f71-122">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f71-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38f71-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="38f71-124">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="38f71-124">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="38f71-125">\<webHttp></span><span class="sxs-lookup"><span data-stu-id="38f71-125">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
