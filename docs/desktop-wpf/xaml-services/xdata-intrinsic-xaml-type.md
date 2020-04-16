---
title: Systeminterner x:XData-XAML-Typ
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432791"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="14469-102">Systeminterner x:XData-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="14469-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="14469-103">Ermöglicht die Platzierung von XML-Dateninseln innerhalb einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="14469-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="14469-104">XML-Elemente `x:XData` innerhalb sollten von XAML-Prozessoren nicht so behandelt werden, als wären sie Teil des standardmäßigen XAML-Namespace oder eines anderen XAML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="14469-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="14469-105">`x:XData`kann beliebigewohle XML-Codes enthalten.</span><span class="sxs-lookup"><span data-stu-id="14469-105">`x:XData` can contain arbitrary well-formed XML.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="14469-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="14469-106">XAML Object Element Usage</span></span>

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a><span data-ttu-id="14469-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="14469-107">XAML Values</span></span>

|||
|-|-|
|`elementDataRoot`|<span data-ttu-id="14469-108">Das einzelne Stammelement der eingeschlossenen Dateninsel.</span><span class="sxs-lookup"><span data-stu-id="14469-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="14469-109">Für die meisten Verbraucher gilt XML, das keinen einzelnen Stamm hat, als ungültig.</span><span class="sxs-lookup"><span data-stu-id="14469-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="14469-110">Insbesondere ist ein einzelner Stamm `x:XData` erforderlich, wenn der als XML-Datenquelle für WPF oder viele andere Technologien gedacht ist, die XML-Quellen für die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="14469-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|
|`[elementData]`|<span data-ttu-id="14469-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="14469-111">Optional.</span></span> <span data-ttu-id="14469-112">XML, das die XML-Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="14469-112">XML that represents the XML data.</span></span> <span data-ttu-id="14469-113">Eine beliebige Anzahl von Elementen kann als Elementdaten enthalten sein, und verschachtelte Elemente können in anderen Elementen enthalten sein. Es gelten jedoch die allgemeinen XML-Regeln.</span><span class="sxs-lookup"><span data-stu-id="14469-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|

## <a name="remarks"></a><span data-ttu-id="14469-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="14469-114">Remarks</span></span>

<span data-ttu-id="14469-115">Die XML-Elemente `x:XData` innerhalb eines Objekts können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM in den Daten neu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="14469-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>

<span data-ttu-id="14469-116">Der programmgesteuerte Zugriff `x:XData` auf XML-Daten und den systeminternen XAML-Typ ist in .NET XAML Services über die <xref:System.Windows.Markup.XData> Klasse möglich.</span><span class="sxs-lookup"><span data-stu-id="14469-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="14469-117">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="14469-117">WPF Usage Notes</span></span>

<span data-ttu-id="14469-118">Das `x:XData` Objekt wird in erster Linie <xref:System.Windows.Data.XmlDataProvider>als untergeordnetes Objekt eines verwendet, oder alternativ als untergeordnetes Objekt der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML wird dies in der Regel in der Eigenschaftselementsyntax ausgedrückt).</span><span class="sxs-lookup"><span data-stu-id="14469-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>

<span data-ttu-id="14469-119">Die Daten sollten in der Regel den XML-Basisnamespace innerhalb der Dateninsel neu definieren, um ein neuer Standard-XML-Namespace zu werden (auf eine leere Zeichenfolge festgelegt).</span><span class="sxs-lookup"><span data-stu-id="14469-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="14469-120">Dies ist für einfache <xref:System.Windows.Data.Binding.XPath%2A> Dateninseln am einfachsten, da die Ausdrücke, die zum Verweisen und Binden an die Daten verwendet werden, die Aufnahme von Präfixen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="14469-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="14469-121">Komplexere Dateninseln können mehrere Präfixe für die Daten definieren und ein bestimmtes Präfix für den XML-Namespace im Stammverwenden verwenden.</span><span class="sxs-lookup"><span data-stu-id="14469-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="14469-122">In diesem Fall <xref:System.Windows.Data.Binding.XPath%2A> sollten alle Ausdrucksverweise das entsprechende Präfix namespace-zugeordnet enthalten.</span><span class="sxs-lookup"><span data-stu-id="14469-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="14469-123">Weitere Informationen finden Sie unter [Datenbindungsübersicht](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="14469-123">For more information, see [Data Binding Overview](../data/data-binding-overview.md).</span></span>

<span data-ttu-id="14469-124">Technisch kann `x:XData` als Inhalt jeder Eigenschaft des <xref:System.Xml.Serialization.IXmlSerializable>Typs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14469-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="14469-125"><xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Dies ist jedoch die einzige prominente Umsetzung.</span><span class="sxs-lookup"><span data-stu-id="14469-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="14469-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14469-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="14469-127">Datenbindung sübersicht</span><span class="sxs-lookup"><span data-stu-id="14469-127">Data Binding Overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="14469-128">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="14469-128">Binding Markup Extension</span></span>](../../framework/wpf/advanced/binding-markup-extension.md)
