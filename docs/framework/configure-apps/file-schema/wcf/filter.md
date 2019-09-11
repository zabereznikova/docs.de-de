---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855257"
---
# <a name="filter"></a><span data-ttu-id="aab5f-101">\<Filter ></span><span class="sxs-lookup"><span data-stu-id="aab5f-101">\<filter></span></span>

<span data-ttu-id="aab5f-102">Definiert einen Routing Filter, der den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmt, der beim Auswerten eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen unterstützenden Daten oder Parameter.</span><span class="sxs-lookup"><span data-stu-id="aab5f-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="aab5f-103">[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aab5f-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aab5f-104">&nbsp;&nbsp;[ **\<Routing >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="aab5f-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="aab5f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Filter >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="aab5f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="aab5f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Filter >**</span><span class="sxs-lookup"><span data-stu-id="aab5f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab5f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aab5f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aab5f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aab5f-108">Attributes and elements</span></span>

<span data-ttu-id="aab5f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aab5f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aab5f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="aab5f-110">Attributes</span></span>

| <span data-ttu-id="aab5f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="aab5f-111">Attribute</span></span>  | <span data-ttu-id="aab5f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab5f-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="aab5f-113">customType</span><span class="sxs-lookup"><span data-stu-id="aab5f-113">customType</span></span> | <span data-ttu-id="aab5f-114">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aab5f-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="aab5f-115">Wenn `filterType` auf`custom`festgelegt ist, enthält dieses Attribut den voll qualifizierten Typnamen der zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="aab5f-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="aab5f-116">`filterData`kann auch Werte enthalten, die während der Auswertung des benutzerdefinierten Typfilters verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="aab5f-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="aab5f-117">filterData</span><span class="sxs-lookup"><span data-stu-id="aab5f-117">filterData</span></span> | <span data-ttu-id="aab5f-118">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="aab5f-118">A string containing the filter data.</span></span> <span data-ttu-id="aab5f-119">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="aab5f-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="aab5f-120">filterType</span><span class="sxs-lookup"><span data-stu-id="aab5f-120">filterType</span></span> | <span data-ttu-id="aab5f-121">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="aab5f-121">A string containing the filter type.</span></span> <span data-ttu-id="aab5f-122">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="aab5f-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="aab5f-123">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="aab5f-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="aab5f-124">NAME</span><span class="sxs-lookup"><span data-stu-id="aab5f-124">name</span></span>       | <span data-ttu-id="aab5f-125">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="aab5f-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="aab5f-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab5f-126">Child elements</span></span>

<span data-ttu-id="aab5f-127">Keine</span><span class="sxs-lookup"><span data-stu-id="aab5f-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="aab5f-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aab5f-128">Parent elements</span></span>

| <span data-ttu-id="aab5f-129">Element</span><span class="sxs-lookup"><span data-stu-id="aab5f-129">Element</span></span> | <span data-ttu-id="aab5f-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aab5f-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="aab5f-131">\<routing></span><span class="sxs-lookup"><span data-stu-id="aab5f-131">\<routing></span></span>](routing.md) | <span data-ttu-id="aab5f-132">Ein Konfigurations Abschnitt zum Definieren eines Satzes von Routing filtern, die den Typ des Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> bestimmen, der bei der Auswertung eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="aab5f-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="aab5f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aab5f-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
