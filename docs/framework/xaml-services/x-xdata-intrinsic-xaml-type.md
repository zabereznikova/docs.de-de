---
title: Systeminterner x:XData-XAML-Typ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 3e448c28be6515748254e267b70f3c898b9226a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a><span data-ttu-id="c4916-102">Systeminterner x:XData-XAML-Typ</span><span class="sxs-lookup"><span data-stu-id="c4916-102">x:XData Intrinsic XAML Type</span></span>
<span data-ttu-id="c4916-103">Ermöglicht die Platzierung von XML-Dateninseln in einer XAML-Produktion.</span><span class="sxs-lookup"><span data-stu-id="c4916-103">Enables placement of XML data islands within a XAML production.</span></span> <span data-ttu-id="c4916-104">XML-Elemente im `x:XData` nicht durch Verwendung von XAML-Prozessoren behandelt werden soll, als wären sie Teil des agierenden standardmäßigen XAML-Namespace oder irgendeinen anderen XAML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="c4916-104">XML elements within `x:XData` should not be treated by XAML processors as if they are a part of the acting default XAML namespace or any other XAML namespace.</span></span> <span data-ttu-id="c4916-105">`x:XData`Dies können beliebiges wohlgeformtes XML enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4916-105">`x:XData` can contain arbitrary well-formed XML.</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="c4916-106">Verwendung von XAML-Objektelementen</span><span class="sxs-lookup"><span data-stu-id="c4916-106">XAML Object Element Usage</span></span>  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="c4916-107">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="c4916-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`elementDataRoot`|<span data-ttu-id="c4916-108">Das einzelne Stammelement der eingeschlossenen Dateninsel.</span><span class="sxs-lookup"><span data-stu-id="c4916-108">The single root element of the enclosed data island.</span></span> <span data-ttu-id="c4916-109">Für die meisten tatsächlichen Consumer wird XML, die keinen einzigen Stammknoten als ungültig betrachtet.</span><span class="sxs-lookup"><span data-stu-id="c4916-109">For most eventual consumers, XML that does not have a single root is considered invalid.</span></span> <span data-ttu-id="c4916-110">Insbesondere ist ein einziger Stammknoten erforderlich, wenn die `x:XData` dient als eine XML-Datenquelle für WPF- oder vielen anderen Technologien, die XML-Datenquellen für die Datenbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4916-110">In particular, a single root is required if the `x:XData` is intended as an XML data source for WPF or many other technologies that use XML sources for data binding.</span></span>|  
|`[elementData]`|<span data-ttu-id="c4916-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c4916-111">Optional.</span></span> <span data-ttu-id="c4916-112">XML-Datei, die die XML-Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="c4916-112">XML that represents the XML data.</span></span> <span data-ttu-id="c4916-113">Kann eine beliebige Anzahl von Elementen als Elementdaten enthalten sein, und geschachtelte Elemente können in andere Elemente enthalten sein. Allerdings gelten die allgemeinen Regeln des XML-Codes.</span><span class="sxs-lookup"><span data-stu-id="c4916-113">Any number of elements can be contained as element data and nested elements can be contained in other elements; however, the general rules of XML apply.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4916-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4916-114">Remarks</span></span>  
 <span data-ttu-id="c4916-115">Die XML-Elemente innerhalb einer `x:XData` Objekt kann erneut deklarieren, alle möglichen Namespaces und Präfixe der enthaltenen XMLDOM in den Daten.</span><span class="sxs-lookup"><span data-stu-id="c4916-115">The XML elements within an `x:XData` object can re-declare all possible namespaces and prefixes of the containing XMLDOM within the data.</span></span>  
  
 <span data-ttu-id="c4916-116">Programmgesteuerter Zugriff auf XML-Daten und die `x:XData` systeminterne XAML-Typ kann in .NET Framework-XAML-Dienste über die <xref:System.Windows.Markup.XData> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c4916-116">Programmatic access to XML data and the `x:XData` intrinsic XAML type is possible in .NET Framework XAML Services through the <xref:System.Windows.Markup.XData> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c4916-117">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="c4916-117">WPF Usage Notes</span></span>  
 <span data-ttu-id="c4916-118">Die `x:XData` Objekt dient in erster Linie als ein untergeordnetes Objekt des ein <xref:System.Windows.Data.XmlDataProvider>, oder alternativ das untergeordnete Objekt von der <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Eigenschaft (in XAML, dies ist i. d. r. ausgedrückt in Eigenschaftenelementsyntax).</span><span class="sxs-lookup"><span data-stu-id="c4916-118">The `x:XData` object is primarily used as a child object of an <xref:System.Windows.Data.XmlDataProvider>, or alternatively, as the child object of the <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> property (in XAML, this is typically expressed in property element syntax).</span></span>  
  
 <span data-ttu-id="c4916-119">Die Daten sollten in der Regel den Basis-XML-Namespace innerhalb der Dateninsel zu einer neuen XML-Namespace (festgelegt auf eine leere Zeichenfolge) definieren.</span><span class="sxs-lookup"><span data-stu-id="c4916-119">The data should typically redefine the base XML namespace within the data island to be a new default XML namespace (set to an empty string).</span></span> <span data-ttu-id="c4916-120">Dies ist einfachste für einfache Datentypen Inseln, da die <xref:System.Windows.Data.Binding.XPath%2A> Ausdrücke, die zum Verweisen auf und Binden an die Daten verwendet werden können die Aufnahme von Präfixen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="c4916-120">This is easiest for simple data islands because the <xref:System.Windows.Data.Binding.XPath%2A> expressions that are used to reference and bind to the data can avoid inclusion of prefixes.</span></span> <span data-ttu-id="c4916-121">Komplexere Dateninseln möglicherweise mehrere Präfixe für die Daten zu definieren und Verwenden von einem bestimmten Präfix für den XML-Namespace im Stammverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c4916-121">More complex data islands might define multiple prefixes for the data and use a specific prefix for the XML namespace at the root.</span></span> <span data-ttu-id="c4916-122">In diesem Fall alle <xref:System.Windows.Data.Binding.XPath%2A> ausdrucksverweisen sollte das entsprechende zugeordneten Namespace-Präfix enthalten.</span><span class="sxs-lookup"><span data-stu-id="c4916-122">In this case, all <xref:System.Windows.Data.Binding.XPath%2A> expression references should include the appropriate namespace-mapped prefix.</span></span> <span data-ttu-id="c4916-123">Weitere Informationen finden Sie unter [Übersicht über Datenbindung](../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c4916-123">For more information, see [Data Binding Overview](../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>  
  
 <span data-ttu-id="c4916-124">Technisch gesehen `x:XData` können verwendet werden, wie der Inhalt einer beliebigen Eigenschaft vom Typ <xref:System.Xml.Serialization.IXmlSerializable>.</span><span class="sxs-lookup"><span data-stu-id="c4916-124">Technically, `x:XData` can be used as the content of any property of type <xref:System.Xml.Serialization.IXmlSerializable>.</span></span> <span data-ttu-id="c4916-125">Allerdings <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> ist die einzige deutlich erkennbare-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="c4916-125">However, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> is the only prominent implementation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4916-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4916-126">See Also</span></span>  
 <xref:System.Windows.Data.XmlDataProvider>  
 [<span data-ttu-id="c4916-127">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="c4916-127">Data Binding Overview</span></span>](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="c4916-128">Bindung als Markuperweiterung</span><span class="sxs-lookup"><span data-stu-id="c4916-128">Binding Markup Extension</span></span>](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
