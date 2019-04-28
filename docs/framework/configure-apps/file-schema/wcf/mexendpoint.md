---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772475"
---
# <a name="mexendpoint"></a><span data-ttu-id="8e6cc-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="8e6cc-101">\<mexEndpoint></span></span>
<span data-ttu-id="8e6cc-102">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="8e6cc-103">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="8e6cc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8e6cc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e6cc-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8e6cc-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e6cc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e6cc-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e6cc-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6cc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8e6cc-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e6cc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="8e6cc-109">Attributes</span></span>  
  
|<span data-ttu-id="8e6cc-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="8e6cc-110">Attribute</span></span>|<span data-ttu-id="8e6cc-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e6cc-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e6cc-112">Name</span><span class="sxs-lookup"><span data-stu-id="8e6cc-112">name</span></span>|<span data-ttu-id="8e6cc-113">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="8e6cc-114">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e6cc-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6cc-115">Child Elements</span></span>  
 <span data-ttu-id="8e6cc-116">Keine</span><span class="sxs-lookup"><span data-stu-id="8e6cc-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e6cc-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8e6cc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8e6cc-118">Element</span><span class="sxs-lookup"><span data-stu-id="8e6cc-118">Element</span></span>|<span data-ttu-id="8e6cc-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e6cc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e6cc-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8e6cc-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8e6cc-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8e6cc-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
