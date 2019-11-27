---
title: LINQ to XML kontra DOM
ms.date: 07/20/2015
ms.assetid: 18c36130-d598-40b7-9007-828232252978
ms.openlocfilehash: b25993fba4d878beb881dfdc46effe5a8ab3485b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331702"
---
# <a name="linq-to-xml-vs-dom-visual-basic"></a>LINQ to XML im Vergleich zu Dom (Visual Basic)
In diesem Abschnitt werden einige der wichtigsten Unterschiede zwischen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] und der derzeit verbreitetsten XML-Programmier-API, dem W3C-Dokumentobjektmodell (DOM), beschrieben.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Neue Möglichkeiten zum Konstruieren von XML-Strukturen  
 Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.  
  
 Das folgende Beispiel zeigt eine typische Herangehensweise an das Erstellen einer XML-Struktur mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:  
  
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
  
 Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterstützt diesen Ansatz der Erstellung einer XML-Struktur, aber auch einen alternativen Ansatz, die so genannte *funktionale Konstruktion*. In Visual Basic verwendet die funktionale Konstruktion XML-Literale, um eine XML-Struktur zu erstellen.  
  
 Das folgende Beispiel zeigt, wie Sie dieselbe XML-Struktur wie oben mit der funktionalen Konstruktion in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] konstruieren können:  
  
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
 Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten. Sie können z. B. folgendermaßen vorgehen:  
  
- Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen. Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.  
  
- Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.  
  
- Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.  
  
 Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird. Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden. Das folgende Codefragment erstellt ein Namenselement im DOM:  
  
```vb  
Dim doc As XmlDocument = New XmlDocument()  
Dim name As XmlElement = doc.CreateElement("Name")  
name.InnerText = "Patrick Hines"  
doc.AppendChild(name)  
```  
  
 Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vermeidet diese Ebene der Komplexität.  
  
 Bei der Verwendung von LINQ to XML müssen Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur dann verwenden, wenn Sie der Stammebene des Dokuments einen Kommentar oder eine Verarbeitungsanweisung hinzufügen möchten.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Vereinfachte Handhabung von Namen und Namespaces  
 Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht Namen und Namespaces, weil der Umgang mit Namespacepräfixen nicht zwingend erforderlich ist. Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können. Wenn Sie sich aber dafür entscheiden, sich nicht mehr explizit um die Steuerung der Namespacepräfixe kümmern zu wollen, weist [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bei der Serialisierung, wo erforderlich, entsprechende Namespacepräfixe zu oder greift für die Serialisierung auf die Standardnamespaces zurück. Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe. Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).  
  
 Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt. Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vermeidet dieses Problem, indem es Ihnen ermöglicht wird, für einen Knoten die <xref:System.Xml.Linq.XName>-Eigenschaft festzulegen.  
  
## <a name="static-method-support-for-loading-xml"></a>Unterstützung statischer Methoden für das Laden von XML  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Laden von XML anstelle von Instanzmethoden statische Methoden verwenden. Dadurch vereinfacht sich das Laden und das Analysieren. Weitere Informationen finden Sie unter Gewusst [wie: Laden von XML aus einer Datei (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Entfernung der Unterstützung für DTD-Konstrukte  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird. Die Verwaltung von Entitäten ist komplex und wird selten verwendet. Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht. Beim Auffüllen einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Struktur werden alle DTD-Entitäten erweitert.  
  
## <a name="support-for-fragments"></a>Unterstützung für Fragmente  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gibt es keine Entsprechung für die Klasse `XmlDocumentFragment`. In vielen Fällen lassen sich aber mit dem Ergebnis einer Abfrage, die als `XmlDocumentFragment`-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> oder als <xref:System.Xml.Linq.XNode>-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> typisiert ist, die gleichen Ergebnisse wie mit der <xref:System.Xml.Linq.XElement>-Klasse erzielen.  
  
## <a name="support-for-xpathnavigator"></a>Unterstützung für XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet über die Erweiterungsmethoden im <xref:System.Xml.XPath.XPathNavigator>-Namespace Unterstützung für <xref:System.Xml.XPath?displayProperty=nameWithType>. Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Unterstützung für Leerraum und Einzüge  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] handhabt Leerzeichen einfacher als das DOM.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] speichert Leerraum als <xref:System.Xml.Linq.XText>-Knoten und nicht als speziellen <xref:System.Xml.XmlNodeType.Whitespace>-Knotentyp, wie dies im DOM der Fall ist.  
  
## <a name="support-for-annotations"></a>Unterstützung für Anmerkungen  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen. Dies ist hilfreich, wenn verschiedene Informationen zu einem Element nachverfolgt werden sollen, z.B. Schemainformationen, die Information, ob das Element an eine Benutzeroberfläche gebunden ist, oder andere anwendungsspezifische Informationen. Weitere Informationen finden Sie unter [Anmerkungen zu LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Unterstützung für Schemainformationen  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet über die Erweiterungsmethoden im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace Unterstützung für die XSD-Validierung. Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet. Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen. Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen mithilfe von XSD](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) und <xref:System.Xml.Schema.Extensions>.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
