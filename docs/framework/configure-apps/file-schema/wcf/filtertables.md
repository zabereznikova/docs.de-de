---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: faa26ca108010330475725f83dfd0c6668cfc6b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178202"
---
# \<filterTables>

<span data-ttu-id="efe0d-101">Stellt einen Konfigurationsabschnitt zum Definieren von Routingtabellen dar, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthalten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="efe0d-101">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**  
  
## <a name="syntax"></a><span data-ttu-id="efe0d-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="efe0d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efe0d-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="efe0d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="efe0d-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="efe0d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efe0d-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="efe0d-105">Attributes</span></span>  

 <span data-ttu-id="efe0d-106">Keine</span><span class="sxs-lookup"><span data-stu-id="efe0d-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="efe0d-107">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efe0d-107">Child Elements</span></span>  
  
|<span data-ttu-id="efe0d-108">Element</span><span class="sxs-lookup"><span data-stu-id="efe0d-108">Element</span></span>|<span data-ttu-id="efe0d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe0d-109">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="efe0d-110">Eine Routingtabelle, die Zuordnungen zwischen den Routingfiltern und den Zielendpunkten enthält, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="efe0d-110">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efe0d-111">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="efe0d-111">Parent Elements</span></span>  
  
|<span data-ttu-id="efe0d-112">Element</span><span class="sxs-lookup"><span data-stu-id="efe0d-112">Element</span></span>|<span data-ttu-id="efe0d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe0d-113">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="efe0d-114">Ein Konfigurationsabschnitt, der Routingfilter und Routingtabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="efe0d-114">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efe0d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efe0d-115">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
