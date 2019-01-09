---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: ff363f97b25496dc9bb3a691de7c8abf77c0dc9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149123"
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="7ad42-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="7ad42-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="7ad42-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7ad42-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="7ad42-104">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="7ad42-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7ad42-105">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7ad42-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="7ad42-106">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="7ad42-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="7ad42-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7ad42-107">\<system.serviceModel></span></span>  
<span data-ttu-id="7ad42-108">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="7ad42-108">\<routing></span></span>  
<span data-ttu-id="7ad42-109">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="7ad42-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ad42-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ad42-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ad42-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7ad42-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7ad42-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7ad42-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ad42-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="7ad42-113">Attributes</span></span>  
 <span data-ttu-id="7ad42-114">Keine</span><span class="sxs-lookup"><span data-stu-id="7ad42-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ad42-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ad42-115">Child Elements</span></span>  
  
|<span data-ttu-id="7ad42-116">Element</span><span class="sxs-lookup"><span data-stu-id="7ad42-116">Element</span></span>|<span data-ttu-id="7ad42-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ad42-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ad42-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="7ad42-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="7ad42-119">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="7ad42-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7ad42-120">sein.</span><span class="sxs-lookup"><span data-stu-id="7ad42-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ad42-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7ad42-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7ad42-122">Element</span><span class="sxs-lookup"><span data-stu-id="7ad42-122">Element</span></span>|<span data-ttu-id="7ad42-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ad42-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ad42-124">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="7ad42-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="7ad42-125">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="7ad42-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ad42-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ad42-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
