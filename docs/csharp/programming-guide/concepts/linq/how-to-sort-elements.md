---
title: 'Vorgehensweise: Sortieren von Elementen (C#)'
description: Erfahren Sie, wie Sie Elemente sortieren. Hier finden Sie Beispiele dafür, wie Sie eine Abfrage schreiben, die ihre Ergebnisse in einem XML-Dokument sortiert.
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 669d9cf583e6ab70c93be39ad271eaf104f88718
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301436"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="0b908-104">Vorgehensweise: Sortieren von Elementen (C#)</span><span class="sxs-lookup"><span data-stu-id="0b908-104">How to sort elements (C#)</span></span>
<span data-ttu-id="0b908-105">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage schreiben können, die ihre Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="0b908-105">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b908-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b908-106">Example</span></span>  
 <span data-ttu-id="0b908-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0b908-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="0b908-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0b908-108">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="0b908-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0b908-109">Example</span></span>  
 <span data-ttu-id="0b908-110">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0b908-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0b908-111">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0b908-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="0b908-112">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="0b908-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="0b908-113">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0b908-113">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b908-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b908-114">See also</span></span>

- [<span data-ttu-id="0b908-115">Sorting Data (C#) (Sortieren von Daten (C#))</span><span class="sxs-lookup"><span data-stu-id="0b908-115">Sorting Data (C#)</span></span>](./sorting-data.md)
