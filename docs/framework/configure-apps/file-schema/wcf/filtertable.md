---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: fb36feedc5fb2cbdf3827cbe44242c7ac6ab8a9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185690"
---
# \<filterTable>

<span data-ttu-id="eaffd-101">Stellt eine Routingtabelle dar, die eine Liste mit Nachrichtenfiltern sowie den Clientendpunkt enthält, an den Nachrichten bei Filterübereinstimmung weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eaffd-101">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a><span data-ttu-id="eaffd-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="eaffd-102">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaffd-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="eaffd-103">Attributes and Elements</span></span>  

 <span data-ttu-id="eaffd-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="eaffd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaffd-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="eaffd-105">Attributes</span></span>  
  
|<span data-ttu-id="eaffd-106">Element</span><span class="sxs-lookup"><span data-stu-id="eaffd-106">Element</span></span>|<span data-ttu-id="eaffd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaffd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eaffd-108">name</span><span class="sxs-lookup"><span data-stu-id="eaffd-108">name</span></span>|<span data-ttu-id="eaffd-109">Eine Zeichenfolge, die den eindeutigen Namen dieses Konfigurationselements enthält.</span><span class="sxs-lookup"><span data-stu-id="eaffd-109">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaffd-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eaffd-110">Child Elements</span></span>  
  
|<span data-ttu-id="eaffd-111">Element</span><span class="sxs-lookup"><span data-stu-id="eaffd-111">Element</span></span>|<span data-ttu-id="eaffd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaffd-112">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="eaffd-113">Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, an die bei Filterübereinstimmung Nachrichten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eaffd-113">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eaffd-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="eaffd-114">Parent Elements</span></span>  
  
|<span data-ttu-id="eaffd-115">Element</span><span class="sxs-lookup"><span data-stu-id="eaffd-115">Element</span></span>|<span data-ttu-id="eaffd-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eaffd-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="eaffd-117">Ein Konfigurationsabschnitt mit Routingtabellen.</span><span class="sxs-lookup"><span data-stu-id="eaffd-117">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eaffd-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eaffd-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
