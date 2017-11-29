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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e941b63e42af9237388df6be8223acbad8db745
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="3d36d-102">&lt;add&gt; von &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="3d36d-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="3d36d-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="3d36d-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="3d36d-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3d36d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3d36d-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="3d36d-105">\<client></span></span>  
<span data-ttu-id="3d36d-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="3d36d-106">\<endpoint></span></span>  
<span data-ttu-id="3d36d-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="3d36d-107">\<host></span></span>  
<span data-ttu-id="3d36d-108">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="3d36d-108">\<baseAddresses></span></span>  
<span data-ttu-id="3d36d-109">\<BaseAddress-Element ></span><span class="sxs-lookup"><span data-stu-id="3d36d-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d36d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d36d-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="3d36d-111">Typ</span><span class="sxs-lookup"><span data-stu-id="3d36d-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d36d-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3d36d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3d36d-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3d36d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d36d-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="3d36d-114">Attributes</span></span>  
  
|<span data-ttu-id="3d36d-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="3d36d-115">Attribute</span></span>|<span data-ttu-id="3d36d-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d36d-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="3d36d-117">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="3d36d-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3d36d-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d36d-118">Child Elements</span></span>  
 <span data-ttu-id="3d36d-119">Keine</span><span class="sxs-lookup"><span data-stu-id="3d36d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3d36d-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3d36d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3d36d-121">Element</span><span class="sxs-lookup"><span data-stu-id="3d36d-121">Element</span></span>|<span data-ttu-id="3d36d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d36d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d36d-123">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="3d36d-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="3d36d-124">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="3d36d-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3d36d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d36d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="3d36d-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="3d36d-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
