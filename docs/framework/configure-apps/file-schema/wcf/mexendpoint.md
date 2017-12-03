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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6eefecb696c88d160e56c7f12a1b03ea67e531b6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="a213f-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="a213f-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="a213f-103">Dieses Konfigurationselement definiert einen Standardendpunkt mit einem festen IMetadataExchange-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="a213f-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="a213f-104">Da alle Metadatenaustausch-Endpunkte IMetadataExchange als Vertrag angeben, können Sie diesen Standardpunkt verwenden, statt einen eigenen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a213f-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="a213f-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a213f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="a213f-106">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a213f-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a213f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a213f-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a213f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a213f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a213f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a213f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a213f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a213f-110">Attributes</span></span>  
  
|<span data-ttu-id="a213f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a213f-111">Attribute</span></span>|<span data-ttu-id="a213f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a213f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a213f-113">Name</span><span class="sxs-lookup"><span data-stu-id="a213f-113">name</span></span>|<span data-ttu-id="a213f-114">Eine Zeichenfolge, die den Namen der Konfiguration des Standardendpunkts angibt.</span><span class="sxs-lookup"><span data-stu-id="a213f-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="a213f-115">Der Name wird im `endpointConfiguration`-Attribut des Dienstendpunkts zum Verknüpfen eines Standardendpunkts mit der Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="a213f-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a213f-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a213f-116">Child Elements</span></span>  
 <span data-ttu-id="a213f-117">Keine</span><span class="sxs-lookup"><span data-stu-id="a213f-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a213f-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a213f-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a213f-119">Element</span><span class="sxs-lookup"><span data-stu-id="a213f-119">Element</span></span>|<span data-ttu-id="a213f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a213f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a213f-121">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="a213f-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="a213f-122">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a213f-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
