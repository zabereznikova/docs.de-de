---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 2783796166d56be3d4983ab09a60d62491699fe3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925865"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="bffda-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="bffda-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="bffda-102">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="bffda-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="bffda-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bffda-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="bffda-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bffda-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bffda-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bffda-105">Syntax</span></span>  
  
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
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bffda-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bffda-106">Attributes and Elements</span></span>  
 <span data-ttu-id="bffda-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bffda-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bffda-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="bffda-108">Attributes</span></span>  
  
|<span data-ttu-id="bffda-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="bffda-109">Attribute</span></span>|<span data-ttu-id="bffda-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bffda-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bffda-111">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="bffda-111">discoveryEndpoint</span></span>|<span data-ttu-id="bffda-112">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bffda-112">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bffda-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bffda-113">Child Elements</span></span>  
  
|<span data-ttu-id="bffda-114">Element</span><span class="sxs-lookup"><span data-stu-id="bffda-114">Element</span></span>|<span data-ttu-id="bffda-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bffda-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bffda-116">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bffda-116">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="bffda-117">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bffda-117">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="bffda-118">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="bffda-118">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bffda-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bffda-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bffda-120">Element</span><span class="sxs-lookup"><span data-stu-id="bffda-120">Element</span></span>|<span data-ttu-id="bffda-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bffda-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bffda-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="bffda-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="bffda-123">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="bffda-123">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bffda-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bffda-124">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
