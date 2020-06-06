---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850258"
---
# \<backupLists>
<span data-ttu-id="16c4b-101">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Sicherungsdiensten dar, die in der Fehlerbehandlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16c4b-101">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="16c4b-102">Jedes untergeordnete Element ist eine Sicherungsliste mit einem Satz von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="16c4b-102">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="16c4b-103">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="16c4b-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="16c4b-104">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="16c4b-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a><span data-ttu-id="16c4b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="16c4b-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16c4b-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16c4b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="16c4b-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16c4b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16c4b-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="16c4b-108">Attributes</span></span>  
 <span data-ttu-id="16c4b-109">Keine</span><span class="sxs-lookup"><span data-stu-id="16c4b-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16c4b-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16c4b-110">Child Elements</span></span>  
  
|<span data-ttu-id="16c4b-111">Element</span><span class="sxs-lookup"><span data-stu-id="16c4b-111">Element</span></span>|<span data-ttu-id="16c4b-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16c4b-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)|<span data-ttu-id="16c4b-113">Enthält eine Reihe von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann. </span><span class="sxs-lookup"><span data-stu-id="16c4b-113">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="16c4b-114">.</span><span class="sxs-lookup"><span data-stu-id="16c4b-114">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16c4b-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16c4b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="16c4b-116">Element</span><span class="sxs-lookup"><span data-stu-id="16c4b-116">Element</span></span>|<span data-ttu-id="16c4b-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16c4b-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="16c4b-118">Stellt einen Konfigurations Abschnitt zum Definieren eines Satzes von Routing Filtern dar, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie Routing Tabellen, die die Ziel Endpunkte definieren, an die Nachrichten gesendet werden sollen, wenn ein Filter übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="16c4b-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16c4b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16c4b-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
