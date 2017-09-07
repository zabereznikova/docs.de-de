---
title: Funktionale Transformation von XML (C#)
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
ms.assetid: 0ccb9251-38d7-44e3-9b84-1b5fe25e4b59
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 57b4d25b7c2257c16401339f590b3487fba7d12a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="functional-transformation-of-xml-c"></a>Funktionale Transformation von XML (C#)
In diesem Thema wird der Ansatz der reinen funktionalen Transformation zum Ändern von XML-Dokumenten erläutert und dem prozeduralen Ansatz gegenübergestellt.  
  
## <a name="modifying-an-xml-document"></a>Ändern eines XML-Dokuments  
 Eine der häufigsten Aufgaben, die XML-Programmierer zu lösen haben, ist das Transformieren von XML von einer Form in eine andere Form. Die Form eines XML-Dokuments wird durch die Struktur des Dokuments bestimmt. Zur Form gehört Folgendes:  
  
-   die durch das Dokument ausgedrückte Hierarchie  
  
-   die Element- und Attributnamen  
  
-   die Datentypen der Elemente und Attribute  
  
 Beim Transformieren von XML von einer Form in eine andere ist es in der Regel am effektivsten, mit der reinen funktionalen Transformation zu arbeiten. Bei dieser Herangehensweise muss der Programmierer in erster Linie eine Transformation erstellen, die auf das gesamte XML-Dokument (oder auf einen oder mehrere streng definierte Knoten) angewendet wird. Die funktionale Transformation ist (zumindest für Programmierer, die damit vertraut sind) sicher am einfachsten zu codieren, führt zu gut verwaltbarem Code und ist häufig kompakter als andere Herangehensweisen.  
  
### <a name="xml-functional-transformational-technologies"></a>Technologien für die funktionale XML-Transformation  
 Microsoft bietet zwei funktionale Transformationstechnologien für XML-Dokumente: XSLT und LINQ to XML. XSLT wird im verwalteten <xref:System.Xml.Xsl>-Namespace und in der systemeigenen COM-Implementierung von MSXML unterstützt. XSLT ist zwar eine robuste Technologie zum Ändern von XML-Dokumenten, erfordert aber Kenntnisse auf einem speziellen Gebiet: der XSLT-Sprache und der sie unterstützenden APIs.  
  
 LINQ to XML stellt die Tools bereit, die für das ausdrucksstarke und leistungsfähige Codieren reiner funktionaler Transformationen innerhalb des C#- und des Visual Basic-Codes benötigt werden. So verwenden z. B. viele der in der LINQ to XML-Dokumentation verwendeten Beispiele reine Funktionen. Auch im [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (C#))](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md) wird LINQ to XML in einer funktionalen Herangehensweise verwendet, um Informationen in einem Microsoft Word-Dokument zu bearbeiten.  
  
 Einen ausführlicheren Vergleich zwischen LINQ to XML und anderen XML-Technologien von Microsoft finden Sie unter [LINQ to XML vs.(LINQ to XML im Vergleich zu) Other XML Technologies (anderen XML-Technologien)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md).  
  
 XSLT ist das empfohlene Tool für dokumentorientierte Transformationen, wenn das Quelldokument eine unregelmäßige Struktur besitzt. Dokumentorientierte Transformationen können aber auch von LINQ to XML ausgeführt werden. Weitere Informationen finden Sie unter [How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (C#) (Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Bäumen in eine XSLT-Formatvorlage (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in reine funktionale Transformationen (c#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md)   
 [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#))](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)   
 [LINQ to XML im Vergleich zu anderen XML-Technologien](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-vs-other-xml-technologies.md)

