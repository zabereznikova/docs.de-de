---
title: 'Vorgehensweise: Schreiben einer Abfrage, die Elemente basierend auf dem Kontext sucht (C#)'
ms.date: 07/20/2015
ms.assetid: 3ff79ef0-fc8b-42fe-8cc0-10dc32b06b4e
ms.openlocfilehash: c1c43bc47df1612be26c78351a9d30272a020160
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45593308"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-c"></a><span data-ttu-id="cd91c-102">Vorgehensweise: Schreiben einer Abfrage, die Elemente basierend auf dem Kontext sucht (C#)</span><span class="sxs-lookup"><span data-stu-id="cd91c-102">How to: Write a Query that Finds Elements Based on Context (C#)</span></span>
<span data-ttu-id="cd91c-103">Es kann vorkommen, dass Sie eine Abfrage schreiben möchten, die Elemente auf der Grundlage ihres Kontexts sucht.</span><span class="sxs-lookup"><span data-stu-id="cd91c-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="cd91c-104">Dabei soll die Filterung auf den vorausgehenden oder folgenden nebengeordneten Elementen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="cd91c-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="cd91c-105">Außerdem möchten Sie vielleicht auch nach untergeordneten oder indirekt übergeordneten Elementen filtern.</span><span class="sxs-lookup"><span data-stu-id="cd91c-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="cd91c-106">Um dies zu bewerkstelligen, können Sie eine Abfrage schreiben und die Ergebnisse dieser Abfrage in der `where`-Klausel verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd91c-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="cd91c-107">Wenn Sie zunächst eine Prüfung auf NULL-Werte vornehmen müssen und dann den Wert testen, empfiehlt es sich, die Abfrage in einer `let`-Klausel durchzuführen und die Ergebnisse dann in der `where`-Klausel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd91c-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd91c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd91c-108">Example</span></span>  
 <span data-ttu-id="cd91c-109">Im folgenden Beispiel werden alle `p`-Elemente ausgewählt, die sofort von einem `ul`-Element gefolgt werden.</span><span class="sxs-lookup"><span data-stu-id="cd91c-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants("p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name.LocalName == "ul"  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="cd91c-110">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cd91c-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="cd91c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd91c-111">Example</span></span>  
 <span data-ttu-id="cd91c-112">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cd91c-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cd91c-113">Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="cd91c-113">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```csharp  
XElement doc = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
    <p id=""1""/>  
    <ul>abc</ul>  
    <Child>  
        <p id=""2""/>  
        <notul/>  
        <p id=""3""/>  
        <ul>def</ul>  
        <p id=""4""/>  
    </Child>  
    <Child>  
        <p id=""5""/>  
        <notul/>  
        <p id=""6""/>  
        <ul>abc</ul>  
        <p id=""7""/>  
    </Child>  
</Root>");  
  
XNamespace ad = "http://www.adatum.com";  
  
IEnumerable<XElement> items =  
    from e in doc.Descendants(ad + "p")  
    let z = e.ElementsAfterSelf().FirstOrDefault()  
    where z != null && z.Name == ad.GetName("ul")  
    select e;  
  
foreach (XElement e in items)  
    Console.WriteLine("id = {0}", (string)e.Attribute("id"));  
```  
  
 <span data-ttu-id="cd91c-114">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cd91c-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd91c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd91c-115">See Also</span></span>

- <xref:System.Xml.Linq.XElement.Parse%2A>  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>  
- [<span data-ttu-id="cd91c-116">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="cd91c-116">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
