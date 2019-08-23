---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eb8ff3905f7696f4c71a79e31db1b8f82c9f0d3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925587"
---
# <a name="findcriteria"></a><span data-ttu-id="d976b-101">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="d976b-101">\<findCriteria></span></span>
<span data-ttu-id="d976b-102">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d976b-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="d976b-103">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="d976b-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="d976b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d976b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d976b-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d976b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d976b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d976b-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d976b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d976b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d976b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d976b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d976b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d976b-109">Attributes</span></span>  
  
|<span data-ttu-id="d976b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="d976b-110">Attribute</span></span>|<span data-ttu-id="d976b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d976b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d976b-112">duration</span><span class="sxs-lookup"><span data-stu-id="d976b-112">duration</span></span>|<span data-ttu-id="d976b-113">Ein Timespan-Wert, der die maximale Zeit angibt, die auf Antworten von Diensten im Netzwerk gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="d976b-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="d976b-114">Der Standardzeitraum beträgt 20 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="d976b-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="d976b-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="d976b-115">maxResults</span></span>|<span data-ttu-id="d976b-116">Eine ganze Zahl, die die maximale Anzahl an Antworten angibt, auf die von Diensten in einem Netzwerk oder im Internet gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="d976b-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="d976b-117">Wenn die maximale Anzahl erreicht wird, bevor der mit dem `duration`-Attribut festgelegte Zeitraum verstrichen ist, wird der Suchvorgang beendet.</span><span class="sxs-lookup"><span data-stu-id="d976b-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="d976b-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="d976b-118">scopeMatchBy</span></span>|<span data-ttu-id="d976b-119">Ein URI, der angibt, welcher Übereinstimmungsalgorithmus verwendet werden soll, während die Übereinstimmung der Bereiche der Probe-Nachricht mit denen des Endpunkts ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="d976b-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="d976b-120">Es gibt fünf unterstützte Bereichsübereinstimmungsregeln.</span><span class="sxs-lookup"><span data-stu-id="d976b-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="d976b-121">Wenn keine Bereichsübereinstimmungsregel angegeben wird, wird `ScopeMatchByPrefix` verwendet.</span><span class="sxs-lookup"><span data-stu-id="d976b-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="d976b-122">Weitere Informationen hierzu finden Sie unter <xref:System.ServiceModel.Discovery.FindCriteria>.</span><span class="sxs-lookup"><span data-stu-id="d976b-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d976b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d976b-123">Child Elements</span></span>  
  
|<span data-ttu-id="d976b-124">Element</span><span class="sxs-lookup"><span data-stu-id="d976b-124">Element</span></span>|<span data-ttu-id="d976b-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d976b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d976b-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="d976b-126">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="d976b-127">Eine Auflistung von Konfigurationselementen, die die Namen von Workflow Dienst-Vertragstypen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d976b-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="d976b-128">\<Erweiterungen > von \<FindCriteria ></span><span class="sxs-lookup"><span data-stu-id="d976b-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="d976b-129">Eine Auflistung von XML-Elementobjekten, die Erweiterungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d976b-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="d976b-130">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="d976b-130">\<scopes></span></span>](scopes.md)|<span data-ttu-id="d976b-131">Eine Auflistung von Objekten, die absolute URIs enthalten, die während eines Suchvorgangs verwendet werden, um einen bestimmten Dienst oder bestimmte Dienste zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d976b-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="d976b-132">Wenn der bestimmte Dienst gefunden wird, wurde eine erfolgreiche Übereinstimmung zwischen dem Dienst- und Bereichs-URI hergestellt. Dies geschieht mitunter mittels Bereichsregeln, die Probleme beim Abgleichen behandeln.</span><span class="sxs-lookup"><span data-stu-id="d976b-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d976b-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d976b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="d976b-134">Element</span><span class="sxs-lookup"><span data-stu-id="d976b-134">Element</span></span>|<span data-ttu-id="d976b-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d976b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d976b-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="d976b-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="d976b-137">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d976b-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d976b-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d976b-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
