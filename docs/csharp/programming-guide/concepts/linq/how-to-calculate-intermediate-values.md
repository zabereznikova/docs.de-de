---
title: 'Vorgehensweise: Berechnen von Zwischenwerten (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fe3f992e85b3fb508fced943e1428a4fb6ae2490
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205384"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="04177-102">Vorgehensweise: Berechnen von Zwischenwerten (C#)</span><span class="sxs-lookup"><span data-stu-id="04177-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="04177-103">In diesem Beispiel wird das Berechnen von Zwischenwerten gezeigt, die zum Sortieren, Filtern und Auswählen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="04177-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04177-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04177-104">Example</span></span>  
 <span data-ttu-id="04177-105">Im folgenden Beispiel kommt die `Let`-Klausel zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="04177-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="04177-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="04177-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="04177-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="04177-107">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="04177-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04177-108">Example</span></span>  
 <span data-ttu-id="04177-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="04177-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="04177-110">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="04177-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="04177-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="04177-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="04177-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="04177-112">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
