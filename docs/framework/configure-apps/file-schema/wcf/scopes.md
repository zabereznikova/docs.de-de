---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: 57e9e19025db5e1fa588f073fdf30de09837a25d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399933"
---
# \<scopes>
<span data-ttu-id="fb97c-101">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="fb97c-101">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<scopes>**  
  
## <a name="syntax"></a><span data-ttu-id="fb97c-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb97c-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb97c-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fb97c-103">Attributes and Elements</span></span>  
 <span data-ttu-id="fb97c-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fb97c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb97c-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="fb97c-105">Attributes</span></span>  
 <span data-ttu-id="fb97c-106">Keine</span><span class="sxs-lookup"><span data-stu-id="fb97c-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fb97c-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb97c-107">Child Elements</span></span>  
  
|<span data-ttu-id="fb97c-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fb97c-108">Attribute</span></span>|<span data-ttu-id="fb97c-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb97c-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|<span data-ttu-id="fb97c-110">Fügt die Bereichsinformationen für den Endpunkt hinzu, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb97c-110">Adds the scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fb97c-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fb97c-111">Parent Elements</span></span>  
  
|<span data-ttu-id="fb97c-112">Element</span><span class="sxs-lookup"><span data-stu-id="fb97c-112">Element</span></span>|<span data-ttu-id="fb97c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb97c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|<span data-ttu-id="fb97c-114">Gibt die verschiedenen Ermittlungseinstellungen für einen Endpunkt an, z. B. seine Ermittelbarkeit, seine Bereiche und benutzerdefinierte Erweiterungen seiner Metadaten.</span><span class="sxs-lookup"><span data-stu-id="fb97c-114">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb97c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb97c-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
