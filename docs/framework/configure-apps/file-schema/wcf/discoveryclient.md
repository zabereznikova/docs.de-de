---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 71305720cad0206ec3dabb1863e2f1cd72eb85f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739034"
---
# \<discoveryClient>
<span data-ttu-id="25e1a-101">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="25e1a-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="25e1a-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="25e1a-102">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String">
  <findCriteria duration="TimeSpan"
                maxResults="Integer"
                scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String"
           namespace="String" />
    </contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25e1a-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25e1a-103">Attributes and Elements</span></span>  
 <span data-ttu-id="25e1a-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25e1a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25e1a-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="25e1a-105">Attributes</span></span>  
  
|<span data-ttu-id="25e1a-106">attribute</span><span class="sxs-lookup"><span data-stu-id="25e1a-106">Attribute</span></span>|<span data-ttu-id="25e1a-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="25e1a-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25e1a-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="25e1a-108">discoveryEndpoint</span></span>|<span data-ttu-id="25e1a-109">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="25e1a-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25e1a-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25e1a-110">Child Elements</span></span>  
  
|<span data-ttu-id="25e1a-111">Element</span><span class="sxs-lookup"><span data-stu-id="25e1a-111">Element</span></span>|<span data-ttu-id="25e1a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25e1a-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="25e1a-113">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25e1a-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="25e1a-114">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden) und Beendigungskriterien für die Suche (wie lange soll die Suche dauern) gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="25e1a-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25e1a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25e1a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="25e1a-116">Element</span><span class="sxs-lookup"><span data-stu-id="25e1a-116">Element</span></span>|<span data-ttu-id="25e1a-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25e1a-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="25e1a-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="25e1a-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25e1a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25e1a-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
