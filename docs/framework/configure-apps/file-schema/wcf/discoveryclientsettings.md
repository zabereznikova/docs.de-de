---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855416"
---
# <a name="discoveryclientsettings"></a><span data-ttu-id="db5d8-101">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="db5d8-101">\<discoveryClientSettings></span></span>
<span data-ttu-id="db5d8-102">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="db5d8-102">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="db5d8-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="db5d8-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="db5d8-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="db5d8-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="db5d8-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="db5d8-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="db5d8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<DynamicEndpoint->** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="db5d8-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="db5d8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardendpoint->** </span><span class="sxs-lookup"><span data-stu-id="db5d8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="db5d8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<discoveryclientsettings->**</span><span class="sxs-lookup"><span data-stu-id="db5d8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db5d8-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="db5d8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db5d8-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db5d8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db5d8-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db5d8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db5d8-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="db5d8-112">Attributes</span></span>  
  
|<span data-ttu-id="db5d8-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="db5d8-113">Attribute</span></span>|<span data-ttu-id="db5d8-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db5d8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db5d8-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="db5d8-115">discoveryEndpoint</span></span>|<span data-ttu-id="db5d8-116">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="db5d8-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db5d8-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db5d8-117">Child Elements</span></span>  
  
|<span data-ttu-id="db5d8-118">Element</span><span class="sxs-lookup"><span data-stu-id="db5d8-118">Element</span></span>|<span data-ttu-id="db5d8-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db5d8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db5d8-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="db5d8-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="db5d8-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="db5d8-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="db5d8-122">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="db5d8-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db5d8-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db5d8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="db5d8-124">Element</span><span class="sxs-lookup"><span data-stu-id="db5d8-124">Element</span></span>|<span data-ttu-id="db5d8-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db5d8-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db5d8-126">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="db5d8-126">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="db5d8-127">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="db5d8-127">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db5d8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db5d8-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
