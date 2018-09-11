---
title: LINQ to XML-Übersicht (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: 962fddcfec04259425c1094f07adf0e3966dfab0
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44361818"
---
# <a name="linq-to-xml-overview-visual-basic"></a>LINQ to XML-Übersicht (Visual Basic)
XML hat sich mittlerweile als hervorragende Möglichkeit durchgesetzt, Daten in einer Vielzahl von Kontexten zu formatieren. Sie finden XML beispielsweise im Internet, in Konfigurationsdateien, in Microsoft Office Word-Dateien und in Datenbanken.  
  
 Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] steht Ihnen ein topaktueller, völlig neu gestalteter Ansatz für die Programmierung mit XML zur Verfügung, der die DOM-Funktionen (Dokumentobjektmodell) zum Ändern von Dokumenten im Arbeitsspeicher als auch die Unterstützung für [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdrücke in sich vereint. Obwohl sich diese Abfrageausdrücke syntaktisch von XPath unterscheiden, bieten sie eine ähnliche Funktionalität.  
  
## <a name="linq-to-xml-developers"></a>LINQ to XML-Entwickler  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eignet sich für ein breites Spektrum von Entwicklern. Für einen ganz normalen Entwickler, der einfach eine Aufgabe erledigen möchte, vereinfacht [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Arbeiten mit XML, weil der Umgang mit Abfragen ähnlich wie in SQL ist. Programmierer werden so innerhalb kurzer Zeit in die Lage versetzt, kompakte und dennoch leistungsfähige Abfragen in der Programmiersprache ihrer Wahl zu erstellen.  
  
 Professionelle Entwickler können mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ihre Produktivität deutlich steigern. Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] muss weniger Code geschrieben werden, und dieser Code ist ausdrucksvoller, kompakter und leistungsstärker. Sie können Abfrageausdrücke aus mehreren Datendomänen gleichzeitig verwenden.  
  
## <a name="what-is-linq-to-xml"></a>Was ist LINQ to XML?  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist eine LINQ-fähige XML-Programmierschnittstelle im Arbeitsspeicher, mit der Sie aus [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Programmiersprachen heraus mit XML arbeiten können.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ähnelt dem Dokumentobjektmodell (DOM) darin, dass das XML-Dokument im Arbeitsspeicher bereitgestellt wird. Sie können das Dokument abfragen und ändern, und nach dem Ändern können Sie es in einer Datei speichern oder es serialisieren und über das Internet versenden. Allerdings [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterscheidet sich vom DOM: Es bietet ein neues Objektmodell, das leichter und einfacher zu handhaben und, die nutzt Sprachfeatures in Visual Basic.  
  
 Der wichtigste Vorteil von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] besteht in dessen Integration in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Diese Integration ermöglicht es Ihnen, Abfragen für das XML-Dokument im Arbeitsspeicher zu schreiben, um Auflistungen von Elementen und Attributen abzurufen. Die Abfragefunktion von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist von ihrer Funktionalität her mit der von XPath und XQuery vergleichbar, die Syntax ist allerdings eine andere. Die Integration von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in Visual Basic bietet eine stärkere Typisierung, syntaxüberprüfung und verbesserte Debuggerunterstützung.  
  
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
  
 Zusätzlich zu diesen [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Funktionen stellt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] eine verbesserte XML-Programmierschnittstelle bereit. Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie Folgendes durchführen:  
  
-   XML aus Dateien oder Streams laden  
  
-   XML in Dateien oder Streams serialisieren  
  
-   XML mittels funktionaler Konstruktion von Grund auf neu erstellen  
  
-   XML mit XPath-ähnlichen Achsen abfragen  
  
-   XML-Strukturen im Arbeitsspeicher mit Methoden wie <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> und <xref:System.Xml.Linq.XElement.SetValue%2A> bearbeiten  
  
-   XML-Strukturen mit XSD validieren  
  
-   XML-Strukturen mit einer Kombination aus diesen Funktionen von einer Form in eine andere transformieren  
  
## <a name="creating-xml-trees"></a>Erstellen von XML-Strukturen  
 Einer der bedeutendsten Vorteile beim Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist die einfache Erstellung von XML-Strukturen. Beispielsweise können um eine kleine XML-Struktur zu erstellen, Sie Code wie folgt schreiben:  
  
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
  
 Visual Basic-Compiler übersetzt XML-Literale in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Methodenaufrufe.  
  
 Weitere Informationen finden Sie unter [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq>  
- [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)  
- [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
