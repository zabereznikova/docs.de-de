---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855278"
---
# \<entries>
<span data-ttu-id="78952-101">Ein Routingeintrag, der Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="78952-101">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**  
  
## <a name="syntax"></a><span data-ttu-id="78952-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="78952-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="78952-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="78952-103">Attributes and Elements</span></span>  
 <span data-ttu-id="78952-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="78952-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="78952-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="78952-105">Attributes</span></span>  
 <span data-ttu-id="78952-106">Keine</span><span class="sxs-lookup"><span data-stu-id="78952-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="78952-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78952-107">Child Elements</span></span>  
  
|<span data-ttu-id="78952-108">Element</span><span class="sxs-lookup"><span data-stu-id="78952-108">Element</span></span>|<span data-ttu-id="78952-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78952-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="78952-110">Ordnet einem Clientendpunkt, der zuvor definiert wurde, einen Filter zu.</span><span class="sxs-lookup"><span data-stu-id="78952-110">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="78952-111">Meldungen, die diesem Filter entsprechen, werden an dieses Ziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="78952-111">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="78952-112">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="78952-112">Parent Elements</span></span>  
  
|<span data-ttu-id="78952-113">Element</span><span class="sxs-lookup"><span data-stu-id="78952-113">Element</span></span>|<span data-ttu-id="78952-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="78952-114">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="78952-115">Ein Konfigurationsabschnitt, der eine Routingtabelle enthält.</span><span class="sxs-lookup"><span data-stu-id="78952-115">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78952-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78952-116">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
