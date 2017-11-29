---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75886c08d3e358d4ed6d3d3048594ef28f06a7af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="e6b3c-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="e6b3c-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="e6b3c-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="e6b3c-104">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="e6b3c-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e6b3c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e6b3c-106">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e6b3c-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b3c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6b3c-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6b3c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e6b3c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e6b3c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6b3c-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e6b3c-110">Attributes</span></span>  
  
|<span data-ttu-id="e6b3c-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e6b3c-111">Attribute</span></span>|<span data-ttu-id="e6b3c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b3c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e6b3c-113">Name</span><span class="sxs-lookup"><span data-stu-id="e6b3c-113">name</span></span>|<span data-ttu-id="e6b3c-114">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="e6b3c-115">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6b3c-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6b3c-116">Child Elements</span></span>  
 <span data-ttu-id="e6b3c-117">Keine</span><span class="sxs-lookup"><span data-stu-id="e6b3c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6b3c-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e6b3c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e6b3c-119">Element</span><span class="sxs-lookup"><span data-stu-id="e6b3c-119">Element</span></span>|<span data-ttu-id="e6b3c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b3c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6b3c-121">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="e6b3c-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="e6b3c-122">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="e6b3c-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
