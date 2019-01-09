---
title: '&lt;Host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: afa9d65223ab3a7730a55bc41ed98458707b32db
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145225"
---
# <a name="lthostgt"></a><span data-ttu-id="7c214-102">&lt;Host&gt;</span><span class="sxs-lookup"><span data-stu-id="7c214-102">&lt;host&gt;</span></span>
<span data-ttu-id="7c214-103">Gibt die Einstellungen für einen Diensthost an.</span><span class="sxs-lookup"><span data-stu-id="7c214-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="7c214-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7c214-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="7c214-105">\<Dienste ></span><span class="sxs-lookup"><span data-stu-id="7c214-105">\<services></span></span>  
<span data-ttu-id="7c214-106">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="7c214-106">\<service></span></span>  
<span data-ttu-id="7c214-107">\<Host ></span><span class="sxs-lookup"><span data-stu-id="7c214-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c214-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c214-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="7c214-109">Typ</span><span class="sxs-lookup"><span data-stu-id="7c214-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c214-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c214-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7c214-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c214-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c214-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c214-112">Attributes</span></span>  
 <span data-ttu-id="7c214-113">Keine</span><span class="sxs-lookup"><span data-stu-id="7c214-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7c214-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c214-114">Child Elements</span></span>  
  
|<span data-ttu-id="7c214-115">Element</span><span class="sxs-lookup"><span data-stu-id="7c214-115">Element</span></span>|<span data-ttu-id="7c214-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c214-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c214-117">\<BaseAddresses ></span><span class="sxs-lookup"><span data-stu-id="7c214-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="7c214-118">Eine Auflistung an `baseAddress`-Elementen, die die vom Diensthost verwendeten Basisadressen angeben.</span><span class="sxs-lookup"><span data-stu-id="7c214-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="7c214-119">\<TimeOuts ></span><span class="sxs-lookup"><span data-stu-id="7c214-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="7c214-120">Ein Konfigurationselement, das das für das Öffnen und Schließen des Diensthosts zulässige Zeitintervall angibt.</span><span class="sxs-lookup"><span data-stu-id="7c214-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c214-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c214-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7c214-122">Element</span><span class="sxs-lookup"><span data-stu-id="7c214-122">Element</span></span>|<span data-ttu-id="7c214-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c214-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c214-124">\<service></span><span class="sxs-lookup"><span data-stu-id="7c214-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="7c214-125">Gibt die Einstellungen für einen Windows Communication Foundation (WCF)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="7c214-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c214-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c214-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="7c214-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="7c214-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
