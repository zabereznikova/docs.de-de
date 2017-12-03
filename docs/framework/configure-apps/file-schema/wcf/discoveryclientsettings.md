---
title: '&lt;discoveryClientSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d5e7106de716e4f25e649dbbca716ef66dfa496
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiscoveryclientsettingsgt"></a><span data-ttu-id="b3e16-102">&lt;discoveryClientSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="b3e16-102">&lt;discoveryClientSettings&gt;</span></span>
<span data-ttu-id="b3e16-103">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="b3e16-103">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
<span data-ttu-id="b3e16-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b3e16-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3e16-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b3e16-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e16-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3e16-106">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3e16-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b3e16-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b3e16-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3e16-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3e16-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b3e16-109">Attributes</span></span>  
  
|<span data-ttu-id="b3e16-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="b3e16-110">Attribute</span></span>|<span data-ttu-id="b3e16-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3e16-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3e16-112">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="b3e16-112">discoveryEndpoint</span></span>|<span data-ttu-id="b3e16-113">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3e16-113">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3e16-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3e16-114">Child Elements</span></span>  
  
|<span data-ttu-id="b3e16-115">Element</span><span class="sxs-lookup"><span data-stu-id="b3e16-115">Element</span></span>|<span data-ttu-id="b3e16-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3e16-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3e16-117">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b3e16-117">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b3e16-118">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b3e16-118">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b3e16-119">Kriterien können in Suchkriterien (was Sie suchen Dienste) gruppiert werden und Beendigungskriterien (wie lange soll die Suche dauern).</span><span class="sxs-lookup"><span data-stu-id="b3e16-119">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3e16-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b3e16-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b3e16-121">Element</span><span class="sxs-lookup"><span data-stu-id="b3e16-121">Element</span></span>|<span data-ttu-id="b3e16-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3e16-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3e16-123">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="b3e16-123">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="b3e16-124">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="b3e16-124">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3e16-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3e16-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
