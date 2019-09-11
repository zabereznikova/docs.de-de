---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850258"
---
# <a name="backuplists"></a><span data-ttu-id="bb79d-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="bb79d-101">\<backupLists></span></span>
<span data-ttu-id="bb79d-102">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bb79d-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="bb79d-103">Jedes untergeordnete Element ist eine Sicherungsliste, die eine Reihe von Endpunkten auflistet, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb79d-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bb79d-104">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="bb79d-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="bb79d-105">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="bb79d-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="bb79d-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb79d-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bb79d-107">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bb79d-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bb79d-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="bb79d-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="bb79d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<backuplists->**</span><span class="sxs-lookup"><span data-stu-id="bb79d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb79d-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb79d-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb79d-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb79d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bb79d-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb79d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb79d-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb79d-113">Attributes</span></span>  
 <span data-ttu-id="bb79d-114">Keine</span><span class="sxs-lookup"><span data-stu-id="bb79d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bb79d-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb79d-115">Child Elements</span></span>  
  
|<span data-ttu-id="bb79d-116">Element</span><span class="sxs-lookup"><span data-stu-id="bb79d-116">Element</span></span>|<span data-ttu-id="bb79d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb79d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb79d-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="bb79d-118">\<filter></span></span>](filter.md)|<span data-ttu-id="bb79d-119">Enthält eine Liste von Endpunkten, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="bb79d-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="bb79d-120">.</span><span class="sxs-lookup"><span data-stu-id="bb79d-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bb79d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb79d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bb79d-122">Element</span><span class="sxs-lookup"><span data-stu-id="bb79d-122">Element</span></span>|<span data-ttu-id="bb79d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb79d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb79d-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="bb79d-124">\<routing></span></span>](routing.md)|<span data-ttu-id="bb79d-125">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren. Senden von Nachrichten an, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="bb79d-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb79d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb79d-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
