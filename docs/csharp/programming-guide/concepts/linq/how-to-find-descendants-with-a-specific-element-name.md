---
title: 'Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)'
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: f95551f0c1506a56474d497622b90090cc4c8865
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="c4ba5-102">Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)</span><span class="sxs-lookup"><span data-stu-id="c4ba5-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="c4ba5-103">Es kann vorkommen, dass Sie alle Nachfolgerelemente mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="c4ba5-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="c4ba5-104">Dazu könnten Sie Code schreiben, der alle Nachfolgerelemente durchläuft, einfacher ist es aber, die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4ba5-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4ba5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4ba5-105">Example</span></span>  
 <span data-ttu-id="c4ba5-106">Im folgenden Beispiel wird gezeigt, wie Sie Nachfolgerelemente anhand des Elementnamens ermitteln können:</span><span class="sxs-lookup"><span data-stu-id="c4ba5-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c4ba5-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c4ba5-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="c4ba5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4ba5-108">Example</span></span>  
 <span data-ttu-id="c4ba5-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4ba5-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c4ba5-110">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="c4ba5-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="c4ba5-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c4ba5-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4ba5-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4ba5-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 [<span data-ttu-id="c4ba5-113">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="c4ba5-113">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
