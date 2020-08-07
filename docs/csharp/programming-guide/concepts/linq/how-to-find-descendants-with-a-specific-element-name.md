---
title: 'Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)'
description: Erfahren Sie, wie Sie über die Descendants-Achse alle Nachfolgerelemente mit einem bestimmten Namen suchen. Hier finden Sie Codebeispiele und weitere Ressourcen.
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: 96ebf2d10a9ed5e07aab2870142f9869903ad442
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303243"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="769cc-104">Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)</span><span class="sxs-lookup"><span data-stu-id="769cc-104">How to find descendants with a specific element name (C#)</span></span>
<span data-ttu-id="769cc-105">Es kann vorkommen, dass Sie alle Nachfolgerelemente mit einem bestimmten Namen ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="769cc-105">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="769cc-106">Dazu könnten Sie Code schreiben, der alle Nachfolgerelemente durchläuft, einfacher ist es aber, die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="769cc-106">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="769cc-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="769cc-107">Example</span></span>  
 <span data-ttu-id="769cc-108">Im folgenden Beispiel wird gezeigt, wie Sie Nachfolgerelemente anhand des Elementnamens ermitteln können:</span><span class="sxs-lookup"><span data-stu-id="769cc-108">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="769cc-109">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="769cc-109">This code produces the following output:</span></span>  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="769cc-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="769cc-110">Example</span></span>  
 <span data-ttu-id="769cc-111">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="769cc-111">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="769cc-112">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="769cc-112">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="769cc-113">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="769cc-113">This code produces the following output:</span></span>  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="769cc-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="769cc-114">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
