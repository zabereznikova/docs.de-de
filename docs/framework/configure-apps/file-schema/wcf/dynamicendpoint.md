---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 6f9cb127deb5651ed27a0ef5802512fb5b6c7b54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190097"
---
# \<dynamicEndpoint>

<span data-ttu-id="6e36d-101">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="6e36d-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="6e36d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e36d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e36d-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6e36d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6e36d-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6e36d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e36d-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="6e36d-105">Attributes</span></span>  

 <span data-ttu-id="6e36d-106">Keine</span><span class="sxs-lookup"><span data-stu-id="6e36d-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6e36d-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e36d-107">Child Elements</span></span>  
  
|<span data-ttu-id="6e36d-108">Element</span><span class="sxs-lookup"><span data-stu-id="6e36d-108">Element</span></span>|<span data-ttu-id="6e36d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e36d-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="6e36d-110">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6e36d-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e36d-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6e36d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="6e36d-112">Element</span><span class="sxs-lookup"><span data-stu-id="6e36d-112">Element</span></span>|<span data-ttu-id="6e36d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e36d-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="6e36d-114">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6e36d-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e36d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e36d-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
