---
title: Funktionale Transformation von XML
ms.date: 07/20/2015
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
ms.openlocfilehash: 7e029fd562ae3f221a8aaef40f332a1e3fa896eb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353423"
---
# <a name="functional-transformation-of-xml-visual-basic"></a>Funktionale Transformation von XML (Visual Basic)
In diesem Thema wird der Ansatz der reinen funktionalen Transformation zum Ändern von XML-Dokumenten erläutert und dem prozeduralen Ansatz gegenübergestellt.  
  
## <a name="modifying-an-xml-document"></a>Ändern eines XML-Dokuments  
 Eine der häufigsten Aufgaben, die XML-Programmierer zu lösen haben, ist das Transformieren von XML von einer Form in eine andere Form. Die Form eines XML-Dokuments wird durch die Struktur des Dokuments bestimmt. Zur Form gehört Folgendes:  
  
- die durch das Dokument ausgedrückte Hierarchie  
  
- die Element- und Attributnamen  
  
- die Datentypen der Elemente und Attribute  
  
 Beim Transformieren von XML von einer Form in eine andere ist es in der Regel am effektivsten, mit der reinen funktionalen Transformation zu arbeiten. Bei dieser Herangehensweise muss der Programmierer in erster Linie eine Transformation erstellen, die auf das gesamte XML-Dokument (oder auf einen oder mehrere streng definierte Knoten) angewendet wird. Die funktionale Transformation ist (zumindest für Programmierer, die damit vertraut sind) sicher am einfachsten zu codieren, führt zu gut verwaltbarem Code und ist häufig kompakter als andere Herangehensweisen.  
  
### <a name="xml-functional-transformational-technologies"></a>Technologien für die funktionale XML-Transformation  
 Microsoft bietet zwei funktionale Transformationstechnologien für XML-Dokumente: XSLT und LINQ to XML. XSLT wird im verwalteten <xref:System.Xml.Xsl>-Namespace und in der systemeigenen COM-Implementierung von MSXML unterstützt. XSLT ist zwar eine robuste Technologie zum Ändern von XML-Dokumenten, erfordert aber Kenntnisse auf einem speziellen Gebiet: der XSLT-Sprache und der sie unterstützenden APIs.  
  
 LINQ to XML stellt die Tools bereit, die für das ausdrucksstarke und leistungsfähige Codieren reiner funktionaler Transformationen innerhalb des C#- und des Visual Basic-Codes benötigt werden. So verwenden z. B. viele der in der LINQ to XML-Dokumentation verwendeten Beispiele reine Funktionen. Außerdem verwenden wir im [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) LINQ to XML in einem funktionalen Ansatz, um Informationen in einem Microsoft Word-Dokument zu bearbeiten.  
  
 Einen ausführlicheren Vergleich von LINQ to XML mit anderen Microsoft XML-Technologien finden Sie unter [LINQ to XML Vergleich zu anderen XML-Technologien](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT ist das empfohlene Tool für dokumentorientierte Transformationen, wenn das Quelldokument eine unregelmäßige Struktur besitzt. Dokumentorientierte Transformationen können aber auch von LINQ to XML ausgeführt werden. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von Anmerkungen zum Transformieren von LINQ to XML Bäumen in einem XSLT-Format (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)
- [LINQ to XML im Vergleich zu anderen XML-Technologien](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)
