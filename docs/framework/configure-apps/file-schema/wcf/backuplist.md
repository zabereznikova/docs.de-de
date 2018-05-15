---
title: '&lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 6684dcc485ef1ee2c3e5501f2fbc43898e172958
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="6d95c-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="6d95c-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="6d95c-103">Stellt einen Konfigurationsabschnitt zum Definieren einer Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d95c-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="6d95c-104">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="6d95c-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="6d95c-105">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="6d95c-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="6d95c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6d95c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6d95c-107">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="6d95c-107">\<routing></span></span>  
<span data-ttu-id="6d95c-108">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="6d95c-108">\<backupLists></span></span>  
<span data-ttu-id="6d95c-109">\<BackupList ></span><span class="sxs-lookup"><span data-stu-id="6d95c-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d95c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d95c-110">Syntax</span></span>  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6d95c-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6d95c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6d95c-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d95c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d95c-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="6d95c-113">Attributes</span></span>  
  
|<span data-ttu-id="6d95c-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="6d95c-114">Attribute</span></span>|<span data-ttu-id="6d95c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d95c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d95c-116">Name</span><span class="sxs-lookup"><span data-stu-id="6d95c-116">name</span></span>|<span data-ttu-id="6d95c-117">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="6d95c-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d95c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d95c-118">Child Elements</span></span>  
  
|<span data-ttu-id="6d95c-119">Element</span><span class="sxs-lookup"><span data-stu-id="6d95c-119">Element</span></span>|<span data-ttu-id="6d95c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d95c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d95c-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="6d95c-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="6d95c-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d95c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6d95c-123">Element</span><span class="sxs-lookup"><span data-stu-id="6d95c-123">Element</span></span>|<span data-ttu-id="6d95c-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d95c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d95c-125">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="6d95c-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6d95c-126">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="6d95c-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d95c-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d95c-127">Remarks</span></span>  
 <span data-ttu-id="6d95c-128">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="6d95c-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="6d95c-129">Wenn ein Sendeversuch an den primären Endpunkt in aufgeführt der `endpointName` Attribut des [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) ein Fehler auftritt, mit einer kommunikationsausnahme, versucht der Routingdienst zum Senden der Nachricht an den ersten Endpunkt in diesem Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="6d95c-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="6d95c-130">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6d95c-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="6d95c-131">Im folgenden Beispiel wenn ein Sendeversuch an den primären Endpunkt mit dem Namen "Destination" eine kommunikationsausnahme zurückgibt versucht der Dienst zum Senden der Nachricht an die "AlternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="6d95c-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="6d95c-132">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="6d95c-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6d95c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d95c-133">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
