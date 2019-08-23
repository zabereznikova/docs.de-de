---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937202"
---
# <a name="services"></a><span data-ttu-id="2cc79-101">\<services></span><span class="sxs-lookup"><span data-stu-id="2cc79-101">\<services></span></span>
<span data-ttu-id="2cc79-102">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="2cc79-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="2cc79-103">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="2cc79-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="2cc79-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2cc79-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc79-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cc79-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cc79-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc79-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2cc79-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cc79-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cc79-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cc79-108">Attributes</span></span>  
 <span data-ttu-id="2cc79-109">None</span><span class="sxs-lookup"><span data-stu-id="2cc79-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2cc79-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc79-110">Child Elements</span></span>  
  
|<span data-ttu-id="2cc79-111">Element</span><span class="sxs-lookup"><span data-stu-id="2cc79-111">Element</span></span>|<span data-ttu-id="2cc79-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc79-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc79-113">\<service></span><span class="sxs-lookup"><span data-stu-id="2cc79-113">\<service></span></span>](service.md)|<span data-ttu-id="2cc79-114">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="2cc79-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cc79-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cc79-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2cc79-116">Element</span><span class="sxs-lookup"><span data-stu-id="2cc79-116">Element</span></span>|<span data-ttu-id="2cc79-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cc79-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cc79-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2cc79-118">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="2cc79-119">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="2cc79-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cc79-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc79-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
