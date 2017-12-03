---
title: '&lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8cb8f08c1d9c48aee9d3b42aadce0f65c8fe0585
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbackuplistgt"></a><span data-ttu-id="edf7f-102">&lt;backupList&gt;</span><span class="sxs-lookup"><span data-stu-id="edf7f-102">&lt;backupList&gt;</span></span>
<span data-ttu-id="edf7f-103">Stellt einen Konfigurationsabschnitt zum Definieren einer Sicherungsliste mit einem Satz von Endpunkten, die Sie möchten den Routingdienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="edf7f-103">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="edf7f-104">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="edf7f-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="edf7f-105">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="edf7f-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="edf7f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="edf7f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="edf7f-107">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="edf7f-107">\<routing></span></span>  
<span data-ttu-id="edf7f-108">\<BackupLists ></span><span class="sxs-lookup"><span data-stu-id="edf7f-108">\<backupLists></span></span>  
<span data-ttu-id="edf7f-109">\<BackupList ></span><span class="sxs-lookup"><span data-stu-id="edf7f-109">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edf7f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="edf7f-110">Syntax</span></span>  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="edf7f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="edf7f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="edf7f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="edf7f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edf7f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="edf7f-113">Attributes</span></span>  
  
|<span data-ttu-id="edf7f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="edf7f-114">Attribute</span></span>|<span data-ttu-id="edf7f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edf7f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edf7f-116">Name</span><span class="sxs-lookup"><span data-stu-id="edf7f-116">name</span></span>|<span data-ttu-id="edf7f-117">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edf7f-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edf7f-118">Child Elements</span></span>  
  
|<span data-ttu-id="edf7f-119">Element</span><span class="sxs-lookup"><span data-stu-id="edf7f-119">Element</span></span>|<span data-ttu-id="edf7f-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edf7f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edf7f-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="edf7f-121">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="edf7f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="edf7f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="edf7f-123">Element</span><span class="sxs-lookup"><span data-stu-id="edf7f-123">Element</span></span>|<span data-ttu-id="edf7f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="edf7f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edf7f-125">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="edf7f-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="edf7f-126">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="edf7f-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edf7f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edf7f-127">Remarks</span></span>  
 <span data-ttu-id="edf7f-128">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="edf7f-129">Wenn ein Sendeversuch an den primären Endpunkt in aufgeführt der `endpointName` Attribut des [ \<hinzufügen >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) ein Fehler auftritt, mit einer kommunikationsausnahme, versucht der Routingdienst zum Senden der Nachricht an den ersten Endpunkt in diesem Konfigurationsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="edf7f-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="edf7f-130">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="edf7f-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="edf7f-131">Im folgenden Beispiel wenn ein Sendeversuch an den primären Endpunkt mit dem Namen "Destination" eine kommunikationsausnahme zurückgibt versucht der Dienst zum Senden der Nachricht an die "AlternateServiceQueue".</span><span class="sxs-lookup"><span data-stu-id="edf7f-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="edf7f-132">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="edf7f-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edf7f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edf7f-133">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
