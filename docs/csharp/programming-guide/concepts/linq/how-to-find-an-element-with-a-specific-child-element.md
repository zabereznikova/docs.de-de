---
title: 'Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (C#)'
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141142"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="44df3-102">Vorgehensweise: Suchen nach einem Element mit einem bestimmten untergeordneten Element (C#)</span><span class="sxs-lookup"><span data-stu-id="44df3-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="44df3-103">In diesem Thema wird gezeigt, wie Sie nach einem bestimmten Element suchen können, das ein untergeordnetes Element mit einem bestimmten Wert besitzt.</span><span class="sxs-lookup"><span data-stu-id="44df3-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44df3-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44df3-104">Example</span></span>  
 <span data-ttu-id="44df3-105">Das Beispiel sucht nach dem `Test`-Element, das ein untergeordnetes `CommandLine`-Element mit dem Wert "Examp2.EXE" besitzt.</span><span class="sxs-lookup"><span data-stu-id="44df3-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="44df3-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="44df3-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="44df3-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="44df3-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="44df3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="44df3-108">Example</span></span>  
 <span data-ttu-id="44df3-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="44df3-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="44df3-110">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="44df3-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="44df3-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Testkonfiguration in einem Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span><span class="sxs-lookup"><span data-stu-id="44df3-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="44df3-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="44df3-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="44df3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44df3-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="44df3-114">Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))</span><span class="sxs-lookup"><span data-stu-id="44df3-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="44df3-115">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="44df3-115">Projection Operations (C#)</span></span>](./projection-operations.md)
