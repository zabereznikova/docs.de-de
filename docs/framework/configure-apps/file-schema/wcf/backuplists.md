---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: b65cc4d04b5304e93b70509c9db3bc2248accb7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926432"
---
# <a name="backuplists"></a><span data-ttu-id="287e2-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="287e2-101">\<backupLists></span></span>
<span data-ttu-id="287e2-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="287e2-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="287e2-103">Jedes untergeordnete Element ist eine Sicherungsliste, die eine Reihe von Endpunkten auflistet, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="287e2-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="287e2-104">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="287e2-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="287e2-105">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="287e2-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="287e2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="287e2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="287e2-107">\<routing></span><span class="sxs-lookup"><span data-stu-id="287e2-107">\<routing></span></span>  
<span data-ttu-id="287e2-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="287e2-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="287e2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="287e2-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="287e2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="287e2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="287e2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="287e2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="287e2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="287e2-112">Attributes</span></span>  
 <span data-ttu-id="287e2-113">Keine</span><span class="sxs-lookup"><span data-stu-id="287e2-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="287e2-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="287e2-114">Child Elements</span></span>  
  
|<span data-ttu-id="287e2-115">Element</span><span class="sxs-lookup"><span data-stu-id="287e2-115">Element</span></span>|<span data-ttu-id="287e2-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="287e2-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="287e2-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="287e2-117">\<filter></span></span>](filter.md)|<span data-ttu-id="287e2-118">Enthält eine Liste von Endpunkten, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="287e2-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="287e2-119">.</span><span class="sxs-lookup"><span data-stu-id="287e2-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="287e2-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="287e2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="287e2-121">Element</span><span class="sxs-lookup"><span data-stu-id="287e2-121">Element</span></span>|<span data-ttu-id="287e2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="287e2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="287e2-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="287e2-123">\<routing></span></span>](routing.md)|<span data-ttu-id="287e2-124">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="287e2-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="287e2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="287e2-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
