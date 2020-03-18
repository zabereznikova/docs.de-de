---
title: LINQ to XML im Vergleich zu anderen XML-Technologien3
ms.date: 07/20/2015
ms.assetid: 01b8e746-12d3-471d-b811-7539e4547784
ms.openlocfilehash: 4cade6ecbee95ee288db34246986858609697731
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635677"
---
# <a name="linq-to-xml-vs-other-xml-technologies"></a>LINQ to XML im Vergleich zu anderen XML-Technologien
In diesem Thema wird [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit den folgenden XML-Technologien verglichen: <xref:System.Xml.XmlReader>, XSLT, MSXML und XmlLite. Diese Informationen helfen Ihnen bei Ihrer Entscheidung für eine dieser Technologien.  
  
 Einen Vergleich von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] mit dem Dokumentobjektmodell (DOM) finden Sie unter [LINQ to XML im Vergleich zu DOM (C#)](./linq-to-xml-vs-dom.md).  
  
## <a name="linq-to-xml-vs-xmlreader"></a>LINQ to XML im Vergleich zu XmlReader  
 <xref:System.Xml.XmlReader> ist ein schneller Parser, der ausschließlich in Vorwärtsrichtung und ohne Zwischenspeicherung arbeitet.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wird über <xref:System.Xml.XmlReader> implementiert. Beide sind eng ineinander integriert. Sie können <xref:System.Xml.XmlReader> jedoch auch allein verwenden.  
  
 Stellen Sie sich z. B. vor, Sie erstellen einen Internetdienst, der pro Sekunde Hunderte von XML-Dokumenten analysiert. Wenn alle Dokumente dieselbe Struktur aufweisen, müssen Sie zum Analysieren der XML-Dokumente nur eine einzige Implementierung schreiben. In diesem Fall ist es wahrscheinlich, dass Sie <xref:System.Xml.XmlReader> allein verwenden möchten.  
  
 Wenn Sie aber ein System erstellen, dass viele kleinere XML-Dokumente analysiert, die alle unterschiedlich sind, empfiehlt sich die Nutzung der höheren Produktivität, die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ermöglicht.  
  
## <a name="linq-to-xml-vs-xslt"></a>LINQ to XML im Vergleich zu XSLT  
 Sowohl [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] als auch XSLT bieten umfangreiche Funktionen zum Transformieren von XML-Dokumenten. XSLT ist ein regelbasierter, deklarativer Ansatz. Erfahrene XSLT-Programmierer schreiben XSLT-Code unter Verwendung eines funktionalen Programmierstils, bei dem der zustandslose Ansatz im Vordergrund steht. Transformationen können mit reinen Funktionen geschrieben werden, die ohne Nebeneffekte implementiert werden. Dieser regelbasierte oder funktionale Ansatz ist vielen Entwicklern nicht bekannt, und das Erlernen dieses Ansatzes kann schwierig und zeitaufwändig sein.  
  
 XSLT kann ein sehr produktives System sein, das leistungsstarke Anwendungen erbringt. Einige große Internetunternehmen verwenden XSLT beispielsweise als Möglichkeit, HTML-Daten aus XML-Code zu generieren, der aus verschiedenen Datenspeichern zusammengestellt wird. Die verwaltete XSLT-Engine kompiliert XSLT in CLR-Code und erweist sich in einigen Szenarios sogar als leistungsfähiger als die systemeigene XSLT-Engine.  
  
 Fakt ist aber, dass Entwickler bei Verwendung von XSLT nicht auf das vorhandene C#- und Visual Basic-Wissen zurückgreifen können. Stattdessen müssen sie Code in einer anderen und komplexen Programmiersprache schreiben. Die Verwendung zweier nicht integrierter Entwicklungssysteme, wie C# (oder Visual Basic) und XSLT, führt zu Softwaresystemen, die schwieriger zu entwickeln und zu verwalten sind.  
  
 Wenn Sie die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrageausdrücke erst einmal verstanden haben, bieten [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Transformationen eine leistungsstarke und einfach zu handhabende Technologie. Im Wesentlichen formen Sie Ihr XML-Dokument, indem Sie die funktionale Konstruktion verwenden, Daten aus verschiedenen Quellen herausziehen, dynamisch <xref:System.Xml.Linq.XElement>-Objekte erstellen und das Ganze dann zu einer neuen XML-Struktur zusammensetzen. Die Transformation kann ein vollkommen neues Dokument zum Ergebnis haben. Das Konstruieren von Transformationen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist relativ einfach und intuitiv, und der resultierende Code ist lesbar. Dies trägt zu geringeren Entwicklungs- und Wartungskosten bei.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist nicht dazu gedacht, XSLT zu ersetzen. XSLT ist für komplizierte und dokumentorientierte XML-Transformationen immer noch die beste Option. Dies gilt insbesondere dann, wenn die Struktur des Dokuments nicht gut definiert ist.  
  
 XSLT hat den Vorteil, ein World Wide Web Consortium (W3C)-Standard zu sein. Wenn bei Ihnen die Anforderung besteht, ausschließlich Standardtechnologien zu verwenden, ist XSLT möglicherweise das Richtige für Sie.  
  
 XSLT ist XML und kann daher programmgesteuert bearbeitet werden.  
  
## <a name="linq-to-xml-vs-msxml"></a>LINQ to XML im Vergleich zu MSXML  
 MSXML ist die COM-basierte Technologie für die XML-Verarbeitung in Microsoft Windows. MSXML stellt eine systemeigene Implementierung des DOM mit Unterstützung für XPath und XSLT bereit. Darüber hinaus enthält MSXML den ereignisbasierten, ohne Zwischenspeicherung arbeitenden Parser SAX2.  
  
 MSXML zeigt eine gute Leistung und ist in den meisten Szenarios standardmäßig sicher. Auf MSXML kann in Internet Explorer zugegriffen werden, sodass eine clientseitige XML-Verarbeitung in AJAX-Anwendungen erfolgen kann. MSXML kann mit jeder Programmiersprache verwendet werden, die COM unterstützt, wie z.B. C++, JavaScripts und Visual Basic 6.0.  
  
 Von der Verwendung von MSXML in verwaltetem Code, der auf der Common Language Runtime (CLR) basiert, wird abgeraten.  
  
## <a name="linq-to-xml-vs-xmllite"></a>LINQ to XML im Vergleich zu XmlLite  
 XmlLite ist ein Pull-Parser, der ausschließlich in Vorwärtsrichtung und ohne Zwischenspeicherung arbeitet. Entwickler verwenden XmlLite hauptsächlich zusammen mit C++. Es wird nicht empfohlen, XmlLite mit verwaltetem Code zu verwenden.  
  
 Der Hauptvorteil von XmlLite besteht darin, dass er ein leichter, schneller XML-Parser ist, der in den meisten Szenarios sicher ist. Seine Angriffsfläche ist sehr klein. Wenn Sie nicht vertrauenswürdige Dokumente analysieren müssen und sich vor Risiken, wie DoS-Angriffen oder der Offenlegung von Daten, schützen möchten, könnte XmlLite ein geeignetes Mittel der Wahl sein.  
  
 XmlLite ist nicht in LINQ (Language-Integrated Query) integriert. Die Produktivitätsverbesserungen für Programmierer, die zu den großen Vorteilen von LINQ gehören, können mit XmlLite nicht erzielt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte (LINQ to XML)](./linq-to-xml-overview.md)
