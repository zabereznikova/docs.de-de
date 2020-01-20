---
title: 'Vorgehensweise: Sortieren von Elementen (C#)'
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7fad9fcb43905072c88a5704c56672917bfc377c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347363"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="e0a75-102">Vorgehensweise: Sortieren von Elementen (C#)</span><span class="sxs-lookup"><span data-stu-id="e0a75-102">How to sort elements (C#)</span></span>
<span data-ttu-id="e0a75-103">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage schreiben können, die ihre Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="e0a75-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0a75-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0a75-104">Example</span></span>  
 <span data-ttu-id="e0a75-105">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0a75-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e0a75-106">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e0a75-106">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="e0a75-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0a75-107">Example</span></span>  
 <span data-ttu-id="e0a75-108">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0a75-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e0a75-109">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0a75-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e0a75-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e0a75-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e0a75-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e0a75-111">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0a75-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0a75-112">See also</span></span>

- [<span data-ttu-id="e0a75-113">Sorting Data (C#) (Sortieren von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="e0a75-113">Sorting Data (C#)</span></span>](./sorting-data.md)
