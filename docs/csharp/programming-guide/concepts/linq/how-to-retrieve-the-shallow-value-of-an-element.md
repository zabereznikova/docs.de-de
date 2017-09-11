---
title: 'Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#)'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aad07fdba1d3df2b72f867e6845536300031146b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="b6c29-102">Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#)</span><span class="sxs-lookup"><span data-stu-id="b6c29-102">How to: Retrieve the Shallow Value of an Element (C#)</span></span>
<span data-ttu-id="b6c29-103">In diesem Thema wird gezeigt, wie Sie den flachen Wert eines Elements abrufen.</span><span class="sxs-lookup"><span data-stu-id="b6c29-103">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="b6c29-104">Der flache Wert ist ausschließlich der Wert des jeweiligen Elements, im Gegensatz zum tiefen Wert, der die Werte aller Nachfolgerelemente enthält, die zu einer einzelnen Zeichenkette verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="b6c29-104">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="b6c29-105">Beim Abrufen des Elementwerts mithilfe des Umwandlungsverfahrens oder der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>-Eigenschaft wird der tiefe Wert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b6c29-105">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property, you retrieve the deep value.</span></span> <span data-ttu-id="b6c29-106">Um den flachen Wert abzurufen, können Sie die `ShallowValue`-Erweiterungsmethode verwenden, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b6c29-106">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the follwing example.</span></span> <span data-ttu-id="b6c29-107">Das Abrufen des flachen Werts ist nützlich, wenn Sie Elemente anhand ihrer Inhalte auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="b6c29-107">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="b6c29-108">Im folgenden Beispiel wird eine Erweiterungsmethode deklariert, die den flachen Wert eines Elements abruft.</span><span class="sxs-lookup"><span data-stu-id="b6c29-108">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="b6c29-109">Anschließend wird die Erweiterungsmethode in einer Abfrage verwendet, um alle Elemente aufzulisten, die einen berechneten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="b6c29-109">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6c29-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6c29-110">Example</span></span>  
 <span data-ttu-id="b6c29-111">In diesem Beispiel wird die folgende Textdatei, Report.xml, als Quelldatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="b6c29-111">The following text file, Report.xml, is the source for this example.</span></span>  
  
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
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="b6c29-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b6c29-112">This example produces the following output:</span></span>  
  
```  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6c29-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b6c29-113">See Also</span></span>  
 [<span data-ttu-id="b6c29-114">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="b6c29-114">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

