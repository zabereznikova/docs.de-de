---
title: Voratomisierung von XName-Objekten (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 2fd754a352bd2988e52ec9c67a9915a8e587b107
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69591495"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a>Voratomisierung von XName-Objekten (LINQ to XML) (C#)
Eine Möglichkeit zum Verbessern der Leistung in LINQ to XML ist, <xref:System.Xml.Linq.XName>-Objekte vorab zu atomisieren. Voratomisierung bedeutet, dass einem <xref:System.Xml.Linq.XName>-Objekt eine Zeichenfolge zugeordnet wird, bevor Sie mithilfe der Konstruktoren der <xref:System.Xml.Linq.XElement>-Klasse und der <xref:System.Xml.Linq.XAttribute>-Klasse die XML-Struktur erstellen. Anschließend wird anstelle der Übergabe einer Zeichenfolge an den Konstruktor, der die implizite Konvertierung von Zeichenfolge in <xref:System.Xml.Linq.XName> verwenden würde, das initialisierte <xref:System.Xml.Linq.XName>-Objekt übergeben.  
  
 Dies verbessert die Leistung beim Erstellen von großen XML-Strukturen, in denen bestimmte Namen wiederholt werden. Deklarieren und initialisieren Sie hierzu <xref:System.Xml.Linq.XName>-Objekte, bevor Sie die XML-Struktur erstellen, und verwenden Sie dann die <xref:System.Xml.Linq.XName>-Objekte, anstatt für die Element- und Attributnamen Zeichenfolgen anzugeben. Mit dieser Vorgehensweise können beim Erstellen einer großen Anzahl von Elementen (oder Attributen) wesentliche Leistungsverbesserungen erzielt werden.  
  
 Sie sollten Voratomisierung innerhalb Ihres Szenarios testen, um eine Entscheidung über die Anwendbarkeit dieses Verfahrens zu treffen.  
  
## <a name="example"></a>Beispiel  
 Dies wird im folgenden Beispiel veranschaulicht:  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 Im folgenden Beispiel wird dieselbe Vorgehensweise für ein XML-Dokument in einem Namespace erläutert.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 Das folgende Beispiel entspricht eher realen Bedingungen. In diesem Beispiel wird der Inhalt des Elements durch eine Abfrage bereitgestellt:  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 Im vorherigen Beispiel wird eine bessere Leistung als im folgenden Beispiel erzielt, in dem Namen nicht voratomisiert werden:  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Atomized XName and XNamespace Objects (LINQ to XML) (C#) (Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#))](./atomized-xname-and-xnamespace-objects-linq-to-xml.md)
