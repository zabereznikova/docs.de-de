---
title: 'Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#) | Microsoft-Dokumentation'
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
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa8c4676890dcc25108d919a501bde44299db04
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a>Vorgehensweise: Projektieren eines neuen Typs (LINQ to XML) (C#)
Andere Beispiele in diesem Abschnitt zeigen Abfragen, die Ergebnisse wie <xref:System.Collections.Generic.IEnumerable%601> für <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> für `string` und <xref:System.Collections.Generic.IEnumerable%601> für `int` zurückgeben. Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen. In vielen Fällen sollten Ihre Abfragen <xref:System.Collections.Generic.IEnumerable%601> eines anderen Typs zurückgeben.  
  
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
