---
title: "Übersicht über die XAttribute-Klasse (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1ce5f4be6006908b35057854f89432471fd9f06b
ms.lasthandoff: 03/13/2017

---
# <a name="xattribute-class-overview-visual-basic"></a>Übersicht über die XAttribute-Klasse (Visual Basic)
Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind. Die <xref:System.Xml.Linq.XAttribute>-Klasse stellt XML-Attribute dar.</xref:System.Xml.Linq.XAttribute>  
  
## <a name="overview"></a>Übersicht  
 Das Arbeiten mit Attributen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist vergleichbar mit dem Arbeiten mit Elementen. Ihre Konstruktoren ähneln sich, und auch die Methoden zum Aufrufen von Auflistungen sind ähnlich. Ein [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Abfrageausdruck für eine Auflistung von Attributen sieht ähnlich einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] -Abfrageausdruck für eine Auflistung von Elementen.  
  
 Die Reihenfolge, in der einem Element Attribute hinzugefügt wurden, wird beibehalten. Das heißt, wenn Sie die Attribute durchlaufen, sehen Sie die Attribute genau in der Reihenfolge, in der sie hinzugefügt wurden.  
  
## <a name="the-xattribute-constructor"></a>Der "XAttribute"-Konstruktor  
 Der folgende Konstruktor der die <xref:System.Xml.Linq.XAttribute>Klasse ist diejenige, die Sie am häufigsten verwenden werden:</xref:System.Xml.Linq.XAttribute>  
  
|Konstruktor|Beschreibung|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|Erstellt ein <xref:System.Xml.Linq.XAttribute>Objekt.</xref:System.Xml.Linq.XAttribute> Das `name`-Argument gibt den Namen des Attributs an, während `content` den Inhalt des Attributs angibt.|  
  
### <a name="creating-an-element-with-an-attribute"></a>Erstellen eines Elements mit einem Attribut  
 Der folgende Code zeigt ein Element, das ein Attribut mit XML-Literalen in Visual Basic enthält:  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a>Funktionale Konstruktion von Attributen  
 Konstruieren <xref:System.Xml.Linq.XAttribute>inline mit der Erstellung der Objekte <xref:System.Xml.Linq.XElement>Objekte, wie folgt:</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute>  
  
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
 Es gibt einige Unterschiede zwischen Attributen und Elementen. <xref:System.Xml.Linq.XAttribute>Objekte sind keine Knoten in der XML-Struktur.</xref:System.Xml.Linq.XAttribute> Sie sind Name/Wert-Paare, die einem XML-Element zugeordnet sind. Im Unterschied zum Dokumentobjektmodell (DOM) reflektiert dies die Struktur des XML genauer. Obwohl <xref:System.Xml.Linq.XAttribute>Objekte sind nicht tatsächlich Knoten in der XML-Struktur, die Arbeit mit <xref:System.Xml.Linq.XAttribute>Objekte ähnelt dem Arbeiten mit <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XAttribute>  
  
 Diese Unterscheidung ist im Wesentlichen nur für Entwickler von Bedeutung, die Code schreiben, der mit XML-Strukturen auf Knotenebene arbeitet. Für die meisten Entwickler dürfte dieser Unterschied ohne praktische Bedeutung sein.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML-Programmierung (Übersicht) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
