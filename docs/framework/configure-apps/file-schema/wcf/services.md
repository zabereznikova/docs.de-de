---
title: '&lt;Dienste&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca55770da8da0fe91a12aeb5fa72e61d6dcd67ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="7c6f1-102">&lt;Dienste&gt;</span><span class="sxs-lookup"><span data-stu-id="7c6f1-102">&lt;services&gt;</span></span>
<span data-ttu-id="7c6f1-103">Dienste werden im `services`-Abschnitt der Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="7c6f1-104">Jeder Dienst hat seinen eigenen `service`-Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="7c6f1-105">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7c6f1-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6f1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c6f1-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c6f1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c6f1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7c6f1-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c6f1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c6f1-109">Attributes</span></span>  
 <span data-ttu-id="7c6f1-110">Keine</span><span class="sxs-lookup"><span data-stu-id="7c6f1-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7c6f1-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c6f1-111">Child Elements</span></span>  
  
|<span data-ttu-id="7c6f1-112">Element</span><span class="sxs-lookup"><span data-stu-id="7c6f1-112">Element</span></span>|<span data-ttu-id="7c6f1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c6f1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c6f1-114">\<Dienst ></span><span class="sxs-lookup"><span data-stu-id="7c6f1-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="7c6f1-115">Definiert den Dienstvertrag, das Verhalten und die Endpunkte des Diensts.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c6f1-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c6f1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7c6f1-117">Element</span><span class="sxs-lookup"><span data-stu-id="7c6f1-117">Element</span></span>|<span data-ttu-id="7c6f1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c6f1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c6f1-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7c6f1-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="7c6f1-120">Das Stammelement aller Windows Communication Foundation (WCF)-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="7c6f1-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c6f1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c6f1-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
