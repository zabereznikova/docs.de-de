---
title: LINQ to XML-Achsen (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
ms.openlocfilehash: 23feaf0aee66002a59279a49192ad459afc682aa
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930131"
---
# <a name="linq-to-xml-axes-visual-basic"></a>LINQ to XML-Achsen (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen.  
  
 Bevor Sie mit dem Schreiben von Abfragen beginnen, müssen Sie sich mit dem Thema [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen beschäftigen. Es gibt zwei Arten von Achsenmethoden: Zum einen gibt es die Methoden, die Sie für ein einzelnes <xref:System.Xml.Linq.XElement>-Objekt, <xref:System.Xml.Linq.XDocument>-Objekt oder <xref:System.Xml.Linq.XNode>-Objekt aufrufen. Diese Methoden arbeiten mit einem einzelnen Objekt und geben eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten, <xref:System.Xml.Linq.XAttribute>-Objekten oder <xref:System.Xml.Linq.XNode>-Objekten zurück. Zum anderen gibt es Erweiterungsmethoden für Auflistungen, die Auflistungen zurückgeben. Die Erweiterungsmethoden zählen die Quellauflistung auf, rufen für jedes Element in der Auflistung die entsprechende Achsenmethode auf und verketten die Ergebnisse.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[LINQ to XML Axes Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definiert Achsen und erklärt, wie sie im Kontext von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen zu verwenden sind.|  
|[Vorgehensweise: Abrufen eine Elementauflistung (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode. Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.|  
|[Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Zeigt, wie Sie die Werte von Elementen abrufen können.|  
|[Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Zeigt, wie bei Verwendung von Achsen nach Elementnamen gefiltert werden kann.|  
|[Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Zeigt, wie Aufrufe mit Achsenmethoden verkettet werden können.|  
|[Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Zeigt, wie ein einzelnes untergeordnetes Element eines Elements anhand des Tagnamens des untergeordneten Elements abgerufen werden kann.|  
|[Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Methode. Diese Methode ruft die Attribute eines Elements ab.|  
|[Vorgehensweise: Abrufen eines einzelnes Attributs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Zeigt, wie ein einzelnes Attribut eines Elements anhand des Attributnamens abgerufen werden kann.|  
|[Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Zeigt, wie Sie die Werte von Attributen abrufen können.|  
|[Vorgehensweise: Abrufen des Shallow-Werts eines Elements (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Erläutert, wie der flache Wert eines Elements abgerufen wird.|  
|[Sprachintegrierte Achsen in Visual Basic (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Enthält eine Zusammenfassung die Achsen Visual Basic integriert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
