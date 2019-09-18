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
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053699"
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="cc490-102">Systeminterner x:XData-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="cc490-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="cc490-103">Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="cc490-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="cc490-104">XML-Elemente `x:XData` in sollten nicht von XAML-Prozessoren behandelt werden, als ob Sie Teil des aktiven XAML-Standard Namespace oder eines anderen XAML-Namespace sind.</span><span class="sxs-lookup"><span data-stu-id="cc490-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="cc490-105">`x:XData`kann beliebige wohlgeformte XML-Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="cc490-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="cc490-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="cc490-106">XAML Object Element Usage</span></span>  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="cc490-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="cc490-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="cc490-108">Das einzelne Stamm Element der eingeschlossenen Daten Insel.</span><span class="sxs-lookup"><span data-stu-id="cc490-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="cc490-109">Bei den meisten möglichen Consumern wird XML, das keinen einzelnen Stamm hat, als ungültig betrachtet.</span><span class="sxs-lookup"><span data-stu-id="cc490-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="cc490-110">Insbesondere ist ein einzelner Stamm erforderlich, wenn der `x:XData` als XML-Datenquelle für WPF oder viele andere Technologien gedacht ist, die XML-Quellen für die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc490-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="cc490-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="cc490-111">Optional.</span></span> <span data-ttu-id="cc490-112">XML-Code, der die XML-Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="cc490-112">XML that represents the XML data.</span></span> <span data-ttu-id="cc490-113">Eine beliebige Anzahl von Elementen kann als Elementdaten enthalten sein, und in anderen Elementen können sich auch die in der Tabelle enthaltenen Elemente befinden. Allerdings gelten die allgemeinen Regeln von XML.</span><span class="sxs-lookup"><span data-stu-id="cc490-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc490-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc490-114">Remarks</span></span>  
 <span data-ttu-id="cc490-115">Die XML-Elemente in `x:XData` einem-Objekt können alle möglichen Namespaces und Präfixe des enthaltenden XMLDOM in den Daten erneut deklarieren.</span><span class="sxs-lookup"><span data-stu-id="cc490-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="cc490-116">Programm gesteuerter Zugriff auf XML- `x:XData` Daten und den systeminternen XAML-Typ ist in .NET Framework XAML-Diensten durch die <xref:System.Windows.Markup.XData> -Klasse möglich.</span><span class="sxs-lookup"><span data-stu-id="cc490-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="cc490-117">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="cc490-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="cc490-118">Das `x:XData` -Objekt wird primär als untergeordnetes Objekt <xref:System.Windows.Data.XmlDataProvider>eines oder alternativ als <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> untergeordnetes Objekt der-Eigenschaft verwendet (in XAML wird dies in der Regel in der Eigenschafts Element Syntax ausgedrückt).</span><span class="sxs-lookup"><span data-stu-id="cc490-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="cc490-119">Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Daten Insel neu definieren, sodass er ein neuer XML-Standard Namespace ist (auf eine leere Zeichenfolge festgelegt).</span><span class="sxs-lookup"><span data-stu-id="cc490-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="cc490-120">Dies ist für einfache Dateninseln am einfachsten, <xref:System.Windows.Data.Binding.XPath%2A> weil die Ausdrücke, mit denen auf die Daten verwiesen und diese gebunden werden, die Einbindung von Präfixen vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="cc490-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="cc490-121">Komplexere Dateninseln definieren möglicherweise mehrere Präfixe für die Daten und verwenden ein bestimmtes Präfix für den XML-Namespace im Stammverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cc490-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="cc490-122">In diesem Fall sollten alle <xref:System.Windows.Data.Binding.XPath%2A> Ausdrucks Verweise das entsprechende, Namespace zugeordnete Präfix enthalten.</span><span class="sxs-lookup"><span data-stu-id="cc490-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="cc490-123">Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cc490-123">For more information, see [Data Binding Overview](../wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="cc490-124">Technisch kann als Inhalt einer beliebigen Eigenschaft des Typs <xref:System.Xml.Serialization.IXmlSerializable>verwendet werden. `x:XData`</span><span class="sxs-lookup"><span data-stu-id="cc490-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="cc490-125"><xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Ist jedoch die einzige bedeutende Implementierung.</span><span class="sxs-lookup"><span data-stu-id="cc490-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc490-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc490-126">See also</span></span>

- <xref:System.Windows.Data.XmlDataProvider>
- [<span data-ttu-id="cc490-127">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="cc490-127">Data Binding Overview</span></span>](../wpf/data/data-binding-overview.md)
- [<span data-ttu-id="cc490-128">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="cc490-128">Binding Markup Extension</span></span>](../wpf/advanced/binding-markup-extension.md)
