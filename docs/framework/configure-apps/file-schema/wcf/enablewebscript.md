---
title: <enableWebScript>
ms.date: 03/30/2017
ms.assetid: 9c7e96e1-af70-4e6e-ac5c-d67929dddbaa
ms.openlocfilehash: 11378e6cc8cbe8e631fd77ab74c91a616099df52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190084"
---
# \<enableWebScript>

<span data-ttu-id="5b2c7-101">Dieses Element aktiviert das Endpunktverhalten, durch das der Dienst über ASP.NET AJAX-Webseiten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-101">This element enables the endpoint behavior that makes it possible to consume the service from ASP.NET AJAX web pages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<enableWebScript>**  
  
## <a name="syntax"></a><span data-ttu-id="5b2c7-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b2c7-102">Syntax</span></span>  
  
```xml  
<enableWebScript />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b2c7-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5b2c7-103">Attributes and Elements</span></span>  

 <span data-ttu-id="5b2c7-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b2c7-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="5b2c7-105">Attributes</span></span>  

 <span data-ttu-id="5b2c7-106">Keine</span><span class="sxs-lookup"><span data-stu-id="5b2c7-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b2c7-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b2c7-107">Child Elements</span></span>  

 <span data-ttu-id="5b2c7-108">Keine</span><span class="sxs-lookup"><span data-stu-id="5b2c7-108">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b2c7-109">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b2c7-109">Parent Elements</span></span>  
  
|<span data-ttu-id="5b2c7-110">Element</span><span class="sxs-lookup"><span data-stu-id="5b2c7-110">Element</span></span>|<span data-ttu-id="5b2c7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b2c7-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="5b2c7-112">Gibt den Satz an Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-112">Specifies the set of endpoint behaviors.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b2c7-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5b2c7-113">Remarks</span></span>  

 <span data-ttu-id="5b2c7-114">Dieses Verhalten sollte nur in Verbindung mit der [\<webHttpBinding>](webhttpbinding.md) Standard Bindung oder dem Bindungs Element verwendet werden [\<webMessageEncoding>](webmessageencoding.md) .</span><span class="sxs-lookup"><span data-stu-id="5b2c7-114">This behavior should only be used in conjunction with either the [\<webHttpBinding>](webhttpbinding.md) standard binding, or the [\<webMessageEncoding>](webmessageencoding.md) binding element.</span></span>  <span data-ttu-id="5b2c7-115">Weitere Informationen zu diesem Verhalten finden Sie unter <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span><span class="sxs-lookup"><span data-stu-id="5b2c7-115">For more information on this behavior, see <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b2c7-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b2c7-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebScriptEnablingElement>
- <xref:System.ServiceModel.Description.WebScriptEnablingBehavior>
- [<span data-ttu-id="5b2c7-117">AJAX-Integration und JSON-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="5b2c7-117">AJAX Integration and JSON Support</span></span>](../../../wcf/feature-details/ajax-integration-and-json-support.md)
- [\<webHttp>](webhttp.md)
