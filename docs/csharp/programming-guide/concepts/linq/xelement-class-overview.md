---
title: "Übersicht über die XElement-Klasse (C#) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 193ae8193d73d57638835c96c3f7dfd28d320473
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-c"></a>Übersicht über die XElement-Klasse (C#)
Die Klasse <xref:System.Xml.Linq.XElement> ist eine der grundlegenden Klassen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Sie stellt ein XML-Element dar. Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden. Sie können auch mit anderen Klassen in <xref:System.Xml?displayProperty=fullName> zusammenarbeiten, z.B. <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>"XElement"-Funktionalität  
 In diesem Thema werden die von der Klasse <xref:System.Xml.Linq.XElement> bereitgestellten Funktionen beschrieben.  
  
### <a name="constructing-xml-trees"></a>Konstruieren von XML-Strukturen  
 Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:  
  
-   XML-Strukturen in Code konstruieren Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#)) ](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Sie können XML aus verschiedenen Quellen analysieren, darunter <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URL). Weitere Informationen finden Sie unter [Parsing XML (C#) (XML analysieren (C#))](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Sie können <xref:System.Xml.XmlReader> verwenden, um die Struktur aufzufüllen. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
-   Wenn Sie über ein Modul verfügen, das Inhalt in einen <xref:System.Xml.XmlWriter> schreiben kann, können Sie die Methode <xref:System.Xml.Linq.XContainer.CreateWriter%2A> verwenden, um einen Writer zu erstellen, ihn an das Modul weiterzugeben und dann den Inhalt zu verwenden, der in <xref:System.Xml.XmlWriter> geschrieben wird, um die XML-Struktur aufzufüllen.  
  
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
  
 Bei einer weiteren häufig verwendeten Technik zum Erstellen einer XML-Struktur wird die XML-Struktur anhand der Ergebnisse einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage aufgefüllt, wie im folgenden Beispiel dargestellt wird:  
  
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
  
### <a name="serializing-xml-trees"></a>Serialisieren von XML-Strukturen  
 Sie können die XML Struktur in <xref:System.IO.File>, <xref:System.IO.TextWriter> oder <xref:System.Xml.XmlWriter> serialisieren.  
  
 Weitere Informationen finden Sie unter [Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Abrufen von XML-Daten über Achsenmethoden  
 Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.  
  
 Weitere Informationen finden Sie unter [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Abfragen von XML-Strukturen  
 Sie können [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfragen schreiben, die Daten aus einer XML-Struktur abrufen.  
  
 Weitere Informationen finden Sie unter [Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Ändern von XML-Strukturen  
 Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute. Sie können ein Element auch aus seinem übergeordneten Element entfernen.  
  
 Weitere Informationen finden Sie unter [Modifying XML Trees (LINQ to XML) (C#) (Bearbeiten von XML-Strukturen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
