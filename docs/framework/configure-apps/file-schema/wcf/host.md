---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102998"
---
# <a name="host"></a><span data-ttu-id="cc832-101">\<host></span><span class="sxs-lookup"><span data-stu-id="cc832-101">\<host></span></span>
<span data-ttu-id="cc832-102">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="cc832-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="cc832-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cc832-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc832-104">\<services></span><span class="sxs-lookup"><span data-stu-id="cc832-104">\<services></span></span>  
<span data-ttu-id="cc832-105">\<service></span><span class="sxs-lookup"><span data-stu-id="cc832-105">\<service></span></span>  
<span data-ttu-id="cc832-106">\<host></span><span class="sxs-lookup"><span data-stu-id="cc832-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc832-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc832-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="cc832-108">Typ</span><span class="sxs-lookup"><span data-stu-id="cc832-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc832-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc832-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cc832-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc832-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc832-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="cc832-111">Attributes</span></span>  
 <span data-ttu-id="cc832-112">Keine</span><span class="sxs-lookup"><span data-stu-id="cc832-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cc832-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc832-113">Child Elements</span></span>  
  
|<span data-ttu-id="cc832-114">Element</span><span class="sxs-lookup"><span data-stu-id="cc832-114">Element</span></span>|<span data-ttu-id="cc832-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc832-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc832-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="cc832-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="cc832-117">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="cc832-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="cc832-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="cc832-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="cc832-119">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="cc832-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc832-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc832-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cc832-121">Element</span><span class="sxs-lookup"><span data-stu-id="cc832-121">Element</span></span>|<span data-ttu-id="cc832-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc832-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc832-123">\<service></span><span class="sxs-lookup"><span data-stu-id="cc832-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="cc832-124">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="cc832-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc832-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc832-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="cc832-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="cc832-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
