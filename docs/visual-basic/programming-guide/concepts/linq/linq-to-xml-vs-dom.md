---
title: LINQ to XML im Vergleich zu DOM (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 18c36130-d598-40b7-9007-828232252978
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
ms.openlocfilehash: 88b6bddcdeec2859844f5d5f94777146d488b5fb
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-vs-dom-visual-basic"></a>LINQ to XML im Vergleich zu DOM (Visual Basic)
Dieser Abschnitt beschreibt einige wichtige Unterschiede zwischen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] und die aktuelle verbreitetsten XML-Programmier-API, die W3C Document Objekt Model (DOM).  
  
## <a name="new-ways-to-construct-xml-trees"></a>Neue Möglichkeiten zum Konstruieren von XML-Strukturen  
 Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.  
  
 Z. B. wäre Folgendes ein übliches Verfahren zum Erstellen einer XML-Struktur, die mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:</xref:System.Xml.XmlDocument>  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
Dim phone1 As XmlElement = doc.CreateElement("Phone")  
phone1.SetAttribute("Type", "Home")  
phone1.InnerText = "206-555-0144"  
Dim phone2 As XmlElement = doc.CreateElement("Phone")  
phone2.SetAttribute("Type", "Work")  
phone2.InnerText = "425-555-0145"  
Dim street1 As XmlElement = doc.CreateElement("Street1")  
street1.InnerText = "123 Main St"  
Dim city As XmlElement = doc.CreateElement("City")  
city.InnerText = "Mercer Island"  
Dim state As XmlElement = doc.CreateElement("State")  
state.InnerText = "WA"  
Dim postal As XmlElement = doc.CreateElement("Postal")  
postal.InnerText = "68042"  
Dim address As XmlElement = doc.CreateElement("Address")  
address.AppendChild(street1)  
address.AppendChild(city)  
address.AppendChild(state)  
address.AppendChild(postal)  
Dim contact As XmlElement = doc.CreateElement("Contact")  
contact.AppendChild(name)  
contact.AppendChild(phone1)  
contact.AppendChild(phone2)  
contact.AppendChild(address)  
Dim contacts As XmlElement = doc.CreateElement("Contacts")  
contacts.AppendChild(contact)  
doc.AppendChild(contacts)  
Console.WriteLine(doc.OuterXml)  
```  
  
 Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]unterstützt diese Möglichkeit zum Konstruieren einer XML-Struktur, aber auch einen alternativen Ansatz, *funktionale Konstruktion*. In Visual Basic verwendet die funktionaler Konstruktion XML-Literale zum Erstellen einer XML-Struktur.  
  
 Hier ist, wie Sie mithilfe die gleiche XML-Struktur erstellen würde [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] funktionale Konstruktion:  
  
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
  
 Die Codeeinzüge verdeutlichen den Aufbau des der XML-Struktur zugrunde liegenden XML-Codes.  
  
 Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="working-directly-with-xml-elements"></a>Direktes Arbeiten mit XML-Elementen  
 Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten. So können Sie z. B. Folgendes tun:  
  
-   Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen. Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.  
  
-   Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.  
  
-   Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.  
  
 Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird. Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden. Das folgende Codefragment erstellt ein Namenselement im DOM:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]vermeidet diese Ebene der Komplexität.  
  
 Wenn Sie LINQ to XML verwenden, verwenden Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur, wenn Sie auf der Stammebene des Dokuments einen Kommentar oder eine verarbeitungsanweisung hinzufügen möchten.</xref:System.Xml.Linq.XDocument>  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Vereinfachte Handhabung von Namen und Namespaces  
 Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]vereinfacht Namen und Namespaces Gerätetreiberschnittstellen einzufügen, die Anforderung für den Umgang mit Namespacepräfixen. Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können. Aber wenn Sie sich entscheiden, nicht explizit steuern von Namespacepräfixen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] weist Namespacepräfixe während der Serialisierung erforderlich sind, oder wird die Serialisierung Standardnamespaces sind. Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe. Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt. Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]vermeidet dieses Problem durch die Möglichkeit zum Festlegen der <xref:System.Xml.Linq.XName>Eigenschaft auf einem Knoten.</xref:System.Xml.Linq.XName>  
  
## <a name="static-method-support-for-loading-xml"></a>Unterstützung statischer Methoden für das Laden von XML  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Sie können XML zu laden, indem Sie anstelle von Instanzmethoden statische Methoden verwenden. Dadurch vereinfacht sich das Laden und das Analysieren. Weitere Informationen finden Sie unter [Gewusst wie: Laden von XML aus einer Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Entfernung der Unterstützung für DTD-Konstrukte  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird. Die Verwaltung von Entitäten ist komplex und wird selten verwendet. Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht. Wenn eine [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Struktur aufgefüllt wird, werden alle DTD-Entitäten erweitert.  
  
## <a name="support-for-fragments"></a>Unterstützung für Fragmente  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]bietet keine Entsprechung für die `XmlDocumentFragment` Klasse. In vielen Fällen jedoch die `XmlDocumentFragment` Konzept behandelt werden kann, durch das Ergebnis einer Abfrage, die typisiert wird <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XNode>, oder <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XNode> </xref:System.Collections.Generic.IEnumerable%601>  
  
## <a name="support-for-xpathnavigator"></a>Unterstützung für XPathNavigator  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]bietet Unterstützung für <xref:System.Xml.XPath.XPathNavigator>durch Erweiterungsmethoden in den <xref:System.Xml.XPath?displayProperty=fullName>Namespace.</xref:System.Xml.XPath?displayProperty=fullName> </xref:System.Xml.XPath.XPathNavigator> Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.</xref:System.Xml.XPath.Extensions?displayProperty=fullName>  
  
## <a name="support-for-white-space-and-indentation"></a>Unterstützung für Leerraum und Einzüge  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]handhabt Leerzeichen einfacher als das DOM.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]Speichert Leerraum als ein <xref:System.Xml.Linq.XText>-Knoten und kein speziellen <xref:System.Xml.XmlNodeType>Knotentyp, wie dies im DOM der Fall ist.</xref:System.Xml.XmlNodeType> </xref:System.Xml.Linq.XText>  
  
## <a name="support-for-annotations"></a>Unterstützung für Anmerkungen  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen. Dies ist nützlich zum Nachverfolgen von verschiedene Informationen zu einem Element, z. B. Schemainformationen, Informationen, ob das Element an eine Benutzeroberfläche gebunden ist oder eine beliebige andere Art von anwendungsspezifischen Informationen. Weitere Informationen finden Sie unter [LINQ to XML-Anmerkungen](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).  
  
## <a name="support-for-schema-information"></a>Unterstützung für Schemainformationen  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]bietet Unterstützung für XSD-Validierung durch Erweiterungsmethoden in den <xref:System.Xml.Schema?displayProperty=fullName>Namespace.</xref:System.Xml.Schema?displayProperty=fullName> Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet. Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen. Weitere Informationen finden Sie unter [Gewusst wie: Überprüfen Sie mithilfe von XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) und <xref:System.Xml.Schema.Extensions>.</xref:System.Xml.Schema.Extensions>  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
