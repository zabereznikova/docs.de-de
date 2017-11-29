---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e24d340364f126d9cf33295d6d36d1b686065a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="eb450-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="eb450-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="eb450-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="eb450-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="eb450-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="eb450-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="eb450-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="eb450-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb450-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb450-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb450-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eb450-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eb450-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb450-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb450-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="eb450-109">Attributes</span></span>  
 <span data-ttu-id="eb450-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="eb450-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb450-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb450-111">Child Elements</span></span>  
  
|<span data-ttu-id="eb450-112">Element</span><span class="sxs-lookup"><span data-stu-id="eb450-112">Element</span></span>|<span data-ttu-id="eb450-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb450-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb450-114">\<DiscoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="eb450-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="eb450-115">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="eb450-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb450-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eb450-116">Parent Elements</span></span>  
  
|<span data-ttu-id="eb450-117">Element</span><span class="sxs-lookup"><span data-stu-id="eb450-117">Element</span></span>|<span data-ttu-id="eb450-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb450-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb450-119">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="eb450-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="eb450-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="eb450-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb450-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb450-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
