---
title: '&lt;enableWebScript&gt;'
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 34100ce17e67e12574ec0cdd677991949d0b9214
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150798"
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="7d945-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="7d945-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="7d945-103">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d945-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="7d945-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7d945-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7d945-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="7d945-105">\<behaviors></span></span>  
<span data-ttu-id="7d945-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="7d945-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="7d945-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="7d945-107">\<behavior></span></span>  
<span data-ttu-id="7d945-108">\<EnableWebScript ></span><span class="sxs-lookup"><span data-stu-id="7d945-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d945-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="7d945-109">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d945-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7d945-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d945-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d945-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d945-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7d945-112">Attributes</span></span>  
 <span data-ttu-id="7d945-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7d945-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d945-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d945-114">Child Elements</span></span>  
 <span data-ttu-id="7d945-115">Keine</span><span class="sxs-lookup"><span data-stu-id="7d945-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d945-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7d945-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7d945-117">Element</span><span class="sxs-lookup"><span data-stu-id="7d945-117">Element</span></span>|<span data-ttu-id="7d945-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d945-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d945-119">\<behavior></span><span class="sxs-lookup"><span data-stu-id="7d945-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="7d945-120">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="7d945-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d945-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7d945-121">Remarks</span></span>  
 <span data-ttu-id="7d945-122">Dieses Verhalten sollte nur verwendet werden, in Verbindung mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung oder dem [ \<WebMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) Binding-Element.</span><span class="sxs-lookup"><span data-stu-id="7d945-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="7d945-123">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="7d945-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d945-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d945-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="7d945-125">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="7d945-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="7d945-126">\<WebHttp ></span><span class="sxs-lookup"><span data-stu-id="7d945-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
