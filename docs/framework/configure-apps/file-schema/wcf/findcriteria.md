---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855166"
---
# <a name="findcriteria"></a><span data-ttu-id="39b7a-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="39b7a-101">\<findCriteria></span></span>
<span data-ttu-id="39b7a-102">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39b7a-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="39b7a-103">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="39b7a-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
<span data-ttu-id="39b7a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39b7a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39b7a-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39b7a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39b7a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="39b7a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="39b7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DynamicEndpoint->** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="39b7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="39b7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardendpoint->** </span><span class="sxs-lookup"><span data-stu-id="39b7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="39b7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryclientsettings->** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="39b7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="39b7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<FindCriteria->**</span><span class="sxs-lookup"><span data-stu-id="39b7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39b7a-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="39b7a-111">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39b7a-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39b7a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="39b7a-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39b7a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39b7a-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="39b7a-114">Attributes</span></span>  
  
|<span data-ttu-id="39b7a-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="39b7a-115">Attribute</span></span>|<span data-ttu-id="39b7a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b7a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39b7a-117">duration</span><span class="sxs-lookup"><span data-stu-id="39b7a-117">duration</span></span>|<span data-ttu-id="39b7a-118">Ein Timespan-Wert, der die maximale Zeit angibt, die auf Antworten von Diensten im Netzwerk gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="39b7a-118">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="39b7a-119">Der Standardzeitraum beträgt 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="39b7a-119">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="39b7a-120">maxResults</span><span class="sxs-lookup"><span data-stu-id="39b7a-120">maxResults</span></span>|<span data-ttu-id="39b7a-121">Eine ganze Zahl, die die maximale Anzahl an Antworten angibt, auf die von Diensten in einem Netzwerk oder im Internet gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="39b7a-121">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="39b7a-122">Wenn die maximale Anzahl erreicht wird, bevor der mit dem `duration`-Attribut festgelegte Zeitraum verstrichen ist, wird der Suchvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="39b7a-122">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="39b7a-123">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="39b7a-123">scopeMatchBy</span></span>|<span data-ttu-id="39b7a-124">Ein URI, der angibt, welcher Übereinstimmungsalgorithmus verwendet werden soll, während die Übereinstimmung der Bereiche der Probe-Nachricht mit denen des Endpunkts ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="39b7a-124">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="39b7a-125">Es gibt fünf unterstützte Bereichsübereinstimmungsregeln.</span><span class="sxs-lookup"><span data-stu-id="39b7a-125">There are five supported scope-matching rules.</span></span> <span data-ttu-id="39b7a-126">Wenn keine Bereichsübereinstimmungsregel angegeben wird, wird `ScopeMatchByPrefix` verwendet.</span><span class="sxs-lookup"><span data-stu-id="39b7a-126">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="39b7a-127">Weitere Informationen hierzu finden Sie unter <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="39b7a-127">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39b7a-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39b7a-128">Child Elements</span></span>  
  
|<span data-ttu-id="39b7a-129">Element</span><span class="sxs-lookup"><span data-stu-id="39b7a-129">Element</span></span>|<span data-ttu-id="39b7a-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b7a-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39b7a-131">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="39b7a-131">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="39b7a-132">Eine Auflistung von Konfigurationselementen, die die Namen von Workflow Dienst-Vertragstypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="39b7a-132">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="39b7a-133">\<Erweiterungen > von \<FindCriteria ></span><span class="sxs-lookup"><span data-stu-id="39b7a-133">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="39b7a-134">Eine Auflistung von XML-Elementobjekten, die Erweiterungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="39b7a-134">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="39b7a-135">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="39b7a-135">\<scopes></span></span>](scopes.md)|<span data-ttu-id="39b7a-136">Eine Auflistung von Objekten, die absolute URIs enthalten, die während eines Suchvorgangs verwendet werden, um einen bestimmten Dienst oder bestimmte Dienste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="39b7a-136">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="39b7a-137">Wenn der bestimmte Dienst gefunden wird, wurde eine erfolgreiche Übereinstimmung zwischen dem Dienst- und Bereichs-URI hergestellt. Dies geschieht mitunter mittels Bereichsregeln, die Probleme beim Abgleichen behandeln.</span><span class="sxs-lookup"><span data-stu-id="39b7a-137">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39b7a-138">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39b7a-138">Parent Elements</span></span>  
  
|<span data-ttu-id="39b7a-139">Element</span><span class="sxs-lookup"><span data-stu-id="39b7a-139">Element</span></span>|<span data-ttu-id="39b7a-140">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39b7a-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39b7a-141">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="39b7a-141">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="39b7a-142">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="39b7a-142">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39b7a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39b7a-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
