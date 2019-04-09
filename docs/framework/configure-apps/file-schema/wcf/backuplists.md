---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6e44dbe3c0966c6d243db343b9f9b0dec2480cb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134445"
---
# <a name="backuplists"></a><span data-ttu-id="5a744-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="5a744-101">\<backupLists></span></span>
<span data-ttu-id="5a744-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a744-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="5a744-103">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a744-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="5a744-104">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5a744-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="5a744-105">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="5a744-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="5a744-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5a744-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5a744-107">\<routing></span><span class="sxs-lookup"><span data-stu-id="5a744-107">\<routing></span></span>  
<span data-ttu-id="5a744-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="5a744-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a744-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a744-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a744-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a744-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5a744-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a744-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a744-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a744-112">Attributes</span></span>  
 <span data-ttu-id="5a744-113">Keine</span><span class="sxs-lookup"><span data-stu-id="5a744-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5a744-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a744-114">Child Elements</span></span>  
  
|<span data-ttu-id="5a744-115">Element</span><span class="sxs-lookup"><span data-stu-id="5a744-115">Element</span></span>|<span data-ttu-id="5a744-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a744-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a744-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="5a744-117">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="5a744-118">Enthält eine Liste der Endpunkte, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="5a744-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="5a744-119">sein.</span><span class="sxs-lookup"><span data-stu-id="5a744-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a744-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a744-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5a744-121">Element</span><span class="sxs-lookup"><span data-stu-id="5a744-121">Element</span></span>|<span data-ttu-id="5a744-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a744-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a744-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="5a744-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="5a744-124">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> verwendet werden, bei der Auswertung eingehender Nachrichten sowie das routing, Tabellen, die die zielendpunkten, definieren Senden von Nachrichten bei filterübereinstimmung.</span><span class="sxs-lookup"><span data-stu-id="5a744-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a744-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a744-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
