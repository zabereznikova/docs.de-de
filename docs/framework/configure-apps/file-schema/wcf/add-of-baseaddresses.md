---
title: '&lt;add&gt; von &lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf417653652c2a0f28fe5c6491a7da9949678140
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="e2b94-102">&lt;add&gt; von &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="e2b94-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="e2b94-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="e2b94-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="e2b94-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e2b94-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2b94-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="e2b94-105">\<client></span></span>  
<span data-ttu-id="e2b94-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="e2b94-106">\<endpoint></span></span>  
<span data-ttu-id="e2b94-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="e2b94-107">\<host></span></span>  
<span data-ttu-id="e2b94-108">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="e2b94-108">\<baseAddresses></span></span>  
<span data-ttu-id="e2b94-109">\<BaseAddress-Element ></span><span class="sxs-lookup"><span data-stu-id="e2b94-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2b94-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2b94-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="e2b94-111">Typ</span><span class="sxs-lookup"><span data-stu-id="e2b94-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2b94-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e2b94-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e2b94-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2b94-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2b94-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="e2b94-114">Attributes</span></span>  
  
|<span data-ttu-id="e2b94-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2b94-115">Attribute</span></span>|<span data-ttu-id="e2b94-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2b94-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="e2b94-117">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="e2b94-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2b94-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2b94-118">Child Elements</span></span>  
 <span data-ttu-id="e2b94-119">Keine</span><span class="sxs-lookup"><span data-stu-id="e2b94-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2b94-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2b94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e2b94-121">Element</span><span class="sxs-lookup"><span data-stu-id="e2b94-121">Element</span></span>|<span data-ttu-id="e2b94-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2b94-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2b94-123">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="e2b94-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="e2b94-124">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="e2b94-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2b94-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2b94-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="e2b94-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="e2b94-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
