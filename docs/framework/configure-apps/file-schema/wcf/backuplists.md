---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 940bf28958251e7257b2cc19a9c5ff0059411bcd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201550"
---
# \<backupLists>

<span data-ttu-id="2eada-101">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2eada-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="2eada-102">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="2eada-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="2eada-103">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2eada-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="2eada-104">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="2eada-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="2eada-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2eada-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2eada-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2eada-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2eada-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2eada-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2eada-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2eada-108">Attributes</span></span>  

 <span data-ttu-id="2eada-109">Keine</span><span class="sxs-lookup"><span data-stu-id="2eada-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2eada-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2eada-110">Child Elements</span></span>  
  
|<span data-ttu-id="2eada-111">Element</span><span class="sxs-lookup"><span data-stu-id="2eada-111">Element</span></span>|<span data-ttu-id="2eada-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eada-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="2eada-113">Enthält eine Reihe von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann. </span><span class="sxs-lookup"><span data-stu-id="2eada-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="2eada-114">.</span><span class="sxs-lookup"><span data-stu-id="2eada-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2eada-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2eada-115">Parent Elements</span></span>  
  
|<span data-ttu-id="2eada-116">Element</span><span class="sxs-lookup"><span data-stu-id="2eada-116">Element</span></span>|<span data-ttu-id="2eada-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eada-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="2eada-118">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="2eada-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2eada-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2eada-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
