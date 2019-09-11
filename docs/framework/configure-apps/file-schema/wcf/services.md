---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 02d1d530f37f5082153c9aa6b9993fc4009917f5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854982"
---
# <a name="services"></a><span data-ttu-id="0353f-101">\<services></span><span class="sxs-lookup"><span data-stu-id="0353f-101">\<services></span></span>
<span data-ttu-id="0353f-102">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="0353f-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="0353f-103">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="0353f-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="0353f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0353f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0353f-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0353f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0353f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Dienste >**</span><span class="sxs-lookup"><span data-stu-id="0353f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0353f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0353f-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0353f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0353f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0353f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0353f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0353f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="0353f-110">Attributes</span></span>  
 <span data-ttu-id="0353f-111">None</span><span class="sxs-lookup"><span data-stu-id="0353f-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0353f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0353f-112">Child Elements</span></span>  
  
|<span data-ttu-id="0353f-113">Element</span><span class="sxs-lookup"><span data-stu-id="0353f-113">Element</span></span>|<span data-ttu-id="0353f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0353f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0353f-115">\<service></span><span class="sxs-lookup"><span data-stu-id="0353f-115">\<service></span></span>](service.md)|<span data-ttu-id="0353f-116">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="0353f-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0353f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0353f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0353f-118">Element</span><span class="sxs-lookup"><span data-stu-id="0353f-118">Element</span></span>|<span data-ttu-id="0353f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0353f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0353f-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0353f-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="0353f-121">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="0353f-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0353f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0353f-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
