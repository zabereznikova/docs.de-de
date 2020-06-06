---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 929c5d170bfc27160e3e15b8bd2f9f26e0ed8975
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855416"
---
# \<discoveryClientSettings>
<span data-ttu-id="41043-101">Enthält die Einstellungen, die von einer Anwendung benötigt werden, um am Dienstermittlungsprozess als Client teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="41043-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="41043-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="41043-102">Syntax</span></span>  
  
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
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41043-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41043-103">Attributes and Elements</span></span>  
 <span data-ttu-id="41043-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41043-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41043-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="41043-105">Attributes</span></span>  
  
|<span data-ttu-id="41043-106">attribute</span><span class="sxs-lookup"><span data-stu-id="41043-106">Attribute</span></span>|<span data-ttu-id="41043-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="41043-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="41043-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="41043-108">discoveryEndpoint</span></span>|<span data-ttu-id="41043-109">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="41043-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41043-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41043-110">Child Elements</span></span>  
  
|<span data-ttu-id="41043-111">Element</span><span class="sxs-lookup"><span data-stu-id="41043-111">Element</span></span>|<span data-ttu-id="41043-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41043-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="41043-113">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="41043-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="41043-114">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden) und Beendigungskriterien für die Suche (wie lange soll die Suche dauern) gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="41043-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="41043-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41043-115">Parent Elements</span></span>  
  
|<span data-ttu-id="41043-116">Element</span><span class="sxs-lookup"><span data-stu-id="41043-116">Element</span></span>|<span data-ttu-id="41043-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41043-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="41043-118">Definiert einen Standardendpunkt, der Informationen enthält, mit denen eine Anwendung als Clientprogramm aktiviert wird, das die Endpunktadresse zur Laufzeit dynamisch suchen kann.</span><span class="sxs-lookup"><span data-stu-id="41043-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41043-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41043-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
