---
title: Übersicht über die XElement-Klasse (C#)
description: Die XElement-Klasse repräsentiert ein XML-Element in C#. Sie ist eine der grundlegenden Klassen in LINQ to XML. Hier erfahren Sie mehr über die von XElement bereitgestellte Funktionalität.
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: f76f51703de054443f47531294777b43a9c0b004
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302177"
---
# <a name="xelement-class-overview-c"></a>Übersicht über die XElement-Klasse (C#)
Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Sie stellt ein XML-Element dar. Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden. Die Klasse kann auch mit anderen Klassen in <xref:System.Xml?displayProperty=nameWithType> zusammenarbeiten, wie <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
In diesem Thema wird die von der <xref:System.Xml.Linq.XElement>-Klasse bereitgestellte Funktionalität beschrieben.  
  
## <a name="constructing-xml-trees"></a>Konstruieren von XML-Strukturen  
 Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:  
  
- XML-Strukturen in Code konstruieren Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md).  
  
- XML aus verschiedenen Quellen, wie <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs), analysieren Weitere Informationen finden Sie unter [Parsing XML (C#) (XML analysieren (C#))](./how-to-parse-a-string.md).  
  
- einen <xref:System.Xml.XmlReader> verwenden, um die Struktur aufzufüllen Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- mit der <xref:System.Xml.XmlWriter>-Methode einen Writer erstellen, den Writer an das Modul übergeben und dann den in den <xref:System.Xml.Linq.XContainer.CreateWriter%2A> geschriebenen Inhalt zum Auffüllen der XML-Struktur verwenden, sofern ein Modul vorhanden ist, das Inhalt in einen <xref:System.Xml.XmlWriter> schreiben kann  
  
 Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:  
  
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
  
 Bei einer weiteren häufig verwendeten Technik zum Erstellen einer XML-Struktur wird die XML-Struktur anhand der Ergebnisse einer LINQ-Abfrage aufgefüllt, wie im folgenden Beispiel dargestellt wird:  
  
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
  
## <a name="serializing-xml-trees"></a>Serialisieren von XML-Strukturen  
 Sie können die XML-Struktur in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.  
  
 Weitere Informationen finden Sie unter [Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](./preserving-white-space-while-serializing.md).  
  
## <a name="retrieving-xml-data-via-axis-methods"></a>Abrufen von XML-Daten über Achsenmethoden  
 Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen. LINQ-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.  
  
 Weitere Informationen finden Sie unter [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md).  
  
## <a name="querying-xml-trees"></a>Abfragen von XML-Strukturen  
 Sie können LINQ-Abfragen schreiben, die Daten aus einer XML-Struktur abrufen.  
  
 Weitere Informationen finden Sie unter [Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))](./how-to-find-an-element-with-a-specific-attribute.md).  
  
## <a name="modifying-xml-trees"></a>Ändern von XML-Strukturen  
 Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute. Sie können ein Element auch aus seinem übergeordneten Element entfernen.  
  
 Weitere Informationen finden Sie unter [Modifying XML Trees (LINQ to XML) (C#) (Bearbeiten von XML-Strukturen (LINQ to XML) (C#))](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))](serializing-to-files-textwriters-and-xmlwriters.md)
