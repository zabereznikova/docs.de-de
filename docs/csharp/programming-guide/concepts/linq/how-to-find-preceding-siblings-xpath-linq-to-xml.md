---
title: 'Vorgehensweise: Ermitteln von vorhergehenden gleichgeordneten Elementen (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 64c5bc35899f85e107ccc9d6b0bf93eefb5576ef
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934022"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a>Vorgehensweise: Ermitteln von vorhergehenden gleichgeordneten Elementen (XPath-LINQ to XML) (C#)
In diesem Thema wird die XPath-`preceding-sibling`-Achse mit der untergeordneten [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>-Achse verglichen.  
  
 Der XPath-Ausdruck lautet:  
  
 `preceding-sibling::*`  
  
 Die Ergebnisse von <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> und von <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> werden in der Reihenfolge ausgegeben, in der sie auch im Dokument auftreten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das `FullAddress`-Element ermittelt, woraufhin mit der `preceding-sibling`-Achse die vorhergehenden Elemente abgerufen werden.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML für XPath-Benutzer (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
