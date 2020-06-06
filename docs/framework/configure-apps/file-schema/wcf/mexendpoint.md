---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855112"
---
# \<mexEndpoint>
<span data-ttu-id="695a5-101">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="695a5-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="695a5-102">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="695a5-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="695a5-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="695a5-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="695a5-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="695a5-104">Attributes and Elements</span></span>  
 <span data-ttu-id="695a5-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="695a5-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="695a5-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="695a5-106">Attributes</span></span>  
  
|<span data-ttu-id="695a5-107">attribute</span><span class="sxs-lookup"><span data-stu-id="695a5-107">Attribute</span></span>|<span data-ttu-id="695a5-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="695a5-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="695a5-109">name</span><span class="sxs-lookup"><span data-stu-id="695a5-109">name</span></span>|<span data-ttu-id="695a5-110">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="695a5-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="695a5-111">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="695a5-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="695a5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="695a5-112">Child Elements</span></span>  
 <span data-ttu-id="695a5-113">Keine</span><span class="sxs-lookup"><span data-stu-id="695a5-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="695a5-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="695a5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="695a5-115">Element</span><span class="sxs-lookup"><span data-stu-id="695a5-115">Element</span></span>|<span data-ttu-id="695a5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="695a5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="695a5-117">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="695a5-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
