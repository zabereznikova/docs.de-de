---
title: '&lt;Dienste&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 789fc52f628174ef61a9c7169cb0cae0f1ba8e31
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltservicesgt"></a><span data-ttu-id="e32b2-102">&lt;Dienste&gt;</span><span class="sxs-lookup"><span data-stu-id="e32b2-102">&lt;services&gt;</span></span>
<span data-ttu-id="e32b2-103">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="e32b2-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e32b2-104">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="e32b2-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="e32b2-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e32b2-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32b2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e32b2-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e32b2-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e32b2-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e32b2-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e32b2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e32b2-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="e32b2-109">Attributes</span></span>  
 <span data-ttu-id="e32b2-110">Keiner</span><span class="sxs-lookup"><span data-stu-id="e32b2-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e32b2-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e32b2-111">Child Elements</span></span>  
  
|<span data-ttu-id="e32b2-112">Element</span><span class="sxs-lookup"><span data-stu-id="e32b2-112">Element</span></span>|<span data-ttu-id="e32b2-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e32b2-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e32b2-114">\<service></span><span class="sxs-lookup"><span data-stu-id="e32b2-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="e32b2-115">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e32b2-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e32b2-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e32b2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="e32b2-117">Element</span><span class="sxs-lookup"><span data-stu-id="e32b2-117">Element</span></span>|<span data-ttu-id="e32b2-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e32b2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e32b2-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e32b2-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="e32b2-120">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="e32b2-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e32b2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e32b2-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
