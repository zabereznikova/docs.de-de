---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739034"
---
# <a name="discoveryclient"></a><span data-ttu-id="8aeb7-101">\<DiscoveryClient ></span><span class="sxs-lookup"><span data-stu-id="8aeb7-101">\<discoveryClient></span></span>
<span data-ttu-id="8aeb7-102">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="8aeb7-102">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="8aeb7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8aeb7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8aeb7-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="8aeb7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8aeb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="8aeb7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="8aeb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8aeb7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="8aeb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="8aeb7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="8aeb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DiscoveryClient >**</span><span class="sxs-lookup"><span data-stu-id="8aeb7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aeb7-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="8aeb7-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8aeb7-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8aeb7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8aeb7-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8aeb7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8aeb7-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8aeb7-112">Attributes</span></span>  
  
|<span data-ttu-id="8aeb7-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="8aeb7-113">Attribute</span></span>|<span data-ttu-id="8aeb7-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8aeb7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8aeb7-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="8aeb7-115">discoveryEndpoint</span></span>|<span data-ttu-id="8aeb7-116">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8aeb7-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8aeb7-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8aeb7-117">Child Elements</span></span>  
  
|<span data-ttu-id="8aeb7-118">Element</span><span class="sxs-lookup"><span data-stu-id="8aeb7-118">Element</span></span>|<span data-ttu-id="8aeb7-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8aeb7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aeb7-120">\<standardendpoints ></span><span class="sxs-lookup"><span data-stu-id="8aeb7-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8aeb7-121">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeb7-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="8aeb7-122">Kriterien können in Suchkriterien gruppiert werden (wobei angegeben wird, welche Dienste Sie suchen) und nach Beendigungs Kriterien suchen (wie lange die Suche dauern sollte).</span><span class="sxs-lookup"><span data-stu-id="8aeb7-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8aeb7-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8aeb7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8aeb7-124">Element</span><span class="sxs-lookup"><span data-stu-id="8aeb7-124">Element</span></span>|<span data-ttu-id="8aeb7-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8aeb7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8aeb7-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="8aeb7-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="8aeb7-127">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="8aeb7-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8aeb7-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aeb7-128">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
