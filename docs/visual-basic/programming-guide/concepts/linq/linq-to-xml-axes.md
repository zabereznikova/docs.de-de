---
title: LINQ to XML-Achsen
ms.date: 07/20/2015
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
ms.openlocfilehash: 757c765062b1d1ca1cddb0c559fa46ef6a0fe796
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368984"
---
# <a name="linq-to-xml-axes-visual-basic"></a>LINQ to XML-Achsen (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen.  
  
 Bevor Sie mit dem Schreiben von Abfragen beginnen, müssen Sie sich mit dem Thema [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen beschäftigen. Es gibt zwei Arten von Achsenmethoden: Zum einen gibt es die Methoden, die Sie für ein einzelnes <xref:System.Xml.Linq.XElement>-Objekt, <xref:System.Xml.Linq.XDocument>-Objekt oder <xref:System.Xml.Linq.XNode>-Objekt aufrufen. Diese Methoden arbeiten mit einem einzelnen Objekt und geben eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten, <xref:System.Xml.Linq.XAttribute>-Objekten oder <xref:System.Xml.Linq.XNode>-Objekten zurück. Zum anderen gibt es Erweiterungsmethoden für Auflistungen, die Auflistungen zurückgeben. Die Erweiterungsmethoden zählen die Quellauflistung auf, rufen für jedes Element in der Auflistung die entsprechende Achsenmethode auf und verketten die Ergebnisse.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|BESCHREIBUNG|  
|-----------|-----------------|  
|[Übersicht über LINQ to XML-Achsen (Visual Basic)](linq-to-xml-axes-overview.md)|Definiert Achsen und erklärt, wie sie im Kontext von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen zu verwenden sind.|  
|[Gewusst wie: Abrufen einer Auflistung von Elementen (LINQ to XML) (Visual Basic)](how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode. Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.|  
|[Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Zeigt, wie Sie die Werte von Elementen abrufen können.|  
|[Gewusst wie: Filtern nach Element Namen (LINQ to XML) (Visual Basic)](how-to-filter-on-element-names-linq-to-xml.md)|Zeigt, wie bei Verwendung von Achsen nach Elementnamen gefiltert werden kann.|  
|[Gewusst wie: Verketten von Achsen Methoden aufrufen (LINQ to XML) (Visual Basic)](how-to-chain-axis-method-calls-linq-to-xml.md)|Zeigt, wie Aufrufe mit Achsenmethoden verkettet werden können.|  
|[Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-child-element-linq-to-xml.md)|Zeigt, wie ein einzelnes untergeordnetes Element eines Elements anhand des Tagnamens des untergeordneten Elements abgerufen werden kann.|  
|[Vorgehensweise: Abrufen einer Auflistung von Attributen (LINQ to XML) (Visual Basic)](how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Methode. Diese Methode ruft die Attribute eines Elements ab.|  
|[Vorgehensweise: Abrufen eines einzelnen Attributs (LINQ to XML) (Visual Basic)](how-to-retrieve-a-single-attribute-linq-to-xml.md)|Zeigt, wie ein einzelnes Attribut eines Elements anhand des Attributnamens abgerufen werden kann.|  
|[Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (Visual Basic)](how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Zeigt, wie Sie die Werte von Attributen abrufen können.|  
|[Gewusst wie: Abrufen des flachen Werts eines Elements (Visual Basic)](how-to-retrieve-the-shallow-value-of-an-element.md)|Erläutert, wie der flache Wert eines Elements abgerufen wird.|  
|[Sprachintegrierte Achsen in Visual Basic (LINQ to XML)](language-integrated-axes.md)|Fasst die Visual Basic integrierten Achsen zusammen.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Programmier Handbuch (LINQ to XML) (Visual Basic)](programming-guide-linq-to-xml.md)
