---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)'
description: In diesem Artikel erfahren Sie, wie Sie Abfragen in LINQ to XML in C# erstellen, die neben „XElement“, „string“ oder „int“ die Schnittstelle „IEnumerable<T>“ von Typen zurückgibt.
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 013ea852a64b77c04ac583b4d9b71e8006cd4976
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104642"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="c644c-103">Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c644c-103">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="c644c-104">In anderen Beispielen dieses Abschnitts wurden Abfragen gezeigt, die Ergebnisse als eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, eine <xref:System.Collections.Generic.IEnumerable%601> von `string` und eine <xref:System.Collections.Generic.IEnumerable%601> von `int` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c644c-104">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="c644c-105">Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen.</span><span class="sxs-lookup"><span data-stu-id="c644c-105">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="c644c-106">In vielen Fällen besteht Ihr Ziel darin, dass Ihre Abfragen als eine <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c644c-106">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="c644c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c644c-107">Example</span></span>

<span data-ttu-id="c644c-108">In diesem Beispiel wird gezeigt, wie Sie Objekte in der `select`-Klausel instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="c644c-108">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="c644c-109">Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.</span><span class="sxs-lookup"><span data-stu-id="c644c-109">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="c644c-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="c644c-110">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

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

<span data-ttu-id="c644c-111">In diesem Beispiel wird die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode verwendet, die im Thema [Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md) eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c644c-111">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="c644c-112">Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c644c-112">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="c644c-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c644c-113">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
