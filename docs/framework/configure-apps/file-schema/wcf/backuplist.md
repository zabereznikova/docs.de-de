---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: d5feab6cb374f98e683cf15f797de4f478e23131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919920"
---
# <a name="backuplist"></a><span data-ttu-id="9231d-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="9231d-101">\<backupList></span></span>
<span data-ttu-id="9231d-102">Stellt einen Konfigurations Abschnitt zum Definieren einer Sicherungsliste dar, die eine Gruppe von Endpunkten auflistet, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="9231d-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="9231d-103">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="9231d-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="9231d-104">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="9231d-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="9231d-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9231d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9231d-106">\<routing></span><span class="sxs-lookup"><span data-stu-id="9231d-106">\<routing></span></span>  
<span data-ttu-id="9231d-107">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="9231d-107">\<backupLists></span></span>  
<span data-ttu-id="9231d-108">\<backupList></span><span class="sxs-lookup"><span data-stu-id="9231d-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9231d-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="9231d-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9231d-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9231d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9231d-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9231d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9231d-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="9231d-112">Attributes</span></span>  
  
|<span data-ttu-id="9231d-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="9231d-113">Attribute</span></span>|<span data-ttu-id="9231d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9231d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9231d-115">Name</span><span class="sxs-lookup"><span data-stu-id="9231d-115">name</span></span>|<span data-ttu-id="9231d-116">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="9231d-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9231d-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9231d-117">Child Elements</span></span>  
  
|<span data-ttu-id="9231d-118">Element</span><span class="sxs-lookup"><span data-stu-id="9231d-118">Element</span></span>|<span data-ttu-id="9231d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9231d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9231d-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="9231d-120">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="9231d-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9231d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9231d-122">Element</span><span class="sxs-lookup"><span data-stu-id="9231d-122">Element</span></span>|<span data-ttu-id="9231d-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9231d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9231d-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="9231d-124">\<routing></span></span>](routing.md)|<span data-ttu-id="9231d-125">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="9231d-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9231d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9231d-126">Remarks</span></span>  
 <span data-ttu-id="9231d-127">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="9231d-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="9231d-128">Wenn ein Sendevorgang an den primären Endpunkt, der `endpointName` im-Attribut von [ \<Add >](add-of-entries.md) aufgeführt ist, mit einer Kommunikations Ausnahme fehlschlägt, versucht der Routing Dienst, die Nachricht an den ersten Endpunkt in diesem Konfigurations Abschnitt zu senden.</span><span class="sxs-lookup"><span data-stu-id="9231d-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="9231d-129">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="9231d-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="9231d-130">Wenn im folgenden Beispiel ein Sendevorgang an den primären Endpunkt mit dem Namen "Destination" eine Kommunikations Ausnahme zurückgibt, versucht der Dienst, die Nachricht an die "Alternative Service Queue" zu senden.</span><span class="sxs-lookup"><span data-stu-id="9231d-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="9231d-131">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="9231d-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9231d-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9231d-132">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
