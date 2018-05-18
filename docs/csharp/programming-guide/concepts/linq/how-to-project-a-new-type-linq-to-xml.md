---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: f9a46e78a0f80f33764e9f87e3e8ce3560a8e0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)
In anderen Beispielen dieses Abschnitts wurden Abfragen gezeigt, die Ergebnisse als eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, eine <xref:System.Collections.Generic.IEnumerable%601> von `string` und eine <xref:System.Collections.Generic.IEnumerable%601> von `int` zurückgeben. Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen. In vielen Fällen besteht Ihr Ziel darin, dass Ihre Abfragen als eine <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgegeben werden.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie Sie Objekte in der `select`-Klausel instanziieren können. Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.  
  
 Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
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
  
 In diesem Beispiel wird die `M:System.Xml.Linq.XElement.Element`-Methode verwendet, die im Thema [Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md) eingeführt wurde. Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der `M:System.Xml.Linq.XElement.Element`-Methode zurückgegeben werden.  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Projektionen und Transformationen (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
