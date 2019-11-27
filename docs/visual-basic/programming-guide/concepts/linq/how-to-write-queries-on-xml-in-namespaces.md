---
title: 'Gewusst wie: Schreiben von XML-Abfragen in Namespaces'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 496cf8daf5136e8aafff000312bbd730a5152e9f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344470"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="01e67-102">Gewusst wie: Schreiben von Abfragen für XML in Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e67-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="01e67-103">Wenn Sie eine Abfrage für XML in einem Namespace schreiben möchten, müssen Sie <xref:System.Xml.Linq.XName>-Objekte verwenden, die den richtigen Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="01e67-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="01e67-104">In Visual Basic wird meist ein globaler Namespace definiert, und anschließend werden XML-Literale und XML-Eigenschaften verwendet, die den globalen Namespace nutzen.</span><span class="sxs-lookup"><span data-stu-id="01e67-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="01e67-105">Sie können einen globalen Standardnamespace definieren. Die Elemente in den XML-Literalen sind dann standardmäßig im Namespace vorhanden.</span><span class="sxs-lookup"><span data-stu-id="01e67-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="01e67-106">Stattdessen können Sie auch einen globalen Namespace mit einem Präfix definieren und dann das Präfix den Anforderungen entsprechend in den XML-Literalen und in den XML-Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="01e67-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="01e67-107">Wie bei anderen XML-Formen auch befinden sich Attribute standardmäßig nicht in einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="01e67-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="01e67-108">Die erste Gruppe der Beispiele in diesem Thema zeigt,wie Sie eine XML-Struktur in einem Standardnamespace erstellen.</span><span class="sxs-lookup"><span data-stu-id="01e67-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="01e67-109">Die zweite Gruppe der Beispiele zeigt, wie Sie eine XML-Struktur in einem Namespace mit einem Präfix erstellen.</span><span class="sxs-lookup"><span data-stu-id="01e67-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01e67-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01e67-110">Example</span></span>  
 <span data-ttu-id="01e67-111">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Standardnamespace befindet.</span><span class="sxs-lookup"><span data-stu-id="01e67-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="01e67-112">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="01e67-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="01e67-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="01e67-113">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="01e67-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01e67-114">Example</span></span>  
 <span data-ttu-id="01e67-115">In Visual Basic unterscheidet sich das Schreiben von Abfragen für eine XML-Struktur, die einen Namespace mit einem Präfix verwendet, jedoch recht stark vom Abfragen einer XML-Struktur in einem Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="01e67-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="01e67-116">Normalerweise verwenden Sie die `Imports`-Anweisung, um den Namespace mit einem Präfix zu importieren.</span><span class="sxs-lookup"><span data-stu-id="01e67-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="01e67-117">Anschließend können Sie das Präfix beim Erstellen der XML-Struktur in den Element- und Attributnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="01e67-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="01e67-118">Sie können das Präfix auch beim Abfragen einer XML-Struktur mithilfe von XML-Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="01e67-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="01e67-119">Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Namespace mit einem Präfix befindet.</span><span class="sxs-lookup"><span data-stu-id="01e67-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="01e67-120">Anschließend ruft das Beispiel eine Auflistung der Elemente ab.</span><span class="sxs-lookup"><span data-stu-id="01e67-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="01e67-121">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="01e67-121">This example produces the following output:</span></span>  
  
```console  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="01e67-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01e67-122">See also</span></span>

- [<span data-ttu-id="01e67-123">Übersicht über Namespaces (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01e67-123">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
