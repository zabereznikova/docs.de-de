---
title: Übersicht der XAttribute-Klasse (C#)
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 7a806314664c6319fc45cff0dddedbe38027059d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635664"
---
# <a name="xattribute-class-overview-c"></a>Übersicht der XAttribute-Klasse (C#)
Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind. Die <xref:System.Xml.Linq.XAttribute>-Klasse stellt XML-Attribute dar.  
  
## <a name="overview"></a>Übersicht  
 Das Arbeiten mit Attributen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist vergleichbar mit dem Arbeiten mit Elementen. Ihre Konstruktoren ähneln sich, und auch die Methoden zum Aufrufen von Auflistungen sind ähnlich. Ein LINQ-Abfrageausdruck für eine Sammlung von Attributen sieht einem LINQ-Abfrageausdruck für eine Sammlung von Elementen sehr ähnlich.  
  
 Die Reihenfolge, in der einem Element Attribute hinzugefügt wurden, wird beibehalten. Das heißt, wenn Sie die Attribute durchlaufen, sehen Sie die Attribute genau in der Reihenfolge, in der sie hinzugefügt wurden.  
  
## <a name="the-xattribute-constructor"></a>Der "XAttribute"-Konstruktor  
 Der folgende Konstruktor der <xref:System.Xml.Linq.XAttribute>-Klasse ist der Konstruktor, den Sie am häufigsten verwenden werden:  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Sie erstellt ein <xref:System.Xml.Linq.XAttribute>-Objekt. Das `name`-Argument gibt den Namen des Attributs an, während `content` den Inhalt des Attributs angibt.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Erstellen eines Elements mit einem Attribut  
 Der folgende Code zeigt die häufige Aufgabe des Erstellens eines Elements mit einem Attribut:  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Funktionale Konstruktion von Attributen  
 Mit der Konstruktion von <xref:System.Xml.Linq.XAttribute>-Objekten können Sie <xref:System.Xml.Linq.XElement>-Objekte "inline" erstellen, wie das folgende Beispiel zeigt:  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a>Attribute sind keine Knoten  
 Es gibt einige Unterschiede zwischen Attributen und Elementen. <xref:System.Xml.Linq.XAttribute>-Objekte sind keine Knoten in der XML-Struktur. Sie sind Name/Wert-Paare, die einem XML-Element zugeordnet sind. Im Unterschied zum Dokumentobjektmodell (DOM) reflektiert dies die Struktur des XML genauer. Auch wenn <xref:System.Xml.Linq.XAttribute>-Objekte keine Knoten in der XML-Struktur im eigentlichen Sinne sind, ist das Arbeiten mit <xref:System.Xml.Linq.XAttribute>-Objekten vergleichbar mit dem Arbeiten mit <xref:System.Xml.Linq.XElement>-Objekten.  
  
 Diese Unterscheidung ist im Wesentlichen nur für Entwickler von Bedeutung, die Code schreiben, der mit XML-Strukturen auf Knotenebene arbeitet. Für die meisten Entwickler dürfte dieser Unterschied ohne praktische Bedeutung sein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Working with XML Namespaces (C#) (Übersicht der LINQ to XML-Programmierung (C#))](./linq-to-xml-overview.md)
