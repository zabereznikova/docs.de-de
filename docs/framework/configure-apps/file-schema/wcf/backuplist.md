---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850273"
---
# \<backupList>
<span data-ttu-id="375c5-101">Ein Konfigurationsabschnitt zur Definition einer Sicherungsliste mit einer Reihe von Endpunkten, die der Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="375c5-101">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="375c5-102">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="375c5-102">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="375c5-103">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="375c5-103">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**  
  
## <a name="syntax"></a><span data-ttu-id="375c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="375c5-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="375c5-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="375c5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="375c5-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="375c5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="375c5-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="375c5-107">Attributes</span></span>  
  
|<span data-ttu-id="375c5-108">attribute</span><span class="sxs-lookup"><span data-stu-id="375c5-108">Attribute</span></span>|<span data-ttu-id="375c5-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="375c5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="375c5-110">name</span><span class="sxs-lookup"><span data-stu-id="375c5-110">name</span></span>|<span data-ttu-id="375c5-111">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="375c5-111">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="375c5-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="375c5-112">Child Elements</span></span>  
  
|<span data-ttu-id="375c5-113">Element</span><span class="sxs-lookup"><span data-stu-id="375c5-113">Element</span></span>|<span data-ttu-id="375c5-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="375c5-114">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="375c5-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="375c5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="375c5-116">Element</span><span class="sxs-lookup"><span data-stu-id="375c5-116">Element</span></span>|<span data-ttu-id="375c5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="375c5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="375c5-118">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="375c5-118">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="375c5-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="375c5-119">Remarks</span></span>  
 <span data-ttu-id="375c5-120">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="375c5-120">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="375c5-121">Wenn das Senden an den primären Endpunkt, der im- `endpointName` Attribut von aufgeführt ist [\<add>](add-of-entries.md) , mit einer Kommunikations Ausnahme fehlschlägt, versucht der Routing Dienst, die Nachricht an den ersten Endpunkt in diesem Konfigurations Abschnitt zu senden.</span><span class="sxs-lookup"><span data-stu-id="375c5-121">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="375c5-122">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="375c5-122">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="375c5-123">Wenn im folgenden Beispiel ein Sendevorgang an den primären Endpunkt mit dem Namen "Destination" eine Kommunikations Ausnahme zurückgibt, versucht der Dienst, die Nachricht an die "Alternative Service Queue" zu senden.</span><span class="sxs-lookup"><span data-stu-id="375c5-123">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="375c5-124">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="375c5-124">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="375c5-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="375c5-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
