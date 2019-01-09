---
title: '&lt;add&gt; von &lt;baseAddresses&gt;'
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: ce476c2d40758cf52eada813873d061d0e441bce
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149084"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="f828b-102">&lt;add&gt; von &lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="f828b-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="f828b-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="f828b-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="f828b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f828b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f828b-105">\<Client ></span><span class="sxs-lookup"><span data-stu-id="f828b-105">\<client></span></span>  
<span data-ttu-id="f828b-106">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="f828b-106">\<endpoint></span></span>  
<span data-ttu-id="f828b-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="f828b-107">\<host></span></span>  
<span data-ttu-id="f828b-108">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="f828b-108">\<baseAddresses></span></span>  
<span data-ttu-id="f828b-109">\<BaseAddress ></span><span class="sxs-lookup"><span data-stu-id="f828b-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f828b-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="f828b-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="f828b-111">Typ</span><span class="sxs-lookup"><span data-stu-id="f828b-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f828b-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f828b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f828b-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f828b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f828b-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="f828b-114">Attributes</span></span>  
  
|<span data-ttu-id="f828b-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="f828b-115">Attribute</span></span>|<span data-ttu-id="f828b-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f828b-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="f828b-117">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="f828b-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f828b-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f828b-118">Child Elements</span></span>  
 <span data-ttu-id="f828b-119">Keine</span><span class="sxs-lookup"><span data-stu-id="f828b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f828b-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f828b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f828b-121">Element</span><span class="sxs-lookup"><span data-stu-id="f828b-121">Element</span></span>|<span data-ttu-id="f828b-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f828b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f828b-123">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="f828b-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="f828b-124">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="f828b-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f828b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f828b-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="f828b-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="f828b-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
