---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 215bc9d8540b2d782a0c63f2f5be96f6fcde6812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="66d54-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="66d54-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="66d54-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="66d54-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="66d54-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="66d54-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="66d54-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="66d54-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66d54-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="66d54-106">Syntax</span></span>  
  
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
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66d54-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="66d54-107">Attributes and Elements</span></span>  
 <span data-ttu-id="66d54-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="66d54-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66d54-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="66d54-109">Attributes</span></span>  
 <span data-ttu-id="66d54-110">Keine</span><span class="sxs-lookup"><span data-stu-id="66d54-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66d54-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66d54-111">Child Elements</span></span>  
  
|<span data-ttu-id="66d54-112">Element</span><span class="sxs-lookup"><span data-stu-id="66d54-112">Element</span></span>|<span data-ttu-id="66d54-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66d54-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66d54-114">\<DiscoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="66d54-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="66d54-115">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="66d54-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66d54-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="66d54-116">Parent Elements</span></span>  
  
|<span data-ttu-id="66d54-117">Element</span><span class="sxs-lookup"><span data-stu-id="66d54-117">Element</span></span>|<span data-ttu-id="66d54-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66d54-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="66d54-119">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="66d54-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="66d54-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="66d54-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="66d54-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66d54-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
