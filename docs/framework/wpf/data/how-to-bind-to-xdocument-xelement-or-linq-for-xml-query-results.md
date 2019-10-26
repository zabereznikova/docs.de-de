---
title: 'Gewusst wie: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920122"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="a29b8-102">Gewusst wie: Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="a29b8-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>

<span data-ttu-id="a29b8-103">In diesem Beispiel wird veranschaulicht, wie XML-Daten mithilfe <xref:System.Xml.Linq.XDocument>an eine <xref:System.Windows.Controls.ItemsControl> gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="a29b8-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>

## <a name="example"></a><span data-ttu-id="a29b8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a29b8-104">Example</span></span>

<span data-ttu-id="a29b8-105">Der folgende XAML-Code definiert eine <xref:System.Windows.Controls.ItemsControl> und enthält eine Daten Vorlage für Daten vom Typ `Planet` im `http://planetsNS` XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="a29b8-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="a29b8-106">Ein XML-Datentyp, der in einem Namespace definiert ist, muss den Namespace in geschweiften Klammern enthalten. An einer Position, an der XAML-Markuperweiterungen auftreten können, muss dem Namespace eine Escapesequenz mit geschweiften Klammern vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="a29b8-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="a29b8-107">Dieser Code bindet an dynamische Eigenschaften, die den Methoden <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> der Klasse <xref:System.Xml.Linq.XElement> entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a29b8-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="a29b8-108">Dynamische Eigenschaften ermöglichen die Bindung von XAML an dynamische Eigenschaften, die die Namen von Methoden gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="a29b8-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="a29b8-109">Weitere Informationen finden Sie unter [LINQ to XML Dynamic Properties](linq-to-xml-dynamic-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a29b8-109">To learn more, see [LINQ to XML dynamic properties](linq-to-xml-dynamic-properties.md).</span></span> <span data-ttu-id="a29b8-110">Beachten Sie, dass die XML-Standardnamespacedeklaration nicht für Attributnamen gilt.</span><span class="sxs-lookup"><span data-stu-id="a29b8-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

<span data-ttu-id="a29b8-111">Der folgende C# Code ruft<xref:System.Xml.Linq.XDocument.Load%2A>auf und legt den Datenkontext des Stapel Bereichs auf alle unter Elemente des Elements`SolarSystemPlanets`im`http://planetsNS`XML-Namespace fest.</span><span class="sxs-lookup"><span data-stu-id="a29b8-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

<span data-ttu-id="a29b8-112">XML-Daten können mit <xref:System.Windows.Data.ObjectDataProvider>als XAML-Ressource gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="a29b8-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="a29b8-113">Ein vollständiges Beispiel finden Sie unter [L2DBForm. XAML-Quellcode](l2dbform-xaml-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="a29b8-113">For a complete example, see  [L2DBForm.xaml source code](l2dbform-xaml-source-code.md).</span></span> <span data-ttu-id="a29b8-114">Im folgenden Beispiel wird gezeigt, wie der Datenkontext in Code auf eine Objektressource festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a29b8-114">The following sample shows how code can set the data context to an object resource.</span></span>

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

<span data-ttu-id="a29b8-115">Die dynamischen Eigenschaften, die <xref:System.Xml.Linq.XContainer.Element%2A> und <xref:System.Xml.Linq.XElement.Attribute%2A> zugeordnet werden, bieten Flexibilität in XAML.</span><span class="sxs-lookup"><span data-stu-id="a29b8-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="a29b8-116">Der Code kann auch an die Ergebnisse einer LINQ to XML-Abfrage gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="a29b8-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="a29b8-117">In diesem Beispiel erfolgt die Bindung an die nach einem Elementwert sortierten Abfrageergebnisse.</span><span class="sxs-lookup"><span data-stu-id="a29b8-117">This example binds to query results ordered by an element value.</span></span>

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a><span data-ttu-id="a29b8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a29b8-118">See also</span></span>

- [<span data-ttu-id="a29b8-119">Übersicht über Bindungsquellen</span><span class="sxs-lookup"><span data-stu-id="a29b8-119">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="a29b8-120">Übersicht über WPF-Datenbindung mit LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a29b8-120">WPF Data Binding with LINQ to XML Overview</span></span>](wpf-data-binding-with-linq-to-xml-overview.md)
- [<span data-ttu-id="a29b8-121">Beispiel für die WPF-Datenbindung mit LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a29b8-121">WPF Data Binding Using LINQ to XML Example</span></span>](linq-to-xml-data-binding-sample.md)
- [<span data-ttu-id="a29b8-122">Dynamische Eigenschaften in LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="a29b8-122">LINQ to XML Dynamic Properties</span></span>](linq-to-xml-dynamic-properties.md)
