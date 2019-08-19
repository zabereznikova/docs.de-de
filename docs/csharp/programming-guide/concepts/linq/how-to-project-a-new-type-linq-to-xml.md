---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 2bb521d1445dcecdad8b9c7b28bed90e1e38c8e8
ms.sourcegitcommit: d98fdb087d9c8aba7d2cb93fe4b4ee35a2308cee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2019
ms.locfileid: "69012929"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="e3387-102">Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e3387-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="e3387-103">In anderen Beispielen dieses Abschnitts wurden Abfragen gezeigt, die Ergebnisse als eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, eine <xref:System.Collections.Generic.IEnumerable%601> von `string` und eine <xref:System.Collections.Generic.IEnumerable%601> von `int` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="e3387-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="e3387-104">Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen.</span><span class="sxs-lookup"><span data-stu-id="e3387-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="e3387-105">In vielen Fällen besteht Ihr Ziel darin, dass Ihre Abfragen als eine <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3387-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="e3387-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e3387-106">Example</span></span>

<span data-ttu-id="e3387-107">In diesem Beispiel wird gezeigt, wie Sie Objekte in der `select`-Klausel instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="e3387-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="e3387-108">Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.</span><span class="sxs-lookup"><span data-stu-id="e3387-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="e3387-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="e3387-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty 
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q; 
    }
};

class Program {
    public static void Main() 
    {
        XElement po = XElement.Load("PurchaseOrder.xml");
  
        IEnumerable<NameQty> nqList =
            from n in po.Descendants("Item")
            select new NameQty(
                    (string)n.Element("ProductName"),
                    (int)n.Element("Quantity")
                );
  
        foreach (NameQty n in nqList)
            Console.WriteLine(n.name + ":" + n.qty);
    }
}
```

<span data-ttu-id="e3387-110">In diesem Beispiel wird die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode verwendet, die im Artikel [Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md) eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e3387-110">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="e3387-111">Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e3387-111">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="e3387-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e3387-112">This example produces the following output:</span></span>

```console
Lawnmower:1
Baby Monitor:2
```
