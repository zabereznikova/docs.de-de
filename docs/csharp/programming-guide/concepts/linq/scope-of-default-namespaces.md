---
title: Bereich von Standardnamespaces in C#
description: Erfahren Sie, wie Sie Abfragen in XML-Standardnamespaces in LINQ to XML in C# durchführen. Verwenden Sie eine XNamespace-Variable und den lokalen Namen, um einen qualifizierten Namen für die Abfrage anzugeben.
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 912e47099f89daa9b80ac58b422d39d598509ac9
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302398"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="66ba8-104">Bereich von Standardnamespaces in C\#</span><span class="sxs-lookup"><span data-stu-id="66ba8-104">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="66ba8-105">Standardnamespaces, wie sie in der XML-Struktur dargestellt werden, befinden sich bei Abfragen nicht innerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="66ba8-105">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="66ba8-106">Bei XML, das sich in einem Standardnamespace befindet, müssen Sie weiterhin eine <xref:System.Xml.Linq.XNamespace>-Variable deklarieren und diese Variable mit dem lokalen Namen kombinieren, um einen qualifizierten Namen zu erhalten, der in der Abfrage verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="66ba8-106">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="66ba8-107">Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="66ba8-107">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="66ba8-108">Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen, dann jedoch nicht ordnungsgemäß abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="66ba8-108">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="66ba8-109">Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="66ba8-109">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66ba8-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66ba8-110">Example</span></span>  
 <span data-ttu-id="66ba8-111">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="66ba8-111">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="66ba8-112">Code</span><span class="sxs-lookup"><span data-stu-id="66ba8-112">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="66ba8-113">Kommentare</span><span class="sxs-lookup"><span data-stu-id="66ba8-113">Comments</span></span>  
 <span data-ttu-id="66ba8-114">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="66ba8-114">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="66ba8-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66ba8-115">Example</span></span>  
 <span data-ttu-id="66ba8-116">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.</span><span class="sxs-lookup"><span data-stu-id="66ba8-116">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="66ba8-117">Im Gegensatz zum falsch codierten Beispiel oben besteht der richtige Ansatz bei Verwendung von C# darin, ein <xref:System.Xml.Linq.XNamespace>-Objekt zu deklarieren und zu initialisieren und dieses beim Angeben von <xref:System.Xml.Linq.XName>-Objekten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="66ba8-117">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="66ba8-118">In diesem Fall ist das Argument der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode ein <xref:System.Xml.Linq.XName>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="66ba8-118">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="66ba8-119">Code</span><span class="sxs-lookup"><span data-stu-id="66ba8-119">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="66ba8-120">Kommentare</span><span class="sxs-lookup"><span data-stu-id="66ba8-120">Comments</span></span>  
 <span data-ttu-id="66ba8-121">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="66ba8-121">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="66ba8-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66ba8-122">See also</span></span>

- [<span data-ttu-id="66ba8-123">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="66ba8-123">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
