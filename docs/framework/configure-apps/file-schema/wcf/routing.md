---
title: '&lt;Routing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed2dd4e68584d6e79e18fc9b61fcc8f078615dac
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt"></a><span data-ttu-id="d3795-102">&lt;Routing&gt;</span><span class="sxs-lookup"><span data-stu-id="d3795-102">&lt;routing&gt;</span></span>

<span data-ttu-id="d3795-103">Stellt einen Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern dar, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie zum Definieren von Routingtabellen mit den Zielendpunkten, an die Nachrichten bei Filterübereinstimmung gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d3795-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="d3795-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="d3795-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="d3795-105">&nbsp;&nbsp;**\<Routing >**</span><span class="sxs-lookup"><span data-stu-id="d3795-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d3795-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3795-106">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d3795-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3795-107">Attributes and elements</span></span>

<span data-ttu-id="d3795-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3795-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3795-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3795-109">Attributes</span></span>

<span data-ttu-id="d3795-110">Keine</span><span class="sxs-lookup"><span data-stu-id="d3795-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="d3795-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3795-111">Child elements</span></span>

|     | <span data-ttu-id="d3795-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3795-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d3795-113">**\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="d3795-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="d3795-114">Enthält einen Satz von Routingfiltern, die den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter bestimmen, der zum Auswerten eingehender Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3795-114">Contains a set of routing filters that determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="d3795-115">**\<FilterTables >**</span><span class="sxs-lookup"><span data-stu-id="d3795-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="d3795-116">Enthält Zuordnungen zwischen den Routingfiltern und den Zielendpunkten, die angeben, welcher Endpunkt bei Filterübereinstimmung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3795-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="d3795-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3795-117">Parent elements</span></span>

|     | <span data-ttu-id="d3795-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3795-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="d3795-119">**\<System. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="d3795-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="d3795-120">Das Stammelement aller WCF-Konfigurationselemente.</span><span class="sxs-lookup"><span data-stu-id="d3795-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d3795-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3795-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
