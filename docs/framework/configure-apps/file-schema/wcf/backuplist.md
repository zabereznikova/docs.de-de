---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850273"
---
# <a name="backuplist"></a><span data-ttu-id="516b8-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="516b8-101">\<backupList></span></span>
<span data-ttu-id="516b8-102">Stellt einen Konfigurations Abschnitt zum Definieren einer Sicherungsliste dar, die eine Gruppe von Endpunkten auflistet, die der Routing Dienst verwenden soll, falls der primäre Endpunkt nicht erreicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="516b8-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="516b8-103">Wenn der erste Endpunkt in der Liste ausgefallen ist, führt der Routingdienst automatisch ein Failover zum nächsten Endpunkt in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="516b8-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="516b8-104">So können Sie die Zuverlässigkeit einer Anwendung schnell verbessern, wobei die Clientanwendung weder komplexe Muster behandeln noch den Bereitstellungsort aller Dienste kennen muss.</span><span class="sxs-lookup"><span data-stu-id="516b8-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="516b8-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="516b8-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="516b8-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="516b8-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="516b8-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="516b8-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="516b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backuplists->** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="516b8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="516b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<backuplist->**</span><span class="sxs-lookup"><span data-stu-id="516b8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="516b8-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="516b8-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="516b8-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="516b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="516b8-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="516b8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="516b8-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="516b8-113">Attributes</span></span>  
  
|<span data-ttu-id="516b8-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="516b8-114">Attribute</span></span>|<span data-ttu-id="516b8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="516b8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="516b8-116">NAME</span><span class="sxs-lookup"><span data-stu-id="516b8-116">name</span></span>|<span data-ttu-id="516b8-117">Eine Zeichenfolge, die den Namen der Endpunktliste angibt.</span><span class="sxs-lookup"><span data-stu-id="516b8-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="516b8-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="516b8-118">Child Elements</span></span>  
  
|<span data-ttu-id="516b8-119">Element</span><span class="sxs-lookup"><span data-stu-id="516b8-119">Element</span></span>|<span data-ttu-id="516b8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="516b8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="516b8-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="516b8-121">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="516b8-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="516b8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="516b8-123">Element</span><span class="sxs-lookup"><span data-stu-id="516b8-123">Element</span></span>|<span data-ttu-id="516b8-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="516b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="516b8-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="516b8-125">\<routing></span></span>](routing.md)|<span data-ttu-id="516b8-126">Eine Liste mit Sicherungsendpunkten.</span><span class="sxs-lookup"><span data-stu-id="516b8-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="516b8-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="516b8-127">Remarks</span></span>  
 <span data-ttu-id="516b8-128">Dieser Abschnitt enthält eine sortierte Auflistung von Endpunkten, an die eine Nachricht gesendet wird, wenn beim Senden an den primären Endpunkt eine Kommunikationsausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="516b8-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="516b8-129">Wenn ein Sendevorgang an den primären Endpunkt, der `endpointName` im-Attribut von [ \<Add >](add-of-entries.md) aufgeführt ist, mit einer Kommunikations Ausnahme fehlschlägt, versucht der Routing Dienst, die Nachricht an den ersten Endpunkt in diesem Konfigurations Abschnitt zu senden.</span><span class="sxs-lookup"><span data-stu-id="516b8-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="516b8-130">Wenn auch dies mit einer Kommunikationsausnahme scheitert, versucht der Routingdienst so lange, die Nachricht an den nächsten Endpunkt in diesem Abschnitt zu senden, bis entweder der Sendeversuch erfolgreich ist, ein anderer Fehler als eine Kommunikationsausnahme zurückgegeben wird oder alle Endpunkte in der Auflistung einen Fehler zurückgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="516b8-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="516b8-131">Wenn im folgenden Beispiel ein Sendevorgang an den primären Endpunkt mit dem Namen "Destination" eine Kommunikations Ausnahme zurückgibt, versucht der Dienst, die Nachricht an die "Alternative Service Queue" zu senden.</span><span class="sxs-lookup"><span data-stu-id="516b8-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="516b8-132">Wenn auch dieser Versuch eine Kommunikationsausnahme zurückgibt, versucht der Routingdienst, die Meldung an den nächsten Endpunkt in der Auflistung zu senden.</span><span class="sxs-lookup"><span data-stu-id="516b8-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="516b8-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="516b8-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
