---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918898"
---
# <a name="filter"></a><span data-ttu-id="e670b-101">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="e670b-101">\<filter></span></span>

<span data-ttu-id="e670b-102">Definiert einen Routing Filter, der den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der beim Auswerten eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen unterstützenden Daten oder Parameter.</span><span class="sxs-lookup"><span data-stu-id="e670b-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="e670b-103">\<System. Service Model > \<Routing > \<Filter > \<Filter ></span><span class="sxs-lookup"><span data-stu-id="e670b-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="e670b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e670b-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e670b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e670b-105">Attributes and elements</span></span>

<span data-ttu-id="e670b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e670b-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e670b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e670b-107">Attributes</span></span>

| <span data-ttu-id="e670b-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="e670b-108">Attribute</span></span>  | <span data-ttu-id="e670b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e670b-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="e670b-110">customType</span><span class="sxs-lookup"><span data-stu-id="e670b-110">customType</span></span> | <span data-ttu-id="e670b-111">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e670b-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="e670b-112">Wenn `filterType` auf`custom`festgelegt ist, enthält dieses Attribut den voll qualifizierten Typnamen der zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="e670b-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="e670b-113">`filterData`kann auch Werte enthalten, die während der Auswertung des benutzerdefinierten Typfilters verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e670b-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="e670b-114">filterData</span><span class="sxs-lookup"><span data-stu-id="e670b-114">filterData</span></span> | <span data-ttu-id="e670b-115">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="e670b-115">A string containing the filter data.</span></span> <span data-ttu-id="e670b-116">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="e670b-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="e670b-117">filterType</span><span class="sxs-lookup"><span data-stu-id="e670b-117">filterType</span></span> | <span data-ttu-id="e670b-118">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="e670b-118">A string containing the filter type.</span></span> <span data-ttu-id="e670b-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="e670b-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="e670b-120">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="e670b-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="e670b-121">Name</span><span class="sxs-lookup"><span data-stu-id="e670b-121">name</span></span>       | <span data-ttu-id="e670b-122">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="e670b-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="e670b-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e670b-123">Child elements</span></span>

<span data-ttu-id="e670b-124">Keine</span><span class="sxs-lookup"><span data-stu-id="e670b-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e670b-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e670b-125">Parent elements</span></span>

| <span data-ttu-id="e670b-126">Element</span><span class="sxs-lookup"><span data-stu-id="e670b-126">Element</span></span> | <span data-ttu-id="e670b-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e670b-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="e670b-128">\<routing></span><span class="sxs-lookup"><span data-stu-id="e670b-128">\<routing></span></span>](routing.md) | <span data-ttu-id="e670b-129">Ein Konfigurations Abschnitt zum Definieren eines Satzes von Routing filtern, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e670b-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="e670b-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e670b-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
