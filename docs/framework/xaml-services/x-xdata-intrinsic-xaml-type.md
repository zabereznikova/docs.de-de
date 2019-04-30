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
ms.openlocfilehash: c8044bc341ded6ef7b03bbdf701e724654460d54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938826"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="790d3-102">Systeminterner x:XData-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="790d3-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="790d3-103">Ermöglicht die Platzierung von XML-Dateninseln innerhalb einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="790d3-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="790d3-104">XML-Elemente im `x:XData` sollten von XAML-Prozessoren nicht behandelt werden, als wären sie Teil der agierende Standard-XAML-Namespace oder irgendeinen anderen XAML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="790d3-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="790d3-105">`x:XData` kann beliebigen wohlgeformten XML-Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="790d3-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="790d3-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="790d3-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="790d3-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="790d3-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="790d3-108">Das einzelne Stammelement der Dateninsel eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="790d3-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="790d3-109">XML, das keinen einzigen Stammknoten verfügt für die meisten Verbraucher "Eventual" wird als ungültig angesehen.</span><span class="sxs-lookup"><span data-stu-id="790d3-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="790d3-110">Ein einziger Stammknoten ist insbesondere erforderlich, wenn die `x:XData` dient als eine XML-Datenquelle für WPF- oder viele andere Technologien, die XML-Datenquellen für die Datenbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="790d3-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="790d3-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="790d3-111">Optional.</span></span> <span data-ttu-id="790d3-112">XML-Code, der die XML-Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="790d3-112">XML that represents the XML data.</span></span> <span data-ttu-id="790d3-113">Kann eine beliebige Anzahl von Elementen als Elementdaten enthalten sein, und geschachtelte Elemente in anderen Elementen enthalten sein können; Allerdings gelten die allgemeinen Regeln des XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="790d3-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="790d3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="790d3-114">Remarks</span></span>  
 <span data-ttu-id="790d3-115">Die XML-Elemente innerhalb einer `x:XData` -Objekt kann erneut deklarieren, alle möglichen Namespaces und Präfixe der enthaltenden XMLDOM in den Daten.</span><span class="sxs-lookup"><span data-stu-id="790d3-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="790d3-116">Den programmgesteuerten Zugriff auf XML-Daten und die `x:XData` XAML-Grundtyp kann in .NET Framework-XAML-Dienste über die <xref:System.Windows.Markup.XData> Klasse.</span><span class="sxs-lookup"><span data-stu-id="790d3-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="790d3-117">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="790d3-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="790d3-118">Die `x:XData` Objekt wird in erster Linie als ein untergeordnetes Objekt verwendet einen <xref:System.Windows.Data.XmlDataProvider>, oder Sie können auch als untergeordnetes Objekt des der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML, dies ist in der Regel ausgedrückt in Eigenschaftenelement-Syntax).</span><span class="sxs-lookup"><span data-stu-id="790d3-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="790d3-119">Die Daten sollten in der Regel den XML-Namespace innerhalb der Dateninsel einer neuen XML-Namespace (festgelegt auf eine leere Zeichenfolge) definieren.</span><span class="sxs-lookup"><span data-stu-id="790d3-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="790d3-120">Dies ist am einfachsten, für die einfache Daten Dateninseln, da die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, die zum Verweisen auf, und Binden an die Daten verwendet werden keine Einbeziehung von Präfixen.</span><span class="sxs-lookup"><span data-stu-id="790d3-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="790d3-121">Komplexere Dateninseln möglicherweise mehrere Präfixe für die Daten definieren und Verwenden von einem bestimmten Präfix für den XML-Namespace im Stammverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="790d3-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="790d3-122">In diesem Fall alle <xref:System.Windows.Data.Binding.XPath%2A> ausdrucksverweisen sollte das entsprechende Namespace zugeordnete Präfix enthalten.</span><span class="sxs-lookup"><span data-stu-id="790d3-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="790d3-123">Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="790d3-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="790d3-124">Technisch gesehen `x:XData` können verwendet werden, wie der Inhalt einer beliebigen Eigenschaft des Typs <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="790d3-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="790d3-125">Allerdings <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ist die einzige deutlich erkennbare-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="790d3-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790d3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="790d3-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="790d3-127">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="790d3-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="790d3-128">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="790d3-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
