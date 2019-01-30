---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271693"
---
# <a name="mexendpoint"></a><span data-ttu-id="90aab-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="90aab-101">\<mexEndpoint></span></span>
<span data-ttu-id="90aab-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="90aab-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="90aab-103">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="90aab-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="90aab-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="90aab-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="90aab-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="90aab-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90aab-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="90aab-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90aab-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90aab-107">Attributes and Elements</span></span>  
 <span data-ttu-id="90aab-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90aab-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90aab-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="90aab-109">Attributes</span></span>  
  
|<span data-ttu-id="90aab-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="90aab-110">Attribute</span></span>|<span data-ttu-id="90aab-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90aab-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90aab-112">Name</span><span class="sxs-lookup"><span data-stu-id="90aab-112">name</span></span>|<span data-ttu-id="90aab-113">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="90aab-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="90aab-114">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="90aab-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90aab-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90aab-115">Child Elements</span></span>  
 <span data-ttu-id="90aab-116">Keine</span><span class="sxs-lookup"><span data-stu-id="90aab-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90aab-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90aab-117">Parent Elements</span></span>  
  
|<span data-ttu-id="90aab-118">Element</span><span class="sxs-lookup"><span data-stu-id="90aab-118">Element</span></span>|<span data-ttu-id="90aab-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90aab-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90aab-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="90aab-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="90aab-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="90aab-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
