---
title: "LINQ to XML für XPath-Benutzer (C#) | Microsoft-Dokumentation"
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
ms.assetid: 91774511-1dca-4f06-ac0b-913746f104fe
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ff9490d7eb89e1503763060dbd123d59308a512d
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-for-xpath-users-c"></a>LINQ to XML für XPath-Benutzer (C#)
Die Themen in diesem Abschnitt demonstrieren eine Reihe von XPath-Ausdrücken und deren [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Entsprechungen.  
  
 Alle Beispiele nutzen die XPath-Funktionalität in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], die durch die Erweiterungsmethoden in <xref:System.Xml.XPath.Extensions?displayProperty=fullName> verfügbar gemacht werden. Die Beispiele führen sowohl den XPath-Ausdruck als auch den [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Ausdruck aus. Anschließend vergleichen sie die Ergebnisse der beiden Abfragen und prüfen dadurch, ob der XPath-Ausdruck funktional mit der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfrage identisch ist. Da beide Abfragearten Knoten aus derselben XML-Struktur zurückgeben, erfolgt der Vergleich der Abfrageergebnisse mittels referenzieller Identität.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Vergleich zwischen XPath und LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Bietet eine Übersicht über die Gemeinsamkeiten und Unterschiede von XPath und [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Vorgehensweise: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-child-element-xpath-linq-to-xml.md)|Vergleicht die Achse des untergeordneten XPath-Elements mit der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Methode </xref:System.Xml.Linq.XContainer.Element%2A>.<br /><br /> Der zugehörige XPath-Ausdruck ist `"DeliveryNotes"`.|  
|[Vorgehensweise: Suchen einer Liste untergeordneter Elemente (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Vergleicht das untergeordnete XPath-Element mit der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achse <xref:System.Xml.Linq.XContainer.Elements%2A>.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./*"`.|  
|[Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-root-element-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] das Stammelement abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"/PurchaseOrders"`.|  
|[Vorgehensweise: Suchen von Nachfolgerelementen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-descendant-elements-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Nachfolgerelemente mit einem bestimmten Namen abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"//Name"`.|  
|[Vorgehensweise: Filtern nach einem Attribut (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `".//Address[@Type='Shipping']"`.|  
|[Vorgehensweise: Suchen nach verwandten Elementen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-related-elements-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ein Element abrufen können, indem nach einem Attribut ausgewählt wird, auf das der Wert eines anderen Elements verweist.<br /><br /> Der zugehörige XPath-Ausdruck ist `".//Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`.|  
|[Vorgehensweise: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-elements-in-a-namespace-xpath-linq-to-xml.md)|Vergleicht die Verwendung der XPath-Klasse <xref:System.Xml.XmlNamespaceManager> mit der Eigenschaft [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> der Klasse <xref:System.Xml.Linq.XName>, um mit XML-Namespaces zu arbeiten.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./aw:*"`.|  
|[Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Vergleicht die XPath-Achse `preceding-sibling` mit der untergeordneten Achse [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>.<br /><br /> Der zugehörige XPath-Ausdruck ist `"preceding-sibling::*"`.|  
|[Vorgehensweise: Suchen nach Nachfolgern von untergeordneten Elementen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Nachfolgerelemente eines untergeordneten Elements mit einem bestimmten Namen abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./Paragraph//Text/text()"`.|  
|[Vorgehensweise: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml.md)|Vergleicht die Verwendung des Union-Operators `&#124;` in XPath mit dem Standardabfrageoperator <xref:System.Linq.Enumerable.Concat%2A> in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].<br /><br /> Der zugehörige XPath-Ausdruck ist `"//Category&#124;//Price"`.|  
|[Vorgehensweise: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nach allen nebengeordneten Knoten eines Knotens suchen können, die einen bestimmten Namen haben.<br /><br /> Der zugehörige XPath-Ausdruck ist `"../Book"`.|  
|[Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] zum übergeordneten Element navigieren und nach einem zugeordneten Attribut suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"../@id"`.|  
|[Vorgehensweise: Suchen nach Attributen von nebengeordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nach bestimmten Attributen der nebengeordneten Knoten des Kontextknotens suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"``../Book/@id``"`.|  
|[Vorgehensweise: Suchen nach Elementen mit bestimmten Attributen (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nach allen Elementen suchen können, die ein bestimmtes Attribut enthalten.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./*[@Select]"`.|  
|[Vorgehensweise: Suchen nach untergeordneten Elementen anhand der Position (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-child-elements-based-on-position-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nach einem Element anhand seiner relativen Position suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"Test[position() >= 2 and position() <= 4]"`.|  
|[Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nach dem unmittelbar vorgehenden nebengeordneten Knoten eines Knotens suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"preceding-sibling::*[1]"`.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.XPath?displayProperty=fullName>   
 [Abfragen von XML-Strukturen (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)   
 [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](http://msdn.microsoft.com/library/536c6fce-1453-4654-9c72-bca54d47e081)
