---
title: Funktionale Transformation von XML (C#)
description: Hier erfahren Sie, wie Sie XML-Dokumente mithilfe des reinen funktionalen Transformationsansatzes in C# ändern und wie sich dieser von einem prozeduralen Ansatz unterscheidet.
ms.date: 07/20/2015
ms.assetid: 0ccb9251-38d7-44e3-9b84-1b5fe25e4b59
ms.openlocfilehash: 4ccc6859f3663eb3760c7faeaf115a5e88a2278a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103674"
---
# <a name="functional-transformation-of-xml-c"></a>Funktionale Transformation von XML (C#)
In diesem Thema wird der Ansatz der reinen funktionalen Transformation zum Ändern von XML-Dokumenten erläutert und dem prozeduralen Ansatz gegenübergestellt.  
  
## <a name="modifying-an-xml-document"></a>Ändern eines XML-Dokuments  
 Eine der häufigsten Aufgaben, die XML-Programmierer zu lösen haben, ist das Transformieren von XML von einer Form in eine andere Form. Die Form eines XML-Dokuments wird durch die Struktur des Dokuments bestimmt. Zur Form gehört Folgendes:  
  
- die durch das Dokument ausgedrückte Hierarchie  
  
- die Element- und Attributnamen  
  
- die Datentypen der Elemente und Attribute  
  
 Beim Transformieren von XML von einer Form in eine andere ist es in der Regel am effektivsten, mit der reinen funktionalen Transformation zu arbeiten. Bei dieser Herangehensweise muss der Programmierer in erster Linie eine Transformation erstellen, die auf das gesamte XML-Dokument (oder auf einen oder mehrere streng definierte Knoten) angewendet wird. Die funktionale Transformation ist (zumindest für Programmierer, die damit vertraut sind) sicher am einfachsten zu codieren, führt zu gut verwaltbarem Code und ist häufig kompakter als andere Herangehensweisen.  
  
### <a name="xml-functional-transformational-technologies"></a>Technologien für die funktionale XML-Transformation  
 Microsoft bietet zwei funktionale Transformationstechnologien für XML-Dokumente: XSLT und LINQ to XML. XSLT wird im verwalteten <xref:System.Xml.Xsl>-Namespace und in der systemeigenen COM-Implementierung von MSXML unterstützt. XSLT ist zwar eine robuste Technologie zum Ändern von XML-Dokumenten, erfordert aber Kenntnisse auf einem speziellen Gebiet: der XSLT-Sprache und der sie unterstützenden APIs.  
  
 LINQ to XML stellt die Tools bereit, die für das ausdrucksstarke und leistungsfähige Codieren reiner funktionaler Transformationen innerhalb des C#- und des Visual Basic-Codes benötigt werden. So verwenden z. B. viele der in der LINQ to XML-Dokumentation verwendeten Beispiele reine Funktionen. Auch im [Tutorial: Manipulating Content in a WordprocessingML Document (C#) (Tutorial: Bearbeiten des Inhalts eines WordprocessingML-Dokuments (C#))](./shape-of-wordprocessingml-documents.md) wird LINQ to XML in einer funktionalen Herangehensweise verwendet, um Informationen in einem Microsoft Word-Dokument zu bearbeiten.  
  
 Einen ausführlicheren Vergleich zwischen LINQ to XML und anderen XML-Technologien von Microsoft finden Sie unter [LINQ to XML vs.(LINQ to XML im Vergleich zu) Other XML Technologies (anderen XML-Technologien)](./linq-to-xml-vs-other-xml-technologies.md).  
  
XSLT ist das empfohlene Tool für dokumentorientierte Transformationen, wenn das Quelldokument eine unregelmäßige Struktur besitzt. Dokumentorientierte Transformationen können aber auch von LINQ to XML ausgeführt werden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von Anmerkungen zum Transformieren von LINQ to XML-Strukturen in einer XSLT-Formatvorlage (C#)](./how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style.md).
  
## <a name="see-also"></a>Siehe auch

- [Introduction to Pure Functional Transformations (C#) (Einführung in reine funktionale Transformationen (c#))](./introduction-to-pure-functional-transformations.md)
- [Tutorial: Bearbeiten von Inhalten in einem WordprocessingML-Dokument (C#)](./shape-of-wordprocessingml-documents.md)
- [LINQ to XML im Vergleich zu anderen XML-Technologien](./linq-to-xml-vs-other-xml-technologies.md)
