---
title: LINQ to XML für XPath-Benutzer
ms.date: 07/20/2015
ms.assetid: 0e64911c-a7cc-4c20-b927-ca99078b5656
ms.openlocfilehash: 7942d33831644875f390e9128965fe1c36433808
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368789"
---
# <a name="linq-to-xml-for-xpath-users-visual-basic"></a>LINQ to XML für XPath-Benutzer (Visual Basic)

Die Themen in diesem Abschnitt demonstrieren eine Reihe von XPath-Ausdrücken und deren [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Entsprechungen.  
  
 Alle Beispiele nutzen die XPath-Funktionalität in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], die durch die Erweiterungsmethoden in <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType> verfügbar gemacht werden. Die Beispiele führen sowohl den XPath-Ausdruck als auch den [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ausdruck aus. Anschließend vergleichen sie die Ergebnisse der beiden Abfragen und prüfen dadurch, ob der XPath-Ausdruck funktional mit der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage identisch ist. Da beide Abfragearten Knoten aus derselben XML-Struktur zurückgeben, erfolgt der Vergleich der Abfrageergebnisse mittels referenzieller Identität.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|BESCHREIBUNG|  
|-----------|-----------------|  
|[Vergleich zwischen XPath und LINQ to XML](../../../../csharp/programming-guide/concepts/linq/comparison-of-xpath-and-linq-to-xml.md)|Bietet eine Übersicht über die Gemeinsamkeiten und Unterschiede von XPath und [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Gewusst wie: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-child-element-xpath-linq-to-xml.md)|Vergleicht die XPath-Achse für untergeordnete Elemente mit der- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> Methode.<br /><br /> Der zugehörige XPath-Ausdruck ist `"DeliveryNotes"`.|  
|[Gewusst wie: Suchen einer Liste untergeordneter Elemente (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-list-of-child-elements-xpath-linq-to-xml.md)|Vergleicht die XPath-Achse für untergeordnete Elemente mit der- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> Achse.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./*"`.|  
|[Gewusst wie: Suchen des Stamm Elements (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-root-element-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Stammelement abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"/PurchaseOrders"`.|  
|[Gewusst wie: Suchen nach Nachfolger Elementen (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendant-elements-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Nachfolgerelemente mit einem bestimmten Namen abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"//Name"`.|  
|[Gewusst wie: Filtern nach einem Attribut (XPath-LINQ to XML) (Visual Basic)](how-to-filter-on-an-attribute-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Nachfolgerelemente mit einem bestimmten Namen und mit einem Attribut mit einem bestimmten Wert abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./Address[@Type='Shipping']"`.|  
|[Gewusst wie: Suchen nach verwandten Elementen (XPath-LINQ to XML) (Visual Basic)](how-to-find-related-elements-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ein Element abrufen können, indem nach einem Attribut ausgewählt wird, auf das der Wert eines anderen Elements verweist.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./Customer[@CustomerID=/Root/Orders/Order[12]/CustomerID]"`.|  
|[Gewusst wie: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-in-a-namespace.md)|Vergleicht die Verwendung der XPath- <xref:System.Xml.XmlNamespaceManager> Klasse mit der- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XName.Namespace%2A> Eigenschaft der- <xref:System.Xml.Linq.XName> Klasse zum Arbeiten mit XML-Namespaces.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./aw:*"`.|  
|[Gewusst wie: Suchen nach vorangehenden neben geordneten Elementen (XPath-LINQ to XML) (Visual Basic)](how-to-find-preceding-siblings-xpath-linq-to-xml.md)|Vergleicht die XPath-`preceding-sibling`-Achse mit der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] untergeordneten <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType>-Achse.<br /><br /> Der zugehörige XPath-Ausdruck ist `"preceding-sibling::*"`.|  
|[Gewusst wie: Suchen nach Nachfolgern eines untergeordneten Elements (XPath-LINQ to XML) (Visual Basic)](how-to-find-descendants-of-a-child-element-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Nachfolgerelemente eines untergeordneten Elements mit einem bestimmten Namen abrufen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./Paragraph//Text/text()"`.|  
|[Gewusst wie: Suchen nach einer Union von zwei Speicherorten (XPath-LINQ to XML) (Visual Basic)](how-to-find-a-union-of-two-location-paths-xpath.md)|Vergleicht die Verwendung des Union-Operators  in XPath mit dem -Standardabfrageoperator in .<br /><br /> Der zugehörige XPath-Ausdruck ist <code>"//Category&#124;//Price"</code>.|  
|[Vorgehensweise: Suchen nach neben geordneten Knoten (XPath-LINQ to XML) (Visual Basic)](how-to-find-sibling-nodes-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nach allen nebengeordneten Knoten eines Knotens suchen können, die einen bestimmten Namen haben.<br /><br /> Der zugehörige XPath-Ausdruck ist `"../Book"`.|  
|[Gewusst wie: Suchen eines Attributs des übergeordneten Elements (XPath-LINQ to XML) (Visual Basic)](how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zum übergeordneten Element navigieren und nach einem zugeordneten Attribut suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"../@id"`.|  
|[Gewusst wie: Suchen nach Attributen von neben geordneten Elementen mit einem bestimmten Namen (XPath-LINQ to XML) (Visual Basic)](how-to-find-attributes-of-siblings-with-a-specific-name.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nach bestimmten Attributen der nebengeordneten Knoten des Kontextknotens suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"../Book/@id"`.|  
|[Gewusst wie: Suchen nach Elementen mit einem bestimmten Attribut (XPath-LINQ to XML) (Visual Basic)](how-to-find-elements-with-a-specific-attribute.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nach allen Elementen suchen können, die ein bestimmtes Attribut enthalten.<br /><br /> Der zugehörige XPath-Ausdruck ist `"./*[@Select]"`.|  
|[Gewusst wie: Suchen nach untergeordneten Elementen auf der Grundlage der Position (XPath-LINQ to XML) (Visual Basic)](how-to-find-child-elements-based-on-position.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nach einem Element anhand seiner relativen Position suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"Test[position() >= 2 and position() <= 4]"`.|  
|[Gewusst wie: Suchen des unmittelbar vorhergehenden neben geordneten Elements (XPath-LINQ to XML) (Visual Basic)](how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml.md)|Vergleicht, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] nach dem unmittelbar vorgehenden nebengeordneten Knoten eines Knotens suchen können.<br /><br /> Der zugehörige XPath-Ausdruck ist `"preceding-sibling::*[1]"`.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.XPath?displayProperty=nameWithType>
- [Querying XML Trees (Visual Basic) (Abfragen von XML-Strukturen (Visual Basic))](querying-xml-trees.md)
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
