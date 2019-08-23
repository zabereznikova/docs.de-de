---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 3dc7fb19c5c7729620a5d9f3df1111b2dbdacf78
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925837"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="642d5-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="642d5-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="642d5-102">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="642d5-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="642d5-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="642d5-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="642d5-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="642d5-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="642d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="642d5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="642d5-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="642d5-106">Attributes and Elements</span></span>  
 <span data-ttu-id="642d5-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="642d5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="642d5-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="642d5-108">Attributes</span></span>  
 <span data-ttu-id="642d5-109">Keine</span><span class="sxs-lookup"><span data-stu-id="642d5-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="642d5-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="642d5-110">Child Elements</span></span>  
  
|<span data-ttu-id="642d5-111">Element</span><span class="sxs-lookup"><span data-stu-id="642d5-111">Element</span></span>|<span data-ttu-id="642d5-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="642d5-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="642d5-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="642d5-113">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="642d5-114">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="642d5-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="642d5-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="642d5-115">Parent Elements</span></span>  
  
|<span data-ttu-id="642d5-116">Element</span><span class="sxs-lookup"><span data-stu-id="642d5-116">Element</span></span>|<span data-ttu-id="642d5-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="642d5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="642d5-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="642d5-118">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="642d5-119">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="642d5-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="642d5-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="642d5-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
