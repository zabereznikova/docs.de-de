---
title: '&lt;Filter&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747209"
---
# <a name="ltfiltergt"></a><span data-ttu-id="7c896-102">&lt;Filter&gt;</span><span class="sxs-lookup"><span data-stu-id="7c896-102">&lt;filter&gt;</span></span>

<span data-ttu-id="7c896-103">Definiert einen Routingfilter, der den Typ der Windows Communication Foundation (WCF) bestimmt<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten, als sowie alle Daten oder den Filter erforderlichen Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c896-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="7c896-104">\<system.serviceModel > \<routing > \<Filter > \<Filter ></span><span class="sxs-lookup"><span data-stu-id="7c896-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="7c896-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c896-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="7c896-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7c896-106">Attributes and elements</span></span>

<span data-ttu-id="7c896-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7c896-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7c896-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="7c896-108">Attributes</span></span>

| <span data-ttu-id="7c896-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="7c896-109">Attribute</span></span>  | <span data-ttu-id="7c896-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c896-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="7c896-111">customType</span><span class="sxs-lookup"><span data-stu-id="7c896-111">customType</span></span> | <span data-ttu-id="7c896-112">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c896-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="7c896-113">Wenn `filterType` festgelegt ist, um `custom`, dieses Attribut enthält den vollqualifizierten Typnamen des zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="7c896-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="7c896-114">`filterData` Es enthält auch Werte, die während der Auswertung des Filters benutzerdefinierten Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c896-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="7c896-115">filterData</span><span class="sxs-lookup"><span data-stu-id="7c896-115">filterData</span></span> | <span data-ttu-id="7c896-116">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="7c896-116">A string containing the filter data.</span></span> <span data-ttu-id="7c896-117">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c896-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="7c896-118">filterType</span><span class="sxs-lookup"><span data-stu-id="7c896-118">filterType</span></span> | <span data-ttu-id="7c896-119">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="7c896-119">A string containing the filter type.</span></span> <span data-ttu-id="7c896-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="7c896-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="7c896-121">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="7c896-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="7c896-122">Name</span><span class="sxs-lookup"><span data-stu-id="7c896-122">name</span></span>       | <span data-ttu-id="7c896-123">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="7c896-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="7c896-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c896-124">Child elements</span></span>

<span data-ttu-id="7c896-125">Keine</span><span class="sxs-lookup"><span data-stu-id="7c896-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7c896-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7c896-126">Parent elements</span></span>

| <span data-ttu-id="7c896-127">Element</span><span class="sxs-lookup"><span data-stu-id="7c896-127">Element</span></span> | <span data-ttu-id="7c896-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c896-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="7c896-129">\<Routing ></span><span class="sxs-lookup"><span data-stu-id="7c896-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="7c896-130">Ein Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c896-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7c896-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c896-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
