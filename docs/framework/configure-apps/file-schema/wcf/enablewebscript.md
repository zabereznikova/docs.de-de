---
title: '&lt;enableWebScript&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7e637a744d24ed32be71d0ecf3f5d93144d32aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltenablewebscriptgt"></a><span data-ttu-id="a5d0b-102">&lt;enableWebScript&gt;</span><span class="sxs-lookup"><span data-stu-id="a5d0b-102">&lt;enableWebScript&gt;</span></span>
<span data-ttu-id="a5d0b-103">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a5d0b-103">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
 <span data-ttu-id="a5d0b-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a5d0b-105">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-105">\<behaviors></span></span>  
<span data-ttu-id="a5d0b-106">\<EndpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a5d0b-107">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-107">\<behavior></span></span>  
<span data-ttu-id="a5d0b-108">\<EnableWebScript ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-108">\<enableWebScript></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d0b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5d0b-109">Syntax</span></span>  
  
```xml  
<enableWebScript />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5d0b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5d0b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5d0b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5d0b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5d0b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5d0b-112">Attributes</span></span>  
 <span data-ttu-id="a5d0b-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a5d0b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5d0b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5d0b-114">Child Elements</span></span>  
 <span data-ttu-id="a5d0b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="a5d0b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5d0b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5d0b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a5d0b-117">Element</span><span class="sxs-lookup"><span data-stu-id="a5d0b-117">Element</span></span>|<span data-ttu-id="a5d0b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5d0b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5d0b-119">\<Verhalten ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-119">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a5d0b-120">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="a5d0b-120">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5d0b-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5d0b-121">Remarks</span></span>  
 <span data-ttu-id="a5d0b-122">Dieses Verhalten sollte nur verwendet werden, zusammen mit der [ \<WebHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) -standardbindung oder [ \<WebMessageEncoding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) Binding-Element.</span><span class="sxs-lookup"><span data-stu-id="a5d0b-122">This behavior should only be used in conjunction with either the [\<webHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](../../../../../docs/framework/configure-apps/file-schema/wcf/webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="a5d0b-123">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="a5d0b-123">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d0b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5d0b-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>  
 <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>  
 [<span data-ttu-id="a5d0b-125">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="a5d0b-125">AJAX Integration and JSON Support</span></span>](../../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)  
 [<span data-ttu-id="a5d0b-126">\<WebHttp ></span><span class="sxs-lookup"><span data-stu-id="a5d0b-126">\<webHttp></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)
