---
title: LINQ to XML im Vergleich zu Andere XML-Technologies2 | Microsoft-Dokumentation
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
ms.assetid: 72ce3a82-ffc6-488c-98e7-b9b40f3591ec
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
ms.openlocfilehash: 0254788fb9efa018e735a57990144c6b176d30d6
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML im Vergleich zu anderen XML-Technologien
In diesem Thema wird [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] mit den folgenden XML-Technologien: <xref:System.Xml.XmlReader>, XSLT, MSXML und XmlLite.</xref:System.Xml.XmlReader> Diese Informationen helfen Ihnen bei Ihrer Entscheidung für eine dieser Technologien.  
  
 Einen Vergleich der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] , die (DOKUMENTOBJEKTMODELL), finden Sie unter [LINQ to XML im Vergleich. DOM (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-vs-dom.md).  
  
## <a name="linq-to-xml-vs-xmlreader"></a>LINQ to XML im Vergleich zu XmlReader  
 <xref:System.Xml.XmlReader>ist ein schneller Vorwärtscursor, ohne Cache-Parser.</xref:System.Xml.XmlReader>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]wird implementiert, auf der Basis von <xref:System.Xml.XmlReader>, und sie sind eng integriert.</xref:System.Xml.XmlReader> Aber Sie können auch <xref:System.Xml.XmlReader>allein.</xref:System.Xml.XmlReader>  
  
 Stellen Sie sich z. B. vor, Sie erstellen einen Internetdienst, der pro Sekunde Hunderte von XML-Dokumenten analysiert. Wenn alle Dokumente dieselbe Struktur aufweisen, müssen Sie zum Analysieren der XML-Dokumente nur eine einzige Implementierung schreiben. In diesem Fall würde wahrscheinlich soll <xref:System.Xml.XmlReader>allein.</xref:System.Xml.XmlReader>  
  
 Im Gegensatz dazu erstellen Sie ein System, das viele kleinere XML-Dokumente analysiert, und jede unterscheidet, Sie möchten Nutzen der höheren Produktivität, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet.  
  
## <a name="linq-to-xml-vs-xslt"></a>LINQ to XML im Vergleich zu XSLT  
 Beide [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] auch XSLT bieten umfangreiche Funktionen zum XML-Dokuments transformieren. XSLT ist ein regelbasierter, deklarativer Ansatz. Erfahrene XSLT-Programmierer schreiben XSLT-Code unter Verwendung eines funktionalen Programmierstils, bei dem der zustandslose Ansatz im Vordergrund steht. Transformationen können mit reinen Funktionen geschrieben werden, die ohne Nebeneffekte implementiert werden. Dieser regelbasierte oder funktionale Ansatz ist vielen Entwicklern nicht bekannt, und das Erlernen dieses Ansatzes kann schwierig und zeitaufwändig sein.  
  
 XSLT kann ein sehr produktives System sein, das leistungsstarke Anwendungen erbringt. Einige große Internetunternehmen verwenden XSLT beispielsweise als Möglichkeit, HTML-Daten aus XML-Code zu generieren, der aus verschiedenen Datenspeichern zusammengestellt wird. Das verwaltete XSLT-Modul kompiliert XSLT in CLR-Code und erweist sich in einigen Szenarios sogar als leistungsfähiger als das systemeigene XSLT-Modul.  
  
 Fakt ist aber, dass Entwickler bei Verwendung von XSLT nicht auf das vorhandene C#- und Visual Basic-Wissen zurückgreifen können. Stattdessen müssen sie Code in einer anderen und komplexen Programmiersprache schreiben. Die Verwendung zweier nicht integrierter Entwicklungssysteme, wie C# (oder Visual Basic) und XSLT, führt zu Softwaresystemen, die schwieriger zu entwickeln und zu verwalten sind.  
  
 Nachdem Sie erst einmal verstanden haben [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Abfrageausdrücke, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Transformationen eine leistungsstarke Technologie, einfach zu verwenden ist. Im Wesentlichen Formen Sie Ihr XML-Dokument mittels funktionalen Konstruktion in Daten aus verschiedenen Quellen herausziehen, Erstellen von <xref:System.Xml.Linq.XElement>-Objekte dynamisch und das ganze dann zu einer neuen XML-Struktur zusammensetzen.</xref:System.Xml.Linq.XElement> Die Transformation kann ein vollkommen neues Dokument zum Ergebnis haben. Konstruieren von Transformationen in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist relativ einfach und intuitiv, und der resultierende Code ist lesbar. Dies trägt zu geringeren Entwicklungs- und Wartungskosten bei.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist nicht dazu gedacht, XSLT zu ersetzen. XSLT ist für komplizierte und dokumentorientierte XML-Transformationen immer noch die beste Option. Dies gilt insbesondere dann, wenn die Struktur des Dokuments nicht gut definiert ist.  
  
 XSLT hat den Vorteil, ein World Wide Web Consortium (W3C)-Standard zu sein. Wenn bei Ihnen die Anforderung besteht, ausschließlich Standardtechnologien zu verwenden, ist XSLT möglicherweise das Richtige für Sie.  
  
 XSLT ist XML und kann daher programmgesteuert bearbeitet werden.  
  
## <a name="linq-to-xml-vs-msxml"></a>LINQ to XML im Vergleich zu MSXML  
 MSXML ist die COM-basierte Technologie für die XML-Verarbeitung in Microsoft Windows. MSXML stellt eine systemeigene Implementierung des DOM mit Unterstützung für XPath und XSLT bereit. Darüber hinaus enthält MSXML den ereignisbasierten, ohne Zwischenspeicherung arbeitenden Parser SAX2.  
  
 MSXML zeigt eine gute Leistung und ist in den meisten Szenarios standardmäßig sicher. Auf MSXML kann in Internet Explorer zugegriffen werden, sodass eine clientseitige XML-Verarbeitung in AJAX-Anwendungen erfolgen kann. MSXML kann von jeder Programmiersprache aus verwendet werden, die COM unterstützt, wie z. B. C++, JavaScripts und [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0.  
  
 Von der Verwendung von MSXML in verwaltetem Code, der auf der Common Language Runtime (CLR) basiert, wird abgeraten.  
  
## <a name="linq-to-xml-vs-xmllite"></a>LINQ to XML im Vergleich zu XmlLite  
 XmlLite ist ein Pull-Parser, der ausschließlich in Vorwärtsrichtung und ohne Zwischenspeicherung arbeitet. Entwickler verwenden XmlLite hauptsächlich zusammen mit C++. Es wird nicht empfohlen, XmlLite mit verwaltetem Code zu verwenden.  
  
 Der Hauptvorteil von XmlLite besteht darin, dass er ein leichter, schneller XML-Parser ist, der in den meisten Szenarios sicher ist. Seine Angriffsfläche ist sehr klein. Wenn Sie nicht vertrauenswürdige Dokumente analysieren müssen und sich vor Risiken, wie DoS-Angriffen oder der Offenlegung von Daten, schützen möchten, könnte XmlLite ein geeignetes Mittel der Wahl sein.  
  
 XmlLite ist nicht in [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] integriert. Dies ergibt keine Programmierer Steigerung der Produktivität, die die produktivitätsverbesserungen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
