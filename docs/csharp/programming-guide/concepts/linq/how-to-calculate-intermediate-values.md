---
title: 'Vorgehensweise: Berechnen von Zwischenwerten (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 15ccf58738b64ebfaef77deb162ddb29db0ae33a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259729"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="b4248-102">Vorgehensweise: Berechnen von Zwischenwerten (C#)</span><span class="sxs-lookup"><span data-stu-id="b4248-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="b4248-103">In diesem Beispiel wird das Berechnen von Zwischenwerten gezeigt, die zum Sortieren, Filtern und Auswählen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="b4248-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4248-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4248-104">Example</span></span>  
 <span data-ttu-id="b4248-105">Im folgenden Beispiel kommt die `Let`-Klausel zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="b4248-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="b4248-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b4248-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="b4248-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b4248-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="b4248-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4248-108">Example</span></span>  
 <span data-ttu-id="b4248-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b4248-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b4248-110">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b4248-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b4248-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b4248-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="b4248-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b4248-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="b4248-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4248-113">See Also</span></span>

- [<span data-ttu-id="b4248-114">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="b4248-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
