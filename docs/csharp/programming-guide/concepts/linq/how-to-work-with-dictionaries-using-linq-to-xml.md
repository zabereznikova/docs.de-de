---
title: 'Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)'
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 1a98293f208e80e969362fca27014ecd2e5c4183
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347224"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a>Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)
Es ist häufig sinnvoll, verschiedene Datenstrukturen in XML und aus XML in andere Datenstrukturen umzuwandeln. In diesem Thema wird eine konkrete Implementierung dieser allgemeinen Herangehensweise gezeigt, bei der ein <xref:System.Collections.Generic.Dictionary%602> in XML umgewandelt und dann wieder zurückgewandelt wird.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel kommt eine Form einer funktionalen Konstruktion zum Einsatz, bei der eine Abfrage neue <xref:System.Xml.Linq.XElement>-Objekte projiziert, woraufhin die sich dabei ergebende Auflistung als Argument an den Konstruktor des <xref:System.Xml.Linq.XElement>-Objekts übergeben wird.  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt aus dem XML-Code ein Wörterbuch:  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
