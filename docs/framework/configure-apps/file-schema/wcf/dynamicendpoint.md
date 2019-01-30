---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 786a70e8c686497e91492938a4d0796db4f6dd91
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269795"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="da510-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="da510-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="da510-102">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="da510-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="da510-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da510-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="da510-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="da510-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da510-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="da510-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da510-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da510-106">Attributes and Elements</span></span>  
 <span data-ttu-id="da510-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da510-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da510-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="da510-108">Attributes</span></span>  
 <span data-ttu-id="da510-109">Keine</span><span class="sxs-lookup"><span data-stu-id="da510-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da510-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da510-110">Child Elements</span></span>  
  
|<span data-ttu-id="da510-111">Element</span><span class="sxs-lookup"><span data-stu-id="da510-111">Element</span></span>|<span data-ttu-id="da510-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da510-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da510-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="da510-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="da510-114">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="da510-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da510-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da510-115">Parent Elements</span></span>  
  
|<span data-ttu-id="da510-116">Element</span><span class="sxs-lookup"><span data-stu-id="da510-116">Element</span></span>|<span data-ttu-id="da510-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da510-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da510-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="da510-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="da510-119">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="da510-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da510-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da510-120">See also</span></span>
- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
