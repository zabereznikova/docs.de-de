---
title: <add> von <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: bcde6b18c34dccf1716c809dddeb45b1b4da90f0
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398304"
---
# <a name="add-of-scopes"></a><span data-ttu-id="da684-102">\<Fügt > von \<Bereichen hinzu ></span><span class="sxs-lookup"><span data-stu-id="da684-102">\<add> of \<scopes></span></span>
<span data-ttu-id="da684-103">Fügt einen benutzerdefinierten Bereichs-URI hinzu, der verwendet werden kann, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="da684-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="da684-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da684-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da684-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="da684-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="da684-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="da684-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="da684-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointverhaltens->** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="da684-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="da684-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Verhaltens >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="da684-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="da684-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointdiscovery->** ](endpointdiscovery.md)</span><span class="sxs-lookup"><span data-stu-id="da684-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointDiscovery>**](endpointdiscovery.md)</span></span>\
<span data-ttu-id="da684-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bereiche >** ](scopes.md)</span><span class="sxs-lookup"><span data-stu-id="da684-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopes>**](scopes.md)</span></span>\
<span data-ttu-id="da684-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> Hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="da684-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da684-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="da684-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da684-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da684-113">Attributes and Elements</span></span>  
 <span data-ttu-id="da684-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da684-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da684-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="da684-115">Attributes</span></span>  
  
|<span data-ttu-id="da684-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="da684-116">Attribute</span></span>|<span data-ttu-id="da684-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da684-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da684-118">Gültigkeitsbereich</span><span class="sxs-lookup"><span data-stu-id="da684-118">scope</span></span>|<span data-ttu-id="da684-119">Ein URI, der Bereichsinformationen für den Endpunkt enthält, die zum Vergleichen von Kriterien bei der Dienstsuche verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="da684-119">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da684-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da684-120">Child Elements</span></span>  
 <span data-ttu-id="da684-121">Keine</span><span class="sxs-lookup"><span data-stu-id="da684-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da684-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da684-122">Parent Elements</span></span>  
  
|<span data-ttu-id="da684-123">Element</span><span class="sxs-lookup"><span data-stu-id="da684-123">Element</span></span>|<span data-ttu-id="da684-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da684-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da684-125">\<Bereiche ></span><span class="sxs-lookup"><span data-stu-id="da684-125">\<scopes></span></span>](scopes.md)|<span data-ttu-id="da684-126">Enthält eine Auflistung von Konfigurationselementen, die benutzerdefinierte Bereichs-URIs angeben, die verwendet werden können, um Dienstendpunkte während der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="da684-126">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da684-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da684-127">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
