---
title: Übersicht über die XAttribute-Klasse
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 00aeeec3f251ecd1d21a313290326b3ba49d63d3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349324"
---
# <a name="xattribute-class-overview-visual-basic"></a>Übersicht über die XAttribute-Klasse (Visual Basic)
Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind. Die <xref:System.Xml.Linq.XAttribute>-Klasse stellt XML-Attribute dar.  
  
## <a name="overview"></a>Übersicht  
 Das Arbeiten mit Attributen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist vergleichbar mit dem Arbeiten mit Elementen. Ihre Konstruktoren ähneln sich, und auch die Methoden zum Aufrufen von Auflistungen sind ähnlich. Ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck für eine Auflistung von Attributen sieht einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck für eine Auflistung von Elementen sehr ähnlich.  
  
 Die Reihenfolge, in der einem Element Attribute hinzugefügt wurden, wird beibehalten. Das heißt, wenn Sie die Attribute durchlaufen, sehen Sie die Attribute genau in der Reihenfolge, in der sie hinzugefügt wurden.  
  
## <a name="the-xattribute-constructor"></a>Der "XAttribute"-Konstruktor  
 Der folgende Konstruktor der <xref:System.Xml.Linq.XAttribute>-Klasse ist der Konstruktor, den Sie am häufigsten verwenden werden:  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Sie erstellt ein <xref:System.Xml.Linq.XAttribute>-Objekt. Das `name`-Argument gibt den Namen des Attributs an, während `content` den Inhalt des Attributs angibt.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Erstellen eines Elements mit einem Attribut  
 Der folgende Code zeigt ein-Element, das ein Attribut mit XML-Literalen in Visual Basic enthält:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Funktionale Konstruktion von Attributen  
 Mit der Konstruktion von <xref:System.Xml.Linq.XAttribute>-Objekten können Sie <xref:System.Xml.Linq.XElement>-Objekte "inline" erstellen, wie das folgende Beispiel zeigt:  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
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
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die LINQ to XML Programmierung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
