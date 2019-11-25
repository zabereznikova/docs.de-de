---
title: LINQ to XML-Achsen
ms.date: 07/20/2015
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
ms.openlocfilehash: 73c5325c23c4724a28a123af5c2f8c25b2fd02de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352022"
---
# <a name="linq-to-xml-axes-visual-basic"></a>LINQ to XML Axes (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen.  
  
 Bevor Sie mit dem Schreiben von Abfragen beginnen, müssen Sie sich mit dem Thema [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen beschäftigen. Es gibt zwei Arten von Achsenmethoden: Zum einen gibt es die Methoden, die Sie für ein einzelnes <xref:System.Xml.Linq.XElement>-Objekt, <xref:System.Xml.Linq.XDocument>-Objekt oder <xref:System.Xml.Linq.XNode>-Objekt aufrufen. Diese Methoden arbeiten mit einem einzelnen Objekt und geben eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten, <xref:System.Xml.Linq.XAttribute>-Objekten oder <xref:System.Xml.Linq.XNode>-Objekten zurück. Zum anderen gibt es Erweiterungsmethoden für Auflistungen, die Auflistungen zurückgeben. Die Erweiterungsmethoden zählen die Quellauflistung auf, rufen für jedes Element in der Auflistung die entsprechende Achsenmethode auf und verketten die Ergebnisse.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Topic|Beschreibung|  
|-----------|-----------------|  
|[LINQ to XML Axes Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definiert Achsen und erklärt, wie sie im Kontext von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen zu verwenden sind.|  
|[How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode. Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.|  
|[How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Zeigt, wie Sie die Werte von Elementen abrufen können.|  
|[How to: Filter on Element Names (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Zeigt, wie bei Verwendung von Achsen nach Elementnamen gefiltert werden kann.|  
|[How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Zeigt, wie Aufrufe mit Achsenmethoden verkettet werden können.|  
|[How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Zeigt, wie ein einzelnes untergeordnetes Element eines Elements anhand des Tagnamens des untergeordneten Elements abgerufen werden kann.|  
|[How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Methode. Diese Methode ruft die Attribute eines Elements ab.|  
|[How to: Retrieve a Single Attribute (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Zeigt, wie ein einzelnes Attribut eines Elements anhand des Attributnamens abgerufen werden kann.|  
|[How to: Retrieve the Value of an Attribute (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Zeigt, wie Sie die Werte von Attributen abrufen können.|  
|[How to: Retrieve the Shallow Value of an Element (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Erläutert, wie der flache Wert eines Elements abgerufen wird.|  
|[Language-Integrated Axes in Visual Basic (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Summarizes the Visual Basic integrated axes.|  
  
## <a name="see-also"></a>Siehe auch

- [Programming Guide (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
