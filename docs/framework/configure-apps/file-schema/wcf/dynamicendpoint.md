---
title: '&lt;DynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 78ec2d4639161f8e10105f205576f052c8a5567c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146835"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="d56e7-102">&lt;DynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="d56e7-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="d56e7-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="d56e7-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="d56e7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d56e7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d56e7-105">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d56e7-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d56e7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d56e7-106">Syntax</span></span>  
  
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
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d56e7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d56e7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d56e7-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d56e7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d56e7-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d56e7-109">Attributes</span></span>  
 <span data-ttu-id="d56e7-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d56e7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d56e7-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d56e7-111">Child Elements</span></span>  
  
|<span data-ttu-id="d56e7-112">Element</span><span class="sxs-lookup"><span data-stu-id="d56e7-112">Element</span></span>|<span data-ttu-id="d56e7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d56e7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d56e7-114">\<DiscoveryClientSettings ></span><span class="sxs-lookup"><span data-stu-id="d56e7-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="d56e7-115">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d56e7-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d56e7-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d56e7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d56e7-117">Element</span><span class="sxs-lookup"><span data-stu-id="d56e7-117">Element</span></span>|<span data-ttu-id="d56e7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d56e7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d56e7-119">\<StandardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="d56e7-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="d56e7-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d56e7-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d56e7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d56e7-121">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
