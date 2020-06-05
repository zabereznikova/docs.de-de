---
title: 'Vorgehensweise: Ermitteln untergeordneter Elemente anhand der Position (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 6831e1db-5e97-444f-a7a1-d0a87104b005
ms.openlocfilehash: d6dd1150ae3e4ad586e476b777b1f7d47d60c261
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84405260"
---
# <a name="how-to-find-child-elements-based-on-position-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="f3691-102">Gewusst wie: Suchen nach untergeordneten Elementen auf der Grundlage der Position (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3691-102">How to: Find Child Elements Based on Position (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f3691-103">Es kann passieren, dass Sie Elemente anhand ihrer Position ermitteln,</span><span class="sxs-lookup"><span data-stu-id="f3691-103">Sometimes you want to find elements based on their position.</span></span> <span data-ttu-id="f3691-104">also z. B. das zweite oder das dritte bis fünfte Element finden möchten.</span><span class="sxs-lookup"><span data-stu-id="f3691-104">You might want to find the second element, or you might want to find the third through the fifth element.</span></span>  
  
 <span data-ttu-id="f3691-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="f3691-105">The XPath expression is:</span></span>  
  
 `Test[position() >= 2 and position() <= 4]`  
  
 <span data-ttu-id="f3691-106">Für das Schreiben dieser [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage mit verzögerter Auswertung gibt es zwei Ansätze:</span><span class="sxs-lookup"><span data-stu-id="f3691-106">There are two approaches to writing this [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query in a lazy way.</span></span> <span data-ttu-id="f3691-107">Sie können entweder die Operatoren <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> verwenden, oder Sie können die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, die einen Index akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f3691-107">You can use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> operators, or you can use the <xref:System.Linq.Enumerable.Where%2A> overload that takes an index.</span></span> <span data-ttu-id="f3691-108">Wenn Sie die <xref:System.Linq.Enumerable.Where%2A>-Überladung verwenden, verwenden Sie einen Lambdaausdruck, der zwei Argumente akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="f3691-108">When you use the <xref:System.Linq.Enumerable.Where%2A> overload, you use a lambda expression that takes two arguments.</span></span> <span data-ttu-id="f3691-109">Im folgenden Beispiel werden beide Methoden für die positionsbasierte Auswahl gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f3691-109">The following example shows both methods of selecting based on position.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3691-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3691-110">Example</span></span>  
 <span data-ttu-id="f3691-111">Dieses Beispiel ermittelt das zweite bis vierte `Test`-Element.</span><span class="sxs-lookup"><span data-stu-id="f3691-111">This example finds the second through the fourth `Test` element.</span></span> <span data-ttu-id="f3691-112">Das Ergebnis ist eine Auflistung von Elementen.</span><span class="sxs-lookup"><span data-stu-id="f3691-112">The result is a collection of elements.</span></span>  
  
 <span data-ttu-id="f3691-113">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f3691-113">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="f3691-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f3691-114">This example produces the following output:</span></span>  
  
```console  
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
  
## <a name="see-also"></a><span data-ttu-id="f3691-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3691-115">See also</span></span>

- [<span data-ttu-id="f3691-116">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3691-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
