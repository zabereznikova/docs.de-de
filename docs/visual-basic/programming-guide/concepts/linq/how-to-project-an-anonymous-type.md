---
title: 'Vorgehensweise: Projektieren eines anonymen Typs'
ms.date: 07/20/2015
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
ms.openlocfilehash: c486fbd7ee8ae917cd0ccf57e2b04e472784b11d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810559"
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a>Gewusst wie: Projizieren eines anonymen Typs (Visual Basic)
Es gibt Fälle, in denen Sie eine Abfrage in einen neuen Typ projizieren möchten, obwohl Sie wissen, dass dieser Typ nur für kurze Zeit verwendet werden wird. Das Erstellen eines neuen Typs für die Verwendung in der Projektion bedeutet viel Zusatzarbeit. Effizienter wäre es in diesem Fall, eine Projektion in einen anonymen Typ vorzunehmen. Mit anonymen Typen können Sie eine Klasse definieren und dann ein Objekt dieser Klasse deklarieren und initialisieren, ohne der Klasse dazu einen Namen geben zu müssen.  
  
 Anonyme Typen stellen die C#-Implementierung des mathematischen Konzepts eines *Tupels* dar. Der mathematische Begriff „Tupel“ bzw. „n-Tupel“ (englisch „Tuple“) leitet sich aus dem englischen Wortbestandteil „-(t)uple“ für „-fach“ (z. B. „quadruple“ für „vierfach“ und „quintuple“ für „fünffach“) ab. Er steht für eine endliche Abfolge von Objekten, die alle von einem bestimmten Typ sind. Mitunter wird dies als Liste von Name/Wert-Paaren bezeichnet. So könnte z.B. der Inhalt einer Adresse im XML-Dokument in [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) wie folgt ausgedrückt werden:  
  
```
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 Das Erstellen einer Instanz eines anonymen Typs können Sie sich wie das Erstellen eines Tupels n-ter Ordnung vorstellen. Wenn Sie eine Abfrage schreiben, die ein Tupel in der `Select`-Klausel erstellt, gibt die Abfrage eine `IEnumerable` des Tupels zurück.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel projiziert die `Select`-Klausel einen anonymen Typ. Das Beispiel verwendet dann `Dim`, um das `IEnumerable`-Objekt zu erstellen. Innerhalb der `For Each`-Schleife wird die Iterationsvariable zu einer Instanz des im Abfrageausdruck erstellten anonymen Typs.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim custList = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select New With { _  
        .CustomerID = el.@<CustomerID>, _  
        .CompanyName = el.<CompanyName>.Value, _  
        .ContactName = el.<ContactName>.Value _  
    }  
For Each cust In custList  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)  
Next  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```console  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Projektionen und Transformationen (LINQ to XML) (Visual Basic)](projections-and-transformations-linq-to-xml.md)
