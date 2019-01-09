---
title: '&lt;Dienste&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: a48bd0ac30c1a85602122b2fd9213c2aa5159e91
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148096"
---
# <a name="ltservicesgt"></a><span data-ttu-id="4b17a-102">&lt;Dienste&gt;</span><span class="sxs-lookup"><span data-stu-id="4b17a-102">&lt;services&gt;</span></span>
<span data-ttu-id="4b17a-103">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="4b17a-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="4b17a-104">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="4b17a-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="4b17a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4b17a-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b17a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b17a-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b17a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4b17a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="4b17a-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4b17a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b17a-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="4b17a-109">Attributes</span></span>  
 <span data-ttu-id="4b17a-110">Keine</span><span class="sxs-lookup"><span data-stu-id="4b17a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b17a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b17a-111">Child Elements</span></span>  
  
|<span data-ttu-id="4b17a-112">Element</span><span class="sxs-lookup"><span data-stu-id="4b17a-112">Element</span></span>|<span data-ttu-id="4b17a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b17a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b17a-114">\<service></span><span class="sxs-lookup"><span data-stu-id="4b17a-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="4b17a-115">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="4b17a-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b17a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4b17a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4b17a-117">Element</span><span class="sxs-lookup"><span data-stu-id="4b17a-117">Element</span></span>|<span data-ttu-id="4b17a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b17a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b17a-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b17a-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="4b17a-120">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="4b17a-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4b17a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b17a-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
