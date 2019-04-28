---
title: <add> von <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: fbcb3a07bf40c96a4cd1b2ec87277b6fefdfb89d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704452"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="b0952-102">\<add> of \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="b0952-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="b0952-103">Stellt ein Konfigurationselement dar, das die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="b0952-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="b0952-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0952-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0952-105">\<client></span><span class="sxs-lookup"><span data-stu-id="b0952-105">\<client></span></span>  
<span data-ttu-id="b0952-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="b0952-106">\<endpoint></span></span>  
<span data-ttu-id="b0952-107">\<host></span><span class="sxs-lookup"><span data-stu-id="b0952-107">\<host></span></span>  
<span data-ttu-id="b0952-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="b0952-108">\<baseAddresses></span></span>  
<span data-ttu-id="b0952-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="b0952-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0952-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0952-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="b0952-111">Typ</span><span class="sxs-lookup"><span data-stu-id="b0952-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0952-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b0952-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b0952-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b0952-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0952-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b0952-114">Attributes</span></span>  
  
|<span data-ttu-id="b0952-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="b0952-115">Attribute</span></span>|<span data-ttu-id="b0952-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0952-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="b0952-117">Eine Zeichenfolge, welche die vom Diensthost verwendeten Basisadressen angibt.</span><span class="sxs-lookup"><span data-stu-id="b0952-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0952-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0952-118">Child Elements</span></span>  
 <span data-ttu-id="b0952-119">Keine</span><span class="sxs-lookup"><span data-stu-id="b0952-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0952-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b0952-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0952-121">Element</span><span class="sxs-lookup"><span data-stu-id="b0952-121">Element</span></span>|<span data-ttu-id="b0952-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0952-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0952-123">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="b0952-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="b0952-124">Eine Auflistung von `baseAddress`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="b0952-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0952-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0952-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="b0952-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="b0952-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
