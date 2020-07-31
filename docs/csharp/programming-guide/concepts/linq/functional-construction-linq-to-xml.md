---
title: Funktionale Konstruktion (LINQ to XML) (C#)
description: Hier erfahren Sie, wie die LINQ to XML-Programmierschnittstelle funktionale Konstruktion ermöglicht, also die Möglichkeit, einen XML-Baum in einer einzelnen Anweisung in C# zu erstellen.
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: f209a7ef2a4597ec8eeccb3083b77223a27e7a65
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103770"
---
# <a name="functional-construction-linq-to-xml-c"></a>Funktionale Konstruktion (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet mit der *funktionalen Konstruktion* eine leistungsfähige Möglichkeit zur Erstellung von XML-Elementen. Funktionale Konstruktion ist die Fähigkeit, eine XML-Struktur in einer einzelnen Anweisung zu erstellen.  
  
 Es gibt mehrere wichtige Features der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Programmierschnittstelle, die für die funktionale Konstruktion verantwortlich sind:  
  
- Der <xref:System.Xml.Linq.XElement>-Konstruktor akzeptiert verschiedene Argumentarten als Inhalt. So können Sie z. B. ein anderes <xref:System.Xml.Linq.XElement>-Objekt übergeben, das zu einem untergeordneten Element wird. Sie können auch ein <xref:System.Xml.Linq.XAttribute>-Objekt übergeben, das zu einem Attribut des Elements wird. Oder Sie übergeben ein beliebiges anderes Objekt, das in eine Zeichenfolge konvertiert wird und zum Textinhalt des Elements wird.  
  
- Der <xref:System.Xml.Linq.XElement>-Konstruktor verwendet ein `params`-Array vom Typ <xref:System.Object>, sodass Sie beliebig viele Objekte an den Konstruktor übergeben können. Auf diese Weise können Sie ein Element erstellen, das über komplexen Inhalt verfügt.  
  
- Wenn ein Objekt eine <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung werden hinzugefügt. Wenn die Auflistung <xref:System.Xml.Linq.XElement>-Objekte oder <xref:System.Xml.Linq.XAttribute>-Objekte enthält, wird jedes Element in der Auflistung getrennt hinzugefügt. Dies ist wichtig, da Sie auf diese Weise die Ergebnisse einer LINQ-Abfrage an den Konstruktor übergeben können.  
  
 Diese Funktionen ermöglichen es Ihnen, Code zu schreiben, um eine XML-Struktur zu erstellen. Im Folgenden finden Sie ein Beispiel dazu:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Diese Funktionen ermöglichen es Ihnen auch, Code zu schreiben, der die Ergebnisse von LINQ-Abfragen verwendet, wenn Sie wie folgt eine XML-Struktur erstellen:  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  