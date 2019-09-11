---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855345"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="8c777-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="8c777-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="8c777-102">Dieses Konfigurationselement definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="8c777-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="8c777-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c777-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8c777-104">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8c777-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8c777-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardendpoints->** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="8c777-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="8c777-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DynamicEndpoint->**</span><span class="sxs-lookup"><span data-stu-id="8c777-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c777-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c777-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c777-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c777-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c777-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c777-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c777-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c777-110">Attributes</span></span>  
 <span data-ttu-id="8c777-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8c777-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c777-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c777-112">Child Elements</span></span>  
  
|<span data-ttu-id="8c777-113">Element</span><span class="sxs-lookup"><span data-stu-id="8c777-113">Element</span></span>|<span data-ttu-id="8c777-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c777-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c777-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="8c777-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="8c777-116">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8c777-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8c777-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c777-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8c777-118">Element</span><span class="sxs-lookup"><span data-stu-id="8c777-118">Element</span></span>|<span data-ttu-id="8c777-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c777-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c777-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="8c777-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="8c777-121">Eine Auflistung von Standardendpunkten, bei denen es sich um vordefinierte Endpunkte handelt, für die eine oder mehrere Eigenschaften (Adresse, Bindung, Vertrag) fest vorgegeben sind.</span><span class="sxs-lookup"><span data-stu-id="8c777-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c777-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c777-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
