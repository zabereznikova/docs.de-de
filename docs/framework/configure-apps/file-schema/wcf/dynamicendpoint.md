---
title: '&lt;dynamicEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: dcb52143c874b14c9241940f9b326a07b3fa6a82
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540250"
---
# <a name="ltdynamicendpointgt"></a><span data-ttu-id="404a1-102">&lt;dynamicEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="404a1-102">&lt;dynamicEndpoint&gt;</span></span>
<span data-ttu-id="404a1-103">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="404a1-103">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="404a1-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="404a1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="404a1-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="404a1-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="404a1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="404a1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="404a1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="404a1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="404a1-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="404a1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="404a1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="404a1-109">Attributes</span></span>  
 <span data-ttu-id="404a1-110">Keine</span><span class="sxs-lookup"><span data-stu-id="404a1-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="404a1-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="404a1-111">Child Elements</span></span>  
  
|<span data-ttu-id="404a1-112">Element</span><span class="sxs-lookup"><span data-stu-id="404a1-112">Element</span></span>|<span data-ttu-id="404a1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404a1-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="404a1-114">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="404a1-114">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="404a1-115">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="404a1-115">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="404a1-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="404a1-116">Parent Elements</span></span>  
  
|<span data-ttu-id="404a1-117">Element</span><span class="sxs-lookup"><span data-stu-id="404a1-117">Element</span></span>|<span data-ttu-id="404a1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="404a1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="404a1-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="404a1-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="404a1-120">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="404a1-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="404a1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="404a1-121">See also</span></span>
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
