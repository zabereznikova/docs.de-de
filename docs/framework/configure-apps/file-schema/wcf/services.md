---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59168076"
---
# <a name="services"></a><span data-ttu-id="b13ae-101">\<services></span><span class="sxs-lookup"><span data-stu-id="b13ae-101">\<services></span></span>
<span data-ttu-id="b13ae-102">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="b13ae-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="b13ae-103">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="b13ae-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="b13ae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b13ae-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13ae-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b13ae-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b13ae-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b13ae-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b13ae-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b13ae-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b13ae-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="b13ae-108">Attributes</span></span>  
 <span data-ttu-id="b13ae-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="b13ae-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b13ae-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b13ae-110">Child Elements</span></span>  
  
|<span data-ttu-id="b13ae-111">Element</span><span class="sxs-lookup"><span data-stu-id="b13ae-111">Element</span></span>|<span data-ttu-id="b13ae-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b13ae-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b13ae-113">\<service></span><span class="sxs-lookup"><span data-stu-id="b13ae-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="b13ae-114">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b13ae-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b13ae-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b13ae-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b13ae-116">Element</span><span class="sxs-lookup"><span data-stu-id="b13ae-116">Element</span></span>|<span data-ttu-id="b13ae-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b13ae-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b13ae-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b13ae-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="b13ae-119">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="b13ae-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b13ae-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b13ae-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
