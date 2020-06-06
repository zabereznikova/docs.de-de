---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855345"
---
# \<dynamicEndpoint>
<span data-ttu-id="d4d7a-101">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="d4d7a-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="d4d7a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4d7a-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4d7a-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d4d7a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d4d7a-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d4d7a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4d7a-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4d7a-105">Attributes</span></span>  
 <span data-ttu-id="d4d7a-106">Keine</span><span class="sxs-lookup"><span data-stu-id="d4d7a-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d4d7a-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4d7a-107">Child Elements</span></span>  
  
|<span data-ttu-id="d4d7a-108">Element</span><span class="sxs-lookup"><span data-stu-id="d4d7a-108">Element</span></span>|<span data-ttu-id="d4d7a-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d4d7a-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="d4d7a-110">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="d4d7a-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d4d7a-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4d7a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="d4d7a-112">Element</span><span class="sxs-lookup"><span data-stu-id="d4d7a-112">Element</span></span>|<span data-ttu-id="d4d7a-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d4d7a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="d4d7a-114">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="d4d7a-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4d7a-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4d7a-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
