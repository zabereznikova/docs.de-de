---
title: 'Gewusst wie: Schreiben eine Abfrage, die Elemente anhand des Kontexts (Visual Basic) sucht | Microsoft-Dokumentation'
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
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fd497c4d63c59eed1873f77f474bfb76eb0194c4
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="691e2-102">Gewusst wie: Schreiben eine Abfrage, die Elemente anhand des Kontexts (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="691e2-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="691e2-103">Es kann vorkommen, dass Sie eine Abfrage schreiben möchten, die Elemente auf der Grundlage ihres Kontexts sucht.</span><span class="sxs-lookup"><span data-stu-id="691e2-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="691e2-104">Dabei soll die Filterung auf den vorausgehenden oder folgenden nebengeordneten Elementen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="691e2-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="691e2-105">Außerdem möchten Sie vielleicht auch nach untergeordneten oder indirekt übergeordneten Elementen filtern.</span><span class="sxs-lookup"><span data-stu-id="691e2-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="691e2-106">Um dies zu bewerkstelligen, können Sie eine Abfrage schreiben und die Ergebnisse dieser Abfrage in der `where`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="691e2-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="691e2-107">Wenn Sie zunächst eine Prüfung auf NULL-Werte vornehmen müssen und dann den Wert testen, empfiehlt es sich, die Abfrage in einer `let`-Klausel durchzuführen und die Ergebnisse dann in der `where`-Klausel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="691e2-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="691e2-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="691e2-108">Example</span></span>  
 <span data-ttu-id="691e2-109">Im folgenden Beispiel werden alle `p`-Elemente ausgewählt, die sofort von einem `ul`-Element gefolgt werden.</span><span class="sxs-lookup"><span data-stu-id="691e2-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
  
```  
  
 <span data-ttu-id="691e2-110">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="691e2-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="691e2-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="691e2-111">Example</span></span>  
 <span data-ttu-id="691e2-112">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="691e2-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="691e2-113">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="691e2-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="691e2-114">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="691e2-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="691e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="691e2-115">See Also</span></span>  
 <span data-ttu-id="691e2-116"><xref:System.Xml.Linq.XElement.Parse%2A></xref:System.Xml.Linq.XElement.Parse%2A></span><span class="sxs-lookup"><span data-stu-id="691e2-116"><xref:System.Xml.Linq.XElement.Parse%2A></span></span>   
 <span data-ttu-id="691e2-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="691e2-117"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>   
 <span data-ttu-id="691e2-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="691e2-118"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>   
 <span data-ttu-id="691e2-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></xref:System.Linq.Enumerable.FirstOrDefault%2A></span><span class="sxs-lookup"><span data-stu-id="691e2-119"><xref:System.Linq.Enumerable.FirstOrDefault%2A></span></span>   
<span data-ttu-id="691e2-120"> [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="691e2-120"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span></span>
