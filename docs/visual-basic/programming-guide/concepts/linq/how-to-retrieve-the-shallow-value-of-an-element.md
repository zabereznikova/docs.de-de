---
title: 'Gewusst wie: Abrufen den flachen Wert eines Elements (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 730a6670-fb8c-41fc-8a1b-eb97a837e432
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: c313f1f13e2dc3cc42d182b3c9542a46f2f4d831
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-visual-basic"></a><span data-ttu-id="f8d78-102">Gewusst wie: Abrufen den flachen Wert eines Elements (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8d78-102">How to: Retrieve the Shallow Value of an Element (Visual Basic)</span></span>
<span data-ttu-id="f8d78-103">In diesem Thema wird gezeigt, wie Sie den flachen Wert eines Elements abrufen.</span><span class="sxs-lookup"><span data-stu-id="f8d78-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="f8d78-104">Der flache Wert ist ausschließlich der Wert des jeweiligen Elements, im Gegensatz zum tiefen Wert, der die Werte aller Nachfolgerelemente enthält, die zu einer einzelnen Zeichenkette verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="f8d78-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="f8d78-105">Beim Abrufen eines Elementwerts mithilfe des Umwandlungsverfahrens oder der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>-Eigenschaft der Tiefen Wert abgerufen.</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f8d78-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property, you retrieve the deep value.</span></span> <span data-ttu-id="f8d78-106">Um den flachen Wert abzurufen, können Sie die `ShallowValue`-Erweiterungsmethode verwenden, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8d78-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="f8d78-107">Das Abrufen des flachen Werts ist nützlich, wenn Sie Elemente anhand ihrer Inhalte auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8d78-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="f8d78-108">Im folgenden Beispiel wird eine Erweiterungsmethode deklariert, die den flachen Wert eines Elements abruft.</span><span class="sxs-lookup"><span data-stu-id="f8d78-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="f8d78-109">Anschließend wird die Erweiterungsmethode in einer Abfrage verwendet, um alle Elemente aufzulisten, die einen berechneten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8d78-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d78-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d78-110">Example</span></span>  
 <span data-ttu-id="f8d78-111">In diesem Beispiel wird die folgende Textdatei, Report.xml, als Quelldatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8d78-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```vb  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function ShallowValue(ByVal xe As XElement)  
        Return xe _  
               .Nodes() _  
               .OfType(Of XText)() _  
               .Aggregate(New StringBuilder(), _  
                              Function(s, c) s.Append(c), _  
                              Function(s) s.ToString())  
    End Function  
  
    Sub Main()  
        Dim root As XElement = XElement.Load("Report.xml")  
  
        Dim query As IEnumerable(Of XElement) = _  
            From el In root.Descendants() _  
            Where (el.ShallowValue().StartsWith("=")) _  
            Select el  
  
        For Each q As XElement In query  
            Console.WriteLine("{0}{1}{2}", _  
                q.Name.ToString().PadRight(8), _  
                q.Attribute("Name").ToString().PadRight(20), _  
                q.ShallowValue())  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="f8d78-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f8d78-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8d78-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8d78-113">See Also</span></span>  
 [<span data-ttu-id="f8d78-114">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f8d78-114">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
