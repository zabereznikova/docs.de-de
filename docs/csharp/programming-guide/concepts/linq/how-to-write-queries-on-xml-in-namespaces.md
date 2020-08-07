---
title: 'Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)'
description: Erfahren Sie, wie Sie Abfragen für XML in Namespaces schreiben. Für solche Abfragen müssen Sie XName-Objekte mit dem richtigen Namespace verwenden.
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: 64eb9df1cde3b434a11e2e5410aab96993dc0fa1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303178"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="789be-104">Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)</span><span class="sxs-lookup"><span data-stu-id="789be-104">How to write queries on XML in namespaces (C#)</span></span>
<span data-ttu-id="789be-105">Wenn Sie eine Abfrage für XML in einem Namespace schreiben möchten, müssen Sie <xref:System.Xml.Linq.XName>-Objekte verwenden, die den richtigen Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="789be-105">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="789be-106">In C# besteht der am häufigsten verwendete Ansatz darin, einen <xref:System.Xml.Linq.XNamespace> mit einer Zeichenfolge zu initialisieren, die den URI enthält, und dann mithilfe der Additionsoperatorüberladung den Namespace mit dem lokalen Namen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="789be-106">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="789be-107">Die erste Gruppe der Beispiele in diesem Thema zeigt,wie Sie eine XML-Struktur in einem Standardnamespace erstellen.</span><span class="sxs-lookup"><span data-stu-id="789be-107">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="789be-108">Die zweite Gruppe der Beispiele zeigt, wie Sie eine XML-Struktur in einem Namespace mit einem Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="789be-108">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="789be-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="789be-109">Example</span></span>  
 <span data-ttu-id="789be-110">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Standardnamespace befindet.</span><span class="sxs-lookup"><span data-stu-id="789be-110">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="789be-111">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="789be-111">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="789be-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="789be-112">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="789be-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="789be-113">Example</span></span>  
 <span data-ttu-id="789be-114">In C# schreiben Sie Abfragen auf die gleiche Weise. Dies gilt unabhängig davon, ob Sie Abfragen für eine XML-Struktur schreiben, die einen Namespace mit einem Präfix verwendet, oder für eine XML-Struktur mit einem Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="789be-114">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="789be-115">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Namespace mit einem Präfix befindet.</span><span class="sxs-lookup"><span data-stu-id="789be-115">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="789be-116">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="789be-116">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="789be-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="789be-117">This example produces the following output:</span></span>  
  
```output  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="789be-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="789be-118">See also</span></span>

- [<span data-ttu-id="789be-119">Namespaces: Übersicht (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="789be-119">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
