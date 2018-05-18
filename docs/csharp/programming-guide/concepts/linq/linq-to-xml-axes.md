---
title: LINQ to XML-Achsen (C#)
ms.date: 07/20/2015
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
ms.openlocfilehash: d12d35a6f9b02056946ba201a7bd5a961f64ba36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linq-to-xml-axes-c"></a>LINQ to XML-Achsen (C#)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen.  
  
 Bevor Sie mit dem Schreiben von Abfragen beginnen, müssen Sie sich mit dem Thema [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsen beschäftigen. Es gibt zwei Arten von Achsenmethoden: Zum einen gibt es die Methoden, die Sie für ein einzelnes <xref:System.Xml.Linq.XElement>-Objekt, <xref:System.Xml.Linq.XDocument>-Objekt oder <xref:System.Xml.Linq.XNode>-Objekt aufrufen. Diese Methoden arbeiten mit einem einzelnen Objekt und geben eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten, <xref:System.Xml.Linq.XAttribute>-Objekten oder <xref:System.Xml.Linq.XNode>-Objekten zurück. Zum anderen gibt es Erweiterungsmethoden für Auflistungen, die Auflistungen zurückgeben. Die Erweiterungsmethoden zählen die Quellauflistung auf, rufen für jedes Element in der Auflistung die entsprechende Achsenmethode auf und verketten die Ergebnisse.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|description|  
|-----------|-----------------|  
|[LINQ to XML Axes Overview (C#) (Übersicht über LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definiert Achsen und erklärt, wie sie im Kontext von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen zu verwenden sind.|  
|[How to: Retrieve a Collection of Elements (LINQ to XML) (C#) (Vorgehensweise: Abrufen einer Elementauflistung (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode. Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.|  
|[How to: Retrieve the Value of an Element (LINQ to XML) (C#) (Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Zeigt, wie Sie die Werte von Elementen abrufen können.|  
|[How to: Filter on Element Names (LINQ to XML) (C#) (Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Zeigt, wie bei Verwendung von Achsen nach Elementnamen gefiltert werden kann.|  
|[How to: Chain Axis Method Calls (LINQ to XML) (C#) (Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Zeigt, wie Aufrufe mit Achsenmethoden verkettet werden können.|  
|[How to: Retrieve a Single Child Element (LINQ to XML) (C#) (Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Zeigt, wie ein einzelnes untergeordnetes Element eines Elements anhand des Tagnamens des untergeordneten Elements abgerufen werden kann.|  
|[How to: Retrieve a Collection of Attributes (LINQ to XML) (C#) (Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Methode. Diese Methode ruft die Attribute eines Elements ab.|  
|[How to: Retrieve a Single Attribute (LINQ to XML) (C#) (Vorgehensweise: Abrufen eines einzelnen Attributs (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Zeigt, wie ein einzelnes Attribut eines Elements anhand des Attributnamens abgerufen werden kann.|  
|[How to: Retrieve the Value of an Attribute (LINQ to XML) (C#) (Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Zeigt, wie Sie die Werte von Attributen abrufen können.|  
|[How to: Retrieve the Shallow Value of an Element (C#) (Vorgehensweise: Abrufen des Shallow-Werts eines Elements (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Erläutert, wie der flache Wert eines Elements abgerufen wird.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [Programming Guide (LINQ to XML) (C#) (Programmierhandbuch (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
