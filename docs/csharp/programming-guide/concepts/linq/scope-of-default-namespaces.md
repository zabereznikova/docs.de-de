---
title: Bereich von Standardnamespaces in C#
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 7615351f6e5f8b18bd6466a83d54aa65a6c99b50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253042"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="5888c-102">Bereich von Standardnamespaces in C\#</span><span class="sxs-lookup"><span data-stu-id="5888c-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="5888c-103">Standardnamespaces, wie sie in der XML-Struktur dargestellt werden, befinden sich bei Abfragen nicht innerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="5888c-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="5888c-104">Bei XML, das sich in einem Standardnamespace befindet, müssen Sie weiterhin eine <xref:System.Xml.Linq.XNamespace>-Variable deklarieren und diese Variable mit dem lokalen Namen kombinieren, um einen qualifizierten Namen zu erhalten, der in der Abfrage verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5888c-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="5888c-105">Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="5888c-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="5888c-106">Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen, dann jedoch nicht ordnungsgemäß abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="5888c-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="5888c-107">Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5888c-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5888c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5888c-108">Example</span></span>  
 <span data-ttu-id="5888c-109">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="5888c-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5888c-110">Code</span><span class="sxs-lookup"><span data-stu-id="5888c-110">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="5888c-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5888c-111">Comments</span></span>  
 <span data-ttu-id="5888c-112">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="5888c-112">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="5888c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5888c-113">Example</span></span>  
 <span data-ttu-id="5888c-114">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.</span><span class="sxs-lookup"><span data-stu-id="5888c-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="5888c-115">Im Gegensatz zum falsch codierten Beispiel oben besteht der richtige Ansatz bei Verwendung von C# darin, ein <xref:System.Xml.Linq.XNamespace>-Objekt zu deklarieren und zu initialisieren und dieses beim Angeben von <xref:System.Xml.Linq.XName>-Objekten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5888c-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="5888c-116">In diesem Fall ist das Argument der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode ein <xref:System.Xml.Linq.XName>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="5888c-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5888c-117">Code</span><span class="sxs-lookup"><span data-stu-id="5888c-117">Code</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
### <a name="comments"></a><span data-ttu-id="5888c-118">Kommentare</span><span class="sxs-lookup"><span data-stu-id="5888c-118">Comments</span></span>  
 <span data-ttu-id="5888c-119">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="5888c-119">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="5888c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5888c-120">See also</span></span>

- [<span data-ttu-id="5888c-121">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5888c-121">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
