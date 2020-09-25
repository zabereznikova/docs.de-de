---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: e8f0e0fa2ea1606bf980fd6fa1fcd47f12c3b540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204748"
---
# \<mexEndpoint>

<span data-ttu-id="3dc35-101">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="3dc35-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="3dc35-102">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="3dc35-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="3dc35-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="3dc35-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dc35-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3dc35-104">Attributes and Elements</span></span>  

 <span data-ttu-id="3dc35-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3dc35-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dc35-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="3dc35-106">Attributes</span></span>  
  
|<span data-ttu-id="3dc35-107">attribute</span><span class="sxs-lookup"><span data-stu-id="3dc35-107">Attribute</span></span>|<span data-ttu-id="3dc35-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3dc35-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dc35-109">name</span><span class="sxs-lookup"><span data-stu-id="3dc35-109">name</span></span>|<span data-ttu-id="3dc35-110">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="3dc35-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3dc35-111">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="3dc35-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dc35-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3dc35-112">Child Elements</span></span>  

 <span data-ttu-id="3dc35-113">Keine</span><span class="sxs-lookup"><span data-stu-id="3dc35-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dc35-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3dc35-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3dc35-115">Element</span><span class="sxs-lookup"><span data-stu-id="3dc35-115">Element</span></span>|<span data-ttu-id="3dc35-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3dc35-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="3dc35-117">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="3dc35-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
