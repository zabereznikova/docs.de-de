---
title: 'Vorgehensweise: Suchen nach untergeordneten Elementen, die anhand der Position (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
ms.openlocfilehash: 57b9f3d7986bd85a65716c833165e7b073414ef0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831604"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="53114-102">Vorgehensweise: Suchen nach untergeordneten Elementen, die anhand der Position (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53114-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="53114-103">Es kann passieren, dass Sie Elemente anhand ihrer Position ermitteln,</span><span class="sxs-lookup"><span data-stu-id="53114-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="53114-104">also z. B. das zweite oder das dritte bis fünfte Element finden möchten.</span><span class="sxs-lookup"><span data-stu-id="53114-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="53114-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="53114-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="53114-106">Für das Schreiben dieser [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage mit verzögerter Auswertung gibt es zwei Ansätze:</span><span class="sxs-lookup"><span data-stu-id="53114-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="53114-107">Sie können entweder die Operatoren <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> verwenden, oder Sie können die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, die einen Index akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="53114-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="53114-108">Wenn Sie die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, verwenden Sie einen Lambdaausdruck, der zwei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="53114-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="53114-109">Im folgenden Beispiel werden beide Methoden für die positionsbasierte Auswahl gezeigt:</span><span class="sxs-lookup"><span data-stu-id="53114-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53114-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53114-110">Example</span></span>  
 <span data-ttu-id="53114-111">Dieses Beispiel ermittelt das zweite bis vierte `Test`-Element.</span><span class="sxs-lookup"><span data-stu-id="53114-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="53114-112">Das Ergebnis ist eine Auflistung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="53114-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="53114-113">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="53114-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim testCfg As XElement = XElement.Load("TestConfig.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test").Skip(1).Take(3)  
  
'LINQ to XML query  
Dim list2 As IEnumerable(Of XElement) = _  
    testCfg.Elements("Test"). _  
    Where(Function(ByVal el, ByVal idx) idx >= 1 And idx <= 3)  
  
' XPath expression  
Dim list3 As IEnumerable(Of XElement) = _  
    testCfg.XPathSelectElements("Test[position() >= 2 and position() <= 4]")  
  
If list1.Count() = list2.Count() And _  
       list1.Count() = list3.Count() And _  
       list1.Intersect(list2).Count() = list1.Count() And _  
       list1.Intersect(list3).Count() = list1.Count() Then  
  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="53114-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="53114-114">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Test TestId="0002" TestType="CMD">  
  <Name>Find succeeding characters</Name>  
  <CommandLine>Examp2.EXE</CommandLine>  
  <Input>abc</Input>  
  <Output>def</Output>  
</Test>  
<Test TestId="0003" TestType="GUI">  
  <Name>Convert multiple numbers to strings</Name>  
  <CommandLine>Examp2.EXE /Verbose</CommandLine>  
  <Input>123</Input>  
  <Output>One Two Three</Output>  
</Test>  
<Test TestId="0004" TestType="GUI">  
  <Name>Find correlated key</Name>  
  <CommandLine>Examp3.EXE</CommandLine>  
  <Input>a1</Input>  
  <Output>b1</Output>  
</Test>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53114-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53114-115">See also</span></span>

- [<span data-ttu-id="53114-116">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53114-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
