---
title: 'Vorgehensweise: Berechnen von Zwischenwerten (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 7b2dfc4e26fc7648cbd93b1e590079e4b105ad43
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594131"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="849d3-102">Vorgehensweise: Berechnen von Zwischenwerten (C#)</span><span class="sxs-lookup"><span data-stu-id="849d3-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="849d3-103">In diesem Beispiel wird das Berechnen von Zwischenwerten gezeigt, die zum Sortieren, Filtern und Auswählen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="849d3-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="849d3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="849d3-104">Example</span></span>  
 <span data-ttu-id="849d3-105">Im folgenden Beispiel kommt die `Let`-Klausel zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="849d3-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="849d3-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="849d3-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="849d3-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="849d3-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="849d3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="849d3-108">Example</span></span>  
 <span data-ttu-id="849d3-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="849d3-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="849d3-110">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="849d3-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="849d3-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="849d3-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="849d3-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="849d3-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
