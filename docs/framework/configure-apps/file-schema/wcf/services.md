---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153715"
---
# \<services>

<span data-ttu-id="59893-101">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="59893-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="59893-102">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="59893-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="59893-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="59893-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59893-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59893-104">Attributes and Elements</span></span>  

 <span data-ttu-id="59893-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59893-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59893-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="59893-106">Attributes</span></span>  

 <span data-ttu-id="59893-107">Keine</span><span class="sxs-lookup"><span data-stu-id="59893-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59893-108">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59893-108">Child Elements</span></span>  
  
|<span data-ttu-id="59893-109">Element</span><span class="sxs-lookup"><span data-stu-id="59893-109">Element</span></span>|<span data-ttu-id="59893-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59893-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="59893-111">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="59893-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59893-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59893-112">Parent Elements</span></span>  
  
|<span data-ttu-id="59893-113">Element</span><span class="sxs-lookup"><span data-stu-id="59893-113">Element</span></span>|<span data-ttu-id="59893-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59893-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="59893-115">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="59893-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59893-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="59893-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
