---
title: 'Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: 1e5aece41021642d43b7f6f7b78bb105156ee4ee
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141005"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML) (C#)
Es kann passieren, dass Sie den unmittelbar vorhergehenden nebengeordneten Knoten eines Knotens ermitteln möchten. Aufgrund des semantischen Unterschieds bei Positionsprädikaten für die Achsen vorhergehender nebengeordneter Knoten in XPath im Vergleich zu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist dies einer der interessanteren Vergleiche.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel verwendet die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage den <xref:System.Linq.Enumerable.Last%2A>-Operator, um nach dem letzten Knoten in der Auflistung zu suchen, der von <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> zurückgegeben wurde. Im Unterschied dazu verwendet der XPath-Ausdruck für die Suche nach dem unmittelbar vorhergehenden Element ein Prädikat mit dem Wert 1.  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
Results are identical  
<Child3 />  
```  
