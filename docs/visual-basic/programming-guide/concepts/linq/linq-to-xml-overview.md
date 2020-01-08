---
title: Übersicht über LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: a30340e06a3f8eac9fe2b7718b14ba20363d682f
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636470"
---
# <a name="linq-to-xml-overview-visual-basic"></a>Übersicht über LINQ to XML (Visual Basic)
XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren. Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.  
  
 Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung, Sie stellt die in-Memory-Funktionen für die Dokument Änderung des Dokumentobjektmodell (DOM) bereit und unterstützt LINQ-Abfrage Ausdrücke. Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.  
  
## <a name="linq-to-xml-developers"></a>LINQ to XML-Entwickler  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eignet sich für ein breites Spektrum von Entwicklern. Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist. Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.  
  
 Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ihre Produktivität deutlich steigern. Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker. Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.  
  
## <a name="what-is-linq-to-xml"></a>Was ist LINQ to XML?  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie in .NET Framework-Programmiersprachen mit XML arbeiten können.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ähnelt dem Dokumentobjektmodell (DOM) darin, dass das XML-Dokument im Arbeitsspeicher bereitgestellt wird. Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterscheidet sich jedoch vom Dom: Es stellt ein neues Objektmodell bereit, das weniger gewichtet und leichter zu arbeiten ist und die Sprachfunktionen in Visual Basic nutzt.  
  
 Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Integration in Language-Integrated Query (LINQ). Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen. Die Abfragefunktion von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere. Die Integration von LINQ in Visual Basic bietet eine stärkere Typisierung, Überprüfung der Kompilierzeit und verbesserte Debuggerunterstützung.  
  
 Ein weiterer Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die Fähigkeit, Abfrageergebnisse als Parameter für <xref:System.Xml.Linq.XElement>-Objektkonstruktoren und <xref:System.Xml.Linq.XAttribute>-Objektkonstruktoren zu verwenden. Dies ist ein sehr effizienter Ansatz zum Erstellen von XML-Strukturen. Diese Herangehensweise, die als *funktionale Konstruktion* bezeichnet wird, versetzt Entwickler in die Lage, XML-Strukturen problemlos von einer Form in eine andere zu transformieren.  
  
 Angenommen, Ihnen liegt eine typische XML-Bestellung, wie in [XML-Beispieldatei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) vor. Durch die Verwendung von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Abrufen des Attributwerts der Teilenummer für jedes Artikelelement im Auftrag die folgende Abfrage ausführen:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 Ein anderes Beispiel: Sie möchten, sortiert nach Teilenummer, eine Liste der Artikel abfragen, deren Wert über 100 Dollar liegt. Zum Abfragen dieser Informationen könnten Sie die folgende Abfrage ausführen:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 Zusätzlich zu diesen LINQ-Funktionen bietet [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eine verbesserte XML-Programmierschnittstelle. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet folgende Möglichkeiten:  
  
- XML aus Dateien oder Streams laden  
  
- XML in Dateien oder Streams serialisieren  
  
- XML mittels funktionaler Konstruktion von Grund auf neu erstellen  
  
- XML mit XPath-ähnlichen Achsen abfragen  
  
- XML-Strukturen im Arbeitsspeicher mit Methoden wie <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> und <xref:System.Xml.Linq.XElement.SetValue%2A> bearbeiten  
  
- XML-Strukturen mit XSD validieren  
  
- XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren  
  
## <a name="creating-xml-trees"></a>Erstellen von XML-Strukturen  
 Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die einfache Erstellung von XML-Strukturen. Wenn Sie z. b. eine kleine XML-Struktur erstellen möchten, können Sie Code wie folgt schreiben:  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 Der Visual Basic-Compiler übersetzt XML-Literale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methodenaufrufe.  
  
 Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq>
- [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
