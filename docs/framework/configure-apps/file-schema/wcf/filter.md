---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278784"
---
# <a name="filter"></a><span data-ttu-id="d3908-101">\<filter></span><span class="sxs-lookup"><span data-stu-id="d3908-101">\<filter></span></span>

<span data-ttu-id="d3908-102">Definiert einen Routingfilter, der den Typ der Windows Communication Foundation (WCF) bestimmt<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten als auch alle Daten oder Parameter, die den Filter erforderlichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3908-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="d3908-103">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="d3908-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="d3908-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3908-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3908-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3908-105">Attributes and elements</span></span>

<span data-ttu-id="d3908-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3908-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d3908-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3908-107">Attributes</span></span>

| <span data-ttu-id="d3908-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="d3908-108">Attribute</span></span>  | <span data-ttu-id="d3908-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3908-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="d3908-110">customType</span><span class="sxs-lookup"><span data-stu-id="d3908-110">customType</span></span> | <span data-ttu-id="d3908-111">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d3908-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="d3908-112">Wenn `filterType` nastaven NA hodnotu `custom`, dieses Attribut enthält den vollqualifizierten Typnamen des zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="d3908-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="d3908-113">`filterData` enthält möglicherweise auch Werte, die während der Auswertung des benutzerdefinierten Typfilters verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3908-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="d3908-114">filterData</span><span class="sxs-lookup"><span data-stu-id="d3908-114">filterData</span></span> | <span data-ttu-id="d3908-115">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="d3908-115">A string containing the filter data.</span></span> <span data-ttu-id="d3908-116">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3908-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d3908-117">filterType</span><span class="sxs-lookup"><span data-stu-id="d3908-117">filterType</span></span> | <span data-ttu-id="d3908-118">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="d3908-118">A string containing the filter type.</span></span> <span data-ttu-id="d3908-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="d3908-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="d3908-120">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3908-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d3908-121">Name</span><span class="sxs-lookup"><span data-stu-id="d3908-121">name</span></span>       | <span data-ttu-id="d3908-122">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="d3908-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d3908-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3908-123">Child elements</span></span>

<span data-ttu-id="d3908-124">Keine</span><span class="sxs-lookup"><span data-stu-id="d3908-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d3908-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3908-125">Parent elements</span></span>

| <span data-ttu-id="d3908-126">Element</span><span class="sxs-lookup"><span data-stu-id="d3908-126">Element</span></span> | <span data-ttu-id="d3908-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3908-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="d3908-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="d3908-128">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="d3908-129">Ein Konfigurationsabschnitt zum Definieren eines Satzes von routingfiltern, die den Typ der Windows Communication Foundation (WCF) bestimmen<xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3908-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d3908-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3908-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
