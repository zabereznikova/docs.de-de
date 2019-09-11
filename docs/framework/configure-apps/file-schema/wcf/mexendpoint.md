---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855112"
---
# <a name="mexendpoint"></a><span data-ttu-id="9cf49-101">\<mexendpoint-></span><span class="sxs-lookup"><span data-stu-id="9cf49-101">\<mexEndpoint></span></span>
<span data-ttu-id="9cf49-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="9cf49-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="9cf49-103">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="9cf49-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="9cf49-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9cf49-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9cf49-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9cf49-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9cf49-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="9cf49-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="9cf49-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexendpoint->**</span><span class="sxs-lookup"><span data-stu-id="9cf49-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf49-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf49-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cf49-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf49-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9cf49-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9cf49-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cf49-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9cf49-111">Attributes</span></span>  
  
|<span data-ttu-id="9cf49-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9cf49-112">Attribute</span></span>|<span data-ttu-id="9cf49-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cf49-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cf49-114">NAME</span><span class="sxs-lookup"><span data-stu-id="9cf49-114">name</span></span>|<span data-ttu-id="9cf49-115">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="9cf49-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="9cf49-116">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cf49-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cf49-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf49-117">Child Elements</span></span>  
 <span data-ttu-id="9cf49-118">Keine</span><span class="sxs-lookup"><span data-stu-id="9cf49-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cf49-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9cf49-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9cf49-120">Element</span><span class="sxs-lookup"><span data-stu-id="9cf49-120">Element</span></span>|<span data-ttu-id="9cf49-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cf49-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cf49-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="9cf49-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="9cf49-123">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="9cf49-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
