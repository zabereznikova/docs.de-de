---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5fb89ce5a942db40b07a65f59ddd05ab4cd624aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="947f3-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="947f3-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="947f3-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="947f3-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="947f3-104">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="947f3-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="947f3-105">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="947f3-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="947f3-106">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="947f3-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="947f3-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="947f3-107">\<system.serviceModel></span></span>  
<span data-ttu-id="947f3-108">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="947f3-108">\<routing></span></span>  
<span data-ttu-id="947f3-109">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="947f3-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="947f3-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="947f3-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="947f3-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="947f3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="947f3-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="947f3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="947f3-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="947f3-113">Attributes</span></span>  
 <span data-ttu-id="947f3-114">Keine</span><span class="sxs-lookup"><span data-stu-id="947f3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="947f3-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="947f3-115">Child Elements</span></span>  
  
|<span data-ttu-id="947f3-116">Element</span><span class="sxs-lookup"><span data-stu-id="947f3-116">Element</span></span>|<span data-ttu-id="947f3-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="947f3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="947f3-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="947f3-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="947f3-119">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="947f3-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="947f3-120">sein.</span><span class="sxs-lookup"><span data-stu-id="947f3-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="947f3-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="947f3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="947f3-122">Element</span><span class="sxs-lookup"><span data-stu-id="947f3-122">Element</span></span>|<span data-ttu-id="947f3-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="947f3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="947f3-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="947f3-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="947f3-125">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) zu bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="947f3-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="947f3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="947f3-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
