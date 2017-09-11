---
title: 'Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (C#)'
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
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: dcbfe8efb16dd5e672deeac2fffea109689dacc5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="64fa5-102">Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (C#)</span><span class="sxs-lookup"><span data-stu-id="64fa5-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="64fa5-103">In diesem Thema wird gezeigt, wie Sie nach einem bestimmten Element suchen können, das ein untergeordnetes Element mit einem bestimmten Wert besitzt.</span><span class="sxs-lookup"><span data-stu-id="64fa5-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64fa5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64fa5-104">Example</span></span>  
 <span data-ttu-id="64fa5-105">Das Beispiel sucht nach dem `Test`-Element, das ein untergeordnetes `CommandLine`-Element mit dem Wert "Examp2.EXE" besitzt.</span><span class="sxs-lookup"><span data-stu-id="64fa5-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="64fa5-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="64fa5-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="64fa5-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="64fa5-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="64fa5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64fa5-108">Example</span></span>  
 <span data-ttu-id="64fa5-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64fa5-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="64fa5-110">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="64fa5-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="64fa5-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel XML-Datei: Testkonfiguration in einem Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="64fa5-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="64fa5-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="64fa5-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="64fa5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64fa5-113">See Also</span></span>  
 <span data-ttu-id="64fa5-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="64fa5-114"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="64fa5-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="64fa5-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
 <span data-ttu-id="64fa5-116">[Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="64fa5-116">[Basic Queries (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
 <span data-ttu-id="64fa5-117">[Übersicht über Standardabfrageoperatoren (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="64fa5-117">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="64fa5-118">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="64fa5-118">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)

