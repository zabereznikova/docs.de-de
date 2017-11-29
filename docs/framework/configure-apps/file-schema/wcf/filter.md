---
title: '&lt;Filter&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86ae428eb29750a348c353a998116f8965b9bb41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="68bc7-102">&lt;Filter&gt;</span><span class="sxs-lookup"><span data-stu-id="68bc7-102">&lt;filter&gt;</span></span>

<span data-ttu-id="68bc7-103">Definiert einen Routingfilter, der den Typ von [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der bei der Auswertung eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen Daten oder Parameter.</span><span class="sxs-lookup"><span data-stu-id="68bc7-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="68bc7-104">\<system.serviceModel > \<routing > \<Filter > \<Filter ></span><span class="sxs-lookup"><span data-stu-id="68bc7-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="68bc7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="68bc7-105">Syntax</span></span>

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="68bc7-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68bc7-106">Attributes and elements</span></span>

<span data-ttu-id="68bc7-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68bc7-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="68bc7-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="68bc7-108">Attributes</span></span>

| <span data-ttu-id="68bc7-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="68bc7-109">Attribute</span></span>  | <span data-ttu-id="68bc7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68bc7-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="68bc7-111">customType</span><span class="sxs-lookup"><span data-stu-id="68bc7-111">customType</span></span> | <span data-ttu-id="68bc7-112">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68bc7-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="68bc7-113">Wenn `filterType` festgelegt ist, um `custom`, dieses Attribut enthält den vollqualifizierten Typnamen des zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="68bc7-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="68bc7-114">`filterData`Es enthält auch Werte, die während der Auswertung des Filters benutzerdefinierten Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68bc7-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="68bc7-115">filterData</span><span class="sxs-lookup"><span data-stu-id="68bc7-115">filterData</span></span> | <span data-ttu-id="68bc7-116">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="68bc7-116">A string containing the filter data.</span></span> <span data-ttu-id="68bc7-117">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="68bc7-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="68bc7-118">filterType</span><span class="sxs-lookup"><span data-stu-id="68bc7-118">filterType</span></span> | <span data-ttu-id="68bc7-119">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="68bc7-119">A string containing the filter type.</span></span> <span data-ttu-id="68bc7-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="68bc7-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="68bc7-121">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="68bc7-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="68bc7-122">Name</span><span class="sxs-lookup"><span data-stu-id="68bc7-122">name</span></span>       | <span data-ttu-id="68bc7-123">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="68bc7-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="68bc7-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68bc7-124">Child elements</span></span>

<span data-ttu-id="68bc7-125">Keine</span><span class="sxs-lookup"><span data-stu-id="68bc7-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68bc7-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68bc7-126">Parent elements</span></span>

| <span data-ttu-id="68bc7-127">Element</span><span class="sxs-lookup"><span data-stu-id="68bc7-127">Element</span></span> | <span data-ttu-id="68bc7-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68bc7-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="68bc7-129">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="68bc7-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="68bc7-130">Ein Konfigurationsabschnitt zum Definieren eines Satzes von Routingfiltern, die den Typ von [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der beim Auswerten eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="68bc7-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="68bc7-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68bc7-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
