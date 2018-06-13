---
title: '&lt;add&gt; von &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 3f1b7e8f1f4ab8542270d459ce5020ce4320eea9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754144"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="d0629-102">&lt;add&gt; von &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="d0629-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="d0629-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="d0629-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="d0629-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0629-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0629-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="d0629-105">\<client></span></span>  
<span data-ttu-id="d0629-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="d0629-106">\<endpoint></span></span>  
<span data-ttu-id="d0629-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="d0629-107">\<host></span></span>  
<span data-ttu-id="d0629-108">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="d0629-108">\<baseAddresses></span></span>  
<span data-ttu-id="d0629-109">\<BaseAddress-Element ></span><span class="sxs-lookup"><span data-stu-id="d0629-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0629-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0629-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="d0629-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d0629-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0629-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d0629-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d0629-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d0629-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0629-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d0629-114">Attributes</span></span>  
  
|<span data-ttu-id="d0629-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="d0629-115">Attribute</span></span>|<span data-ttu-id="d0629-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0629-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="d0629-117">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="d0629-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0629-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0629-118">Child Elements</span></span>  
 <span data-ttu-id="d0629-119">Keine</span><span class="sxs-lookup"><span data-stu-id="d0629-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0629-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d0629-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d0629-121">Element</span><span class="sxs-lookup"><span data-stu-id="d0629-121">Element</span></span>|<span data-ttu-id="d0629-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0629-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0629-123">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="d0629-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="d0629-124">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="d0629-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0629-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0629-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="d0629-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="d0629-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
