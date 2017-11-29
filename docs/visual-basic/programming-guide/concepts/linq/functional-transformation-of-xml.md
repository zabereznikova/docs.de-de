---
title: Funktionale Transformation von XML (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdbe5b91-f457-4b4e-a11b-def4bdd77bab
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 69cd09a017ab7fbf9fc56a6724abb4cc15b3e1cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="functional-transformation-of-xml-visual-basic"></a>Funktionale Transformation von XML (Visual Basic)
In diesem Thema wird der Ansatz der reinen funktionalen Transformation zum Ändern von XML-Dokumenten erläutert und dem prozeduralen Ansatz gegenübergestellt.  
  
## <a name="modifying-an-xml-document"></a>Ändern eines XML-Dokuments  
 Eine der häufigsten Aufgaben, die XML-Programmierer zu lösen haben, ist das Transformieren von XML von einer Form in eine andere Form. Die Form eines XML-Dokuments wird durch die Struktur des Dokuments bestimmt. Zur Form gehört Folgendes:  
  
-   die durch das Dokument ausgedrückte Hierarchie  
  
-   die Element- und Attributnamen  
  
-   die Datentypen der Elemente und Attribute  
  
 Beim Transformieren von XML von einer Form in eine andere ist es in der Regel am effektivsten, mit der reinen funktionalen Transformation zu arbeiten. Bei dieser Herangehensweise muss der Programmierer in erster Linie eine Transformation erstellen, die auf das gesamte XML-Dokument (oder auf einen oder mehrere streng definierte Knoten) angewendet wird. Die funktionale Transformation ist (zumindest für Programmierer, die damit vertraut sind) sicher am einfachsten zu codieren, führt zu gut verwaltbarem Code und ist häufig kompakter als andere Herangehensweisen.  
  
### <a name="xml-functional-transformational-technologies"></a>Technologien für die funktionale XML-Transformation  
 Microsoft bietet zwei funktionale Transformationstechnologien für XML-Dokumente: XSLT und LINQ to XML. XSLT wird im verwalteten <xref:System.Xml.Xsl>-Namespace und in der systemeigenen COM-Implementierung von MSXML unterstützt. XSLT ist zwar eine robuste Technologie zum Ändern von XML-Dokumenten, erfordert aber Kenntnisse auf einem speziellen Gebiet: der XSLT-Sprache und der sie unterstützenden APIs.  
  
 LINQ to XML stellt die Tools bereit, die für das ausdrucksstarke und leistungsfähige Codieren reiner funktionaler Transformationen innerhalb des C#- und des Visual Basic-Codes benötigt werden. So verwenden z. B. viele der in der LINQ to XML-Dokumentation verwendeten Beispiele reine Funktionen. Auch in der [Lernprogramm: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) Lernprogramm verwenden wir LINQ to XML in funktionalen Konstruktion zum Bearbeiten von Informationen in Microsoft Word-Dokument.  
  
 Einen ausführlicheren Vergleich zwischen LINQ to XML und anderen XML-Technologien von Microsoft finden Sie unter [LINQ to XML vs.(LINQ to XML im Vergleich zu) Other XML Technologies (anderen XML-Technologien)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT ist das empfohlene Tool für dokumentorientierte Transformationen, wenn das Quelldokument eine unregelmäßige Struktur besitzt. Dokumentorientierte Transformationen können aber auch von LINQ to XML ausgeführt werden. Weitere Informationen finden Sie unter [wie: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in eine XSLT-Formatvorlage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in reine funktionale Transformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)  
 [LINQ to XML im Vergleich zu anderen XML-Technologien](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)  
 [LINQ to XML im Vergleich zu anderen XML-Technologien](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)
