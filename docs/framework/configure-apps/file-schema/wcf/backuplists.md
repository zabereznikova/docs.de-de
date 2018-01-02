---
title: '&lt;backupLists&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5fee9e455189d5be1c81fb950eff3882aa8222b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="fa84e-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="fa84e-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="fa84e-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa84e-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="fa84e-104">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa84e-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="fa84e-105">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="fa84e-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="fa84e-106">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="fa84e-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="fa84e-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fa84e-107">\<system.serviceModel></span></span>  
<span data-ttu-id="fa84e-108">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="fa84e-108">\<routing></span></span>  
<span data-ttu-id="fa84e-109">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="fa84e-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa84e-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa84e-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fa84e-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa84e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa84e-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa84e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa84e-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa84e-113">Attributes</span></span>  
 <span data-ttu-id="fa84e-114">Keine</span><span class="sxs-lookup"><span data-stu-id="fa84e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa84e-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa84e-115">Child Elements</span></span>  
  
|<span data-ttu-id="fa84e-116">Element</span><span class="sxs-lookup"><span data-stu-id="fa84e-116">Element</span></span>|<span data-ttu-id="fa84e-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa84e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa84e-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="fa84e-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="fa84e-119">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="fa84e-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="fa84e-120">sein.</span><span class="sxs-lookup"><span data-stu-id="fa84e-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa84e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa84e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fa84e-122">Element</span><span class="sxs-lookup"><span data-stu-id="fa84e-122">Element</span></span>|<span data-ttu-id="fa84e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa84e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa84e-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="fa84e-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="fa84e-125">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die bestimmen, welche [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die definieren, die Zielendpunkte zum Senden von Nachrichten, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fa84e-125">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa84e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa84e-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
