---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855166"
---
# \<findCriteria>
<span data-ttu-id="8d411-101">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d411-101">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="8d411-102">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden) und Beendigungskriterien für die Suche (wie lange soll die Suche dauern) gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="8d411-102">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a><span data-ttu-id="8d411-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d411-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8d411-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8d411-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8d411-105">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d411-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8d411-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="8d411-106">Attributes</span></span>  
  
|<span data-ttu-id="8d411-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8d411-107">Attribute</span></span>|<span data-ttu-id="8d411-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8d411-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8d411-109">duration</span><span class="sxs-lookup"><span data-stu-id="8d411-109">duration</span></span>|<span data-ttu-id="8d411-110">Ein Timespan-Wert, der die maximale Zeit angibt, die auf Antworten von Diensten im Netzwerk gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="8d411-110">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="8d411-111">Der Standardzeitraum beträgt 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="8d411-111">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="8d411-112">maxResults</span><span class="sxs-lookup"><span data-stu-id="8d411-112">maxResults</span></span>|<span data-ttu-id="8d411-113">Eine ganze Zahl, die die maximale Anzahl an Antworten angibt, auf die von Diensten in einem Netzwerk oder im Internet gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="8d411-113">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="8d411-114">Wenn die maximale Anzahl erreicht wird, bevor der mit dem `duration`-Attribut festgelegte Zeitraum verstrichen ist, wird der Suchvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="8d411-114">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="8d411-115">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="8d411-115">scopeMatchBy</span></span>|<span data-ttu-id="8d411-116">Ein URI, der angibt, welcher Übereinstimmungsalgorithmus verwendet werden soll, während die Übereinstimmung der Bereiche der Probe-Nachricht mit denen des Endpunkts ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="8d411-116">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="8d411-117">Es gibt fünf unterstützte Bereichsübereinstimmungsregeln.</span><span class="sxs-lookup"><span data-stu-id="8d411-117">There are five supported scope-matching rules.</span></span> <span data-ttu-id="8d411-118">Wenn keine Bereichsübereinstimmungsregel angegeben wird, wird `ScopeMatchByPrefix` verwendet.</span><span class="sxs-lookup"><span data-stu-id="8d411-118">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="8d411-119">Weitere Informationen hierzu finden Sie unter <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="8d411-119">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8d411-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d411-120">Child Elements</span></span>  
  
|<span data-ttu-id="8d411-121">Element</span><span class="sxs-lookup"><span data-stu-id="8d411-121">Element</span></span>|<span data-ttu-id="8d411-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d411-122">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="8d411-123">Eine Auflistung von Konfigurationselementen, die die Namen von Workflow Dienst-Vertragstypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8d411-123">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="8d411-124">\<extensions> von \<findCriteria></span><span class="sxs-lookup"><span data-stu-id="8d411-124">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="8d411-125">Eine Auflistung von XML-Elementobjekten, die Erweiterungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8d411-125">A collection of XML element objects that provide extensions.</span></span>|  
|[\<scopes>](scopes.md)|<span data-ttu-id="8d411-126">Eine Auflistung von Objekten, die absolute URIs enthalten, die während eines Suchvorgangs verwendet werden, um einen bestimmten Dienst oder bestimmte Dienste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8d411-126">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="8d411-127">Wenn der bestimmte Dienst gefunden wird, wurde eine erfolgreiche Übereinstimmung zwischen dem Dienst- und Bereichs-URI hergestellt. Dies geschieht mitunter mittels Bereichsregeln, die Probleme beim Abgleichen behandeln.</span><span class="sxs-lookup"><span data-stu-id="8d411-127">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8d411-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8d411-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8d411-129">Element</span><span class="sxs-lookup"><span data-stu-id="8d411-129">Element</span></span>|<span data-ttu-id="8d411-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8d411-130">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="8d411-131">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8d411-131">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8d411-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d411-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
