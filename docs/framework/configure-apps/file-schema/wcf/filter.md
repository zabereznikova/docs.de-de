---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855257"
---
# \<filter>

<span data-ttu-id="91b1e-101">Definiert einen Routing Filter, der den Typ des Windows Communication Foundation (WCF) bestimmt, der <xref:System.ServiceModel.Dispatcher.MessageFilter> beim Auswerten eingehender Nachrichten verwendet werden soll, sowie alle für den Filter erforderlichen unterstützenden Daten oder Parameter.</span><span class="sxs-lookup"><span data-stu-id="91b1e-101">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**  
  
## <a name="syntax"></a><span data-ttu-id="91b1e-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="91b1e-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91b1e-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="91b1e-103">Attributes and elements</span></span>

<span data-ttu-id="91b1e-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="91b1e-104">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="91b1e-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="91b1e-105">Attributes</span></span>

| <span data-ttu-id="91b1e-106">attribute</span><span class="sxs-lookup"><span data-stu-id="91b1e-106">Attribute</span></span>  | <span data-ttu-id="91b1e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91b1e-107">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="91b1e-108">customType</span><span class="sxs-lookup"><span data-stu-id="91b1e-108">customType</span></span> | <span data-ttu-id="91b1e-109">Eine Zeichenfolge, die den vollqualifizierten Typnamen des benutzerdefinierten Typs enthält, der als Filter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91b1e-109">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="91b1e-110">Wenn `filterType` auf festgelegt ist `custom` , enthält dieses Attribut den voll qualifizierten Typnamen der zu erstellenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="91b1e-110">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="91b1e-111">`filterData`kann auch Werte enthalten, die während der Auswertung des benutzerdefinierten Typfilters verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="91b1e-111">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="91b1e-112">filterData</span><span class="sxs-lookup"><span data-stu-id="91b1e-112">filterData</span></span> | <span data-ttu-id="91b1e-113">Eine Zeichenfolge, die die Filterdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="91b1e-113">A string containing the filter data.</span></span> <span data-ttu-id="91b1e-114">Weitere Informationen zur Angabe dieses Attributs finden Sie unter <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="91b1e-114">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="91b1e-115">filterType</span><span class="sxs-lookup"><span data-stu-id="91b1e-115">filterType</span></span> | <span data-ttu-id="91b1e-116">Eine Zeichenfolge, die den Filtertyp enthält.</span><span class="sxs-lookup"><span data-stu-id="91b1e-116">A string containing the filter type.</span></span> <span data-ttu-id="91b1e-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="91b1e-117">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="91b1e-118">Weitere Informationen zur Funktionsweise mit dem `filterData`-Attribut finden Sie unter  <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="91b1e-118">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="91b1e-119">name</span><span class="sxs-lookup"><span data-stu-id="91b1e-119">name</span></span>       | <span data-ttu-id="91b1e-120">Eine Zeichenfolge, die den eindeutigen Namen dieses Filterelements enthält.</span><span class="sxs-lookup"><span data-stu-id="91b1e-120">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="91b1e-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91b1e-121">Child elements</span></span>

<span data-ttu-id="91b1e-122">Keine</span><span class="sxs-lookup"><span data-stu-id="91b1e-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="91b1e-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="91b1e-123">Parent elements</span></span>

| <span data-ttu-id="91b1e-124">Element</span><span class="sxs-lookup"><span data-stu-id="91b1e-124">Element</span></span> | <span data-ttu-id="91b1e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91b1e-125">Description</span></span> |
| ------- | ----------- |
| [\<routing>](routing.md) | <span data-ttu-id="91b1e-126">Ein Konfigurations Abschnitt zum Definieren eines Satzes von Routing filtern, die den Typ des Windows Communication Foundation (WCF) bestimmen, der <xref:System.ServiceModel.Dispatcher.MessageFilter> bei der Auswertung eingehender Nachrichten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91b1e-126">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="91b1e-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91b1e-127">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
