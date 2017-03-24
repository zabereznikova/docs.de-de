---
title: LINQ to XML-Achsen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4d6466a78c3a8e9d21e30f2d3cf8a49ed89dafbf
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-axes-visual-basic"></a>LINQ to XML-Achsen (Visual Basic)
Nachdem Sie eine XML-Struktur erstellt oder ein XML-Dokument in eine XML-Struktur geladen haben, können Sie durch Abfragen der XML-Struktur nach Elementen und Attributen suchen und deren Werte abrufen.  
  
 Bevor Sie mit dem Schreiben von Abfragen beginnen, müssen Sie sich mit dem Thema [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achsen beschäftigen. Es gibt zwei Arten von Achsenmethoden: Erstens werden die Methoden, die Sie auf einem einzelnen <xref:System.Xml.Linq.XElement>Objekt <xref:System.Xml.Linq.XDocument>Objekt oder <xref:System.Xml.Linq.XNode>Objekt.</xref:System.Xml.Linq.XNode> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Diese Methoden arbeiten mit einem einzelnen Objekt und eine Auflistung <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, oder <xref:System.Xml.Linq.XNode>Objekte.</xref:System.Xml.Linq.XNode> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Zum anderen gibt es Erweiterungsmethoden für Auflistungen, die Auflistungen zurückgeben. Die Erweiterungsmethoden zählen die Quellauflistung auf, rufen für jedes Element in der Auflistung die entsprechende Achsenmethode auf und verketten die Ergebnisse.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[LINQ to XML-Achsen (Übersicht) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Definiert Achsen und erklärt, wie sie im Kontext von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfragen zu verwenden sind.|  
|[Gewusst wie: Abrufen einer Auflistung von Elementen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Führt die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A> Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.|  
|[Gewusst wie: Abrufen des Werts eines Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Zeigt, wie Sie die Werte von Elementen abrufen können.|  
|[Gewusst wie: Filtern nach Elementnamen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Zeigt, wie bei Verwendung von Achsen nach Elementnamen gefiltert werden kann.|  
|[Gewusst wie: Verketten von Aufrufen der Axis-Methode (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Zeigt, wie Aufrufe mit Achsenmethoden verkettet werden können.|  
|[Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Zeigt, wie ein einzelnes untergeordnetes Element eines Elements anhand des Tagnamens des untergeordneten Elements abgerufen werden kann.|  
|[Gewusst wie: Abrufen eine Auflistung von Attributen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Führt die <xref:System.Xml.Linq.XElement.Attributes%2A>-Methode.</xref:System.Xml.Linq.XElement.Attributes%2A> Diese Methode ruft die Attribute eines Elements ab.|  
|[Gewusst wie: Abrufen eines einzelnen Attributs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Zeigt, wie ein einzelnes Attribut eines Elements anhand des Attributnamens abgerufen werden kann.|  
|[Gewusst wie: Abrufen des Werts eines Attributs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Zeigt, wie Sie die Werte von Attributen abrufen können.|  
|[Gewusst wie: Abrufen den flachen Wert eines Elements (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Erläutert, wie der flache Wert eines Elements abgerufen wird.|  
|[Sprachintegrierte Achsen in Visual Basic (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Fasst die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Achsen integriert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
