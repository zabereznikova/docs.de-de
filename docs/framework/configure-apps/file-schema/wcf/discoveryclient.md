---
title: <discoveryClient>
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: af9cf127652f1e12ae57948f9b4a6a26285af793
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192255"
---
# \<discoveryClient>

<span data-ttu-id="0ef56-101">Ein Konfigurationselement zum Erstellen einer benutzerdefinierten Bindung, mit der eine Clientanwendung automatisch nach einem sichtbaren Workflowdienst suchen und zur Laufzeit dessen Adresse abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="0ef56-101">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClient>**  
  
## <a name="syntax"></a><span data-ttu-id="0ef56-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ef56-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ef56-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0ef56-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0ef56-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0ef56-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ef56-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="0ef56-105">Attributes</span></span>  
  
|<span data-ttu-id="0ef56-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0ef56-106">Attribute</span></span>|<span data-ttu-id="0ef56-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ef56-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ef56-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="0ef56-108">discoveryEndpoint</span></span>|<span data-ttu-id="0ef56-109">Eine Zeichenfolge mit dem Namen des Ermittlungsendpunkts, der einer Clientanwendung ermöglicht, automatisch nach einem sichtbaren Dienst zu suchen und zur Laufzeit dessen Adresse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0ef56-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ef56-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ef56-110">Child Elements</span></span>  
  
|<span data-ttu-id="0ef56-111">Element</span><span class="sxs-lookup"><span data-stu-id="0ef56-111">Element</span></span>|<span data-ttu-id="0ef56-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ef56-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="0ef56-113">Ein Konfigurationselement, das einen Kriteriensatz bereitstellt, der von einer Clientanwendung zum Suchen nach einem Ermittlungsdienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0ef56-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="0ef56-114">Kriterien können in Suchkriterien (nach welchen Diensten soll gesucht werden) und Beendigungskriterien für die Suche (wie lange soll die Suche dauern) gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="0ef56-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ef56-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0ef56-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0ef56-116">Element</span><span class="sxs-lookup"><span data-stu-id="0ef56-116">Element</span></span>|<span data-ttu-id="0ef56-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0ef56-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0ef56-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="0ef56-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ef56-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ef56-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
