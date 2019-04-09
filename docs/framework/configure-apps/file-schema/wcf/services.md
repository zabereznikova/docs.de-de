---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168076"
---
# <a name="services"></a><span data-ttu-id="acfe4-101">\<services></span><span class="sxs-lookup"><span data-stu-id="acfe4-101">\<services></span></span>
<span data-ttu-id="acfe4-102">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="acfe4-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="acfe4-103">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="acfe4-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="acfe4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="acfe4-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acfe4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="acfe4-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acfe4-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="acfe4-106">Attributes and Elements</span></span>  
 <span data-ttu-id="acfe4-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="acfe4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acfe4-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="acfe4-108">Attributes</span></span>  
 <span data-ttu-id="acfe4-109">Keiner</span><span class="sxs-lookup"><span data-stu-id="acfe4-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="acfe4-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acfe4-110">Child Elements</span></span>  
  
|<span data-ttu-id="acfe4-111">Element</span><span class="sxs-lookup"><span data-stu-id="acfe4-111">Element</span></span>|<span data-ttu-id="acfe4-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acfe4-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acfe4-113">\<service></span><span class="sxs-lookup"><span data-stu-id="acfe4-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="acfe4-114">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="acfe4-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="acfe4-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="acfe4-115">Parent Elements</span></span>  
  
|<span data-ttu-id="acfe4-116">Element</span><span class="sxs-lookup"><span data-stu-id="acfe4-116">Element</span></span>|<span data-ttu-id="acfe4-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acfe4-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="acfe4-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="acfe4-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="acfe4-119">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="acfe4-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="acfe4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acfe4-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
