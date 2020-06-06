---
title: <add> von <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398304"
---
# <a name="add-of-scopes"></a><span data-ttu-id="88658-102">\<add> von \<scopes></span><span class="sxs-lookup"><span data-stu-id="88658-102">\<add> of \<scopes></span></span>
<span data-ttu-id="88658-103">Fügt einen benutzerdefinierten Bereichs-URI hinzu, der verwendet werden kann, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="88658-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="88658-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="88658-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88658-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="88658-105">Attributes and Elements</span></span>  
 <span data-ttu-id="88658-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="88658-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88658-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="88658-107">Attributes</span></span>  
  
|<span data-ttu-id="88658-108">attribute</span><span class="sxs-lookup"><span data-stu-id="88658-108">Attribute</span></span>|<span data-ttu-id="88658-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="88658-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88658-110">scope</span><span class="sxs-lookup"><span data-stu-id="88658-110">scope</span></span>|<span data-ttu-id="88658-111">Ein URI, der Bereichsinformationen für den Endpunkt enthält, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="88658-111">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88658-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="88658-112">Child Elements</span></span>  
 <span data-ttu-id="88658-113">Keine</span><span class="sxs-lookup"><span data-stu-id="88658-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88658-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="88658-114">Parent Elements</span></span>  
  
|<span data-ttu-id="88658-115">Element</span><span class="sxs-lookup"><span data-stu-id="88658-115">Element</span></span>|<span data-ttu-id="88658-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="88658-116">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="88658-117">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="88658-117">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="88658-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88658-118">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
