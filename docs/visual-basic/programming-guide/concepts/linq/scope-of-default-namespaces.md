---
title: Bereich von Standardnamespaces in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 138115cb1a5ec2e2c513419a32a9ebaec9c90d61
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="567d1-102">Bereich von Standardnamespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="567d1-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="567d1-103">Standardnamespaces, wie sie in der XML-Struktur dargestellt werden, befinden sich bei Abfragen nicht innerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="567d1-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="567d1-104">Bei XML, die in einem Standardnamespace befindet, noch müssen Sie deklarieren eine <xref:System.Xml.Linq.XNamespace>Variable, und kombinieren Sie diese mit dem lokalen Namen, um einen qualifizierten Namen in der Abfrage verwendet werden kann.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="567d1-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="567d1-105">Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="567d1-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="567d1-106">Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen, dann jedoch nicht ordnungsgemäß abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="567d1-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="567d1-107">Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="567d1-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="567d1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="567d1-108">Example</span></span>  
 <span data-ttu-id="567d1-109">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="567d1-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="567d1-110">Code</span><span class="sxs-lookup"><span data-stu-id="567d1-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
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
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="567d1-111">Kommentare</span><span class="sxs-lookup"><span data-stu-id="567d1-111">Comments</span></span>  
 <span data-ttu-id="567d1-112">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="567d1-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="567d1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="567d1-113">Example</span></span>  
 <span data-ttu-id="567d1-114">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.</span><span class="sxs-lookup"><span data-stu-id="567d1-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="567d1-115">Im Gegensatz zum falsch codierten Beispiel oben wird der richtige Ansatz bei Verwendung von Visual Basic deklarieren und initialisieren einen globalen Standardnamespace ist.</span><span class="sxs-lookup"><span data-stu-id="567d1-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="567d1-116">Dadurch werden alle XML-Eigenschaften im Standardnamespace platziert.</span><span class="sxs-lookup"><span data-stu-id="567d1-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="567d1-117">Weitere Änderungen sind für das ordnungsgemäße Funktionieren des Beispiels nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="567d1-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="567d1-118">Code</span><span class="sxs-lookup"><span data-stu-id="567d1-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
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
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="567d1-119">Kommentare</span><span class="sxs-lookup"><span data-stu-id="567d1-119">Comments</span></span>  
 <span data-ttu-id="567d1-120">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="567d1-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="567d1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="567d1-121">See Also</span></span>  
 [<span data-ttu-id="567d1-122">Arbeiten mit XML-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="567d1-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
