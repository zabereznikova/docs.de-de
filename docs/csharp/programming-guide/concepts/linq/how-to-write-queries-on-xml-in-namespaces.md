---
title: 'Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)'
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: a8b8d55daaad1ae00e43fed897080ed7a62fafab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75337371"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="3b384-102">Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)</span><span class="sxs-lookup"><span data-stu-id="3b384-102">How to write queries on XML in namespaces (C#)</span></span>
<span data-ttu-id="3b384-103">Wenn Sie eine Abfrage für XML in einem Namespace schreiben möchten, müssen Sie <xref:System.Xml.Linq.XName>-Objekte verwenden, die den richtigen Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b384-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="3b384-104">In C# besteht der am häufigsten verwendete Ansatz darin, einen <xref:System.Xml.Linq.XNamespace> mit einer Zeichenfolge zu initialisieren, die den URI enthält, und dann mithilfe der Additionsoperatorüberladung den Namespace mit dem lokalen Namen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="3b384-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="3b384-105">Die erste Gruppe der Beispiele in diesem Thema zeigt,wie Sie eine XML-Struktur in einem Standardnamespace erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b384-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="3b384-106">Die zweite Gruppe der Beispiele zeigt, wie Sie eine XML-Struktur in einem Namespace mit einem Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b384-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b384-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b384-107">Example</span></span>  
 <span data-ttu-id="3b384-108">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Standardnamespace befindet.</span><span class="sxs-lookup"><span data-stu-id="3b384-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="3b384-109">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="3b384-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
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
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="3b384-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3b384-110">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="3b384-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b384-111">Example</span></span>  
 <span data-ttu-id="3b384-112">In C# schreiben Sie Abfragen auf die gleiche Weise. Dies gilt unabhängig davon, ob Sie Abfragen für eine XML-Struktur schreiben, die einen Namespace mit einem Präfix verwendet, oder für eine XML-Struktur mit einem Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="3b384-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="3b384-113">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Namespace mit einem Präfix befindet.</span><span class="sxs-lookup"><span data-stu-id="3b384-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="3b384-114">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="3b384-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="3b384-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3b384-115">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="3b384-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b384-116">See also</span></span>

- [<span data-ttu-id="3b384-117">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3b384-117">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
