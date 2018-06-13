---
title: '&lt;mexEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: aceff3e373d9a5f7e57c28d85870af19ae8ef3e1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747784"
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="21900-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="21900-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="21900-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="21900-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="21900-104">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="21900-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="21900-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="21900-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="21900-106">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="21900-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21900-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="21900-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21900-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="21900-108">Attributes and Elements</span></span>  
 <span data-ttu-id="21900-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="21900-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21900-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="21900-110">Attributes</span></span>  
  
|<span data-ttu-id="21900-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="21900-111">Attribute</span></span>|<span data-ttu-id="21900-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21900-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21900-113">Name</span><span class="sxs-lookup"><span data-stu-id="21900-113">name</span></span>|<span data-ttu-id="21900-114">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="21900-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="21900-115">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="21900-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21900-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21900-116">Child Elements</span></span>  
 <span data-ttu-id="21900-117">Keine</span><span class="sxs-lookup"><span data-stu-id="21900-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21900-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="21900-118">Parent Elements</span></span>  
  
|<span data-ttu-id="21900-119">Element</span><span class="sxs-lookup"><span data-stu-id="21900-119">Element</span></span>|<span data-ttu-id="21900-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21900-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21900-121">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="21900-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="21900-122">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="21900-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
