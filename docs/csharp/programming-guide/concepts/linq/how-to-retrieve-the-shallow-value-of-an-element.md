---
title: 'Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#)'
description: Erfahren Sie, wie Sie den Shallow-Wert eines Elements abrufen. Der Shallow-Wert gilt nur für dieses spezifische Element.
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 597859e5b66606aa0cff9c1a475e79e6b66c39fc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301579"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="e7c42-104">Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#)</span><span class="sxs-lookup"><span data-stu-id="e7c42-104">How to retrieve the shallow value of an element (C#)</span></span>
<span data-ttu-id="e7c42-105">In diesem Thema wird gezeigt, wie Sie den flachen Wert eines Elements abrufen.</span><span class="sxs-lookup"><span data-stu-id="e7c42-105">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="e7c42-106">Der flache Wert ist ausschließlich der Wert des jeweiligen Elements, im Gegensatz zum tiefen Wert, der die Werte aller Nachfolgerelemente enthält, die zu einer einzelnen Zeichenkette verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="e7c42-106">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="e7c42-107">Beim Abrufen des Elementwerts mithilfe des Umwandlungsverfahrens oder der <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>-Eigenschaft wird der tiefe Wert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e7c42-107">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="e7c42-108">Um den flachen Wert abzurufen, können Sie die `ShallowValue`-Erweiterungsmethode verwenden, wie im folgenden Beispiel gezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e7c42-108">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="e7c42-109">Das Abrufen des flachen Werts ist nützlich, wenn Sie Elemente anhand ihrer Inhalte auswählen möchten.</span><span class="sxs-lookup"><span data-stu-id="e7c42-109">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="e7c42-110">Im folgenden Beispiel wird eine Erweiterungsmethode deklariert, die den flachen Wert eines Elements abruft.</span><span class="sxs-lookup"><span data-stu-id="e7c42-110">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="e7c42-111">Anschließend wird die Erweiterungsmethode in einer Abfrage verwendet, um alle Elemente aufzulisten, die einen berechneten Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7c42-111">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7c42-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7c42-112">Example</span></span>  
 <span data-ttu-id="e7c42-113">In diesem Beispiel wird die folgende Textdatei, Report.xml, als Quelldatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="e7c42-113">The following text file, Report.xml, is the source for this example.</span></span>  
  
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
  
 <span data-ttu-id="e7c42-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e7c42-114">This example produces the following output:</span></span>  
  
```output  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7c42-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7c42-115">See also</span></span>

- [<span data-ttu-id="e7c42-116">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="e7c42-116">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
