---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: b0a6c604b5741c1355c35fca510cd10544dab9f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135732"
---
# <a name="backuplist"></a><span data-ttu-id="75d3b-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="75d3b-101">\<backupList></span></span>
<span data-ttu-id="75d3b-102">Stellt einen Konfigurationsabschnitt zum Definieren einer Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="75d3b-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="75d3b-103">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="75d3b-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="75d3b-104">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="75d3b-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="75d3b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="75d3b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="75d3b-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="75d3b-106">\<routing></span></span>  
<span data-ttu-id="75d3b-107">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="75d3b-107">\<backupLists></span></span>  
<span data-ttu-id="75d3b-108">\<backupList></span><span class="sxs-lookup"><span data-stu-id="75d3b-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d3b-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="75d3b-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75d3b-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="75d3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="75d3b-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="75d3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75d3b-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="75d3b-112">Attributes</span></span>  
  
|<span data-ttu-id="75d3b-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="75d3b-113">Attribute</span></span>|<span data-ttu-id="75d3b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75d3b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75d3b-115">Name</span><span class="sxs-lookup"><span data-stu-id="75d3b-115">name</span></span>|<span data-ttu-id="75d3b-116">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="75d3b-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75d3b-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75d3b-117">Child Elements</span></span>  
  
|<span data-ttu-id="75d3b-118">Element</span><span class="sxs-lookup"><span data-stu-id="75d3b-118">Element</span></span>|<span data-ttu-id="75d3b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75d3b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75d3b-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="75d3b-120">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="75d3b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="75d3b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="75d3b-122">Element</span><span class="sxs-lookup"><span data-stu-id="75d3b-122">Element</span></span>|<span data-ttu-id="75d3b-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="75d3b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75d3b-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="75d3b-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="75d3b-125">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="75d3b-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75d3b-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="75d3b-126">Remarks</span></span>  
 <span data-ttu-id="75d3b-127">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="75d3b-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="75d3b-128">Wenn ein Senden an den primären Endpunkt im aufgeführt der `endpointName` Attribut [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) tritt der Fehler eine kommunikationsausnahme auftritt, versucht der Routingdienst zum Senden der Nachricht an den ersten Endpunkt in diesem Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="75d3b-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="75d3b-129">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="75d3b-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="75d3b-130">Im folgenden Beispiel wenn ein Senden an den primären Endpunkt mit dem Namen "Destination" eine kommunikationsausnahme zurückgibt versucht der Dienst zum Senden der Nachricht an die "AlternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="75d3b-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="75d3b-131">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="75d3b-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75d3b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75d3b-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
