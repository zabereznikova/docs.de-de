---
title: LINQ to XML im Vergleich zu DOM (C#)
description: Hier erfahren Sie mehr über einige wichtige Unterschiede zwischen LINQ to XML und der XML-Programmier-API des W3C-Dokumentobjektmodells (DOM).
ms.date: 07/20/2015
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
ms.openlocfilehash: f5fc3fd7869079d47d7c9031e3668afeed7a117b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165346"
---
# <a name="linq-to-xml-vs-dom-c"></a>LINQ to XML im Vergleich zu DOM (C#)
In diesem Abschnitt werden einige der wichtigsten Unterschiede zwischen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] und der derzeit verbreitetsten XML-Programmier-API, dem W3C-Dokumentobjektmodell (DOM), beschrieben.  
  
## <a name="new-ways-to-construct-xml-trees"></a>Neue Möglichkeiten zum Konstruieren von XML-Strukturen  
 Im W3C-DOM erstellen Sie eine XML-Struktur von unten nach oben. Das bedeutet, Sie erstellen ein Dokument, Sie erstellen Elemente, und anschließend fügen Sie die Elemente dem Dokument hinzu.  
  
 Das folgende Beispiel zeigt eine typische Herangehensweise an das Erstellen einer XML-Struktur mit der Microsoft-Implementierung des DOM, <xref:System.Xml.XmlDocument>:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
XmlElement phone1 = doc.CreateElement("Phone");  
phone1.SetAttribute("Type", "Home");  
phone1.InnerText = "206-555-0144";
XmlElement phone2 = doc.CreateElement("Phone");  
phone2.SetAttribute("Type", "Work");  
phone2.InnerText = "425-555-0145";
XmlElement street1 = doc.CreateElement("Street1");
street1.InnerText = "123 Main St";  
XmlElement city = doc.CreateElement("City");  
city.InnerText = "Mercer Island";  
XmlElement state = doc.CreateElement("State");  
state.InnerText = "WA";  
XmlElement postal = doc.CreateElement("Postal");  
postal.InnerText = "68042";  
XmlElement address = doc.CreateElement("Address");  
address.AppendChild(street1);  
address.AppendChild(city);  
address.AppendChild(state);  
address.AppendChild(postal);  
XmlElement contact = doc.CreateElement("Contact");  
contact.AppendChild(name);  
contact.AppendChild(phone1);  
contact.AppendChild(phone2);  
contact.AppendChild(address);  
XmlElement contacts = doc.CreateElement("Contacts");  
contacts.AppendChild(contact);  
doc.AppendChild(contacts);  
```  
  
 Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] unterstützt diesen Ansatz der Erstellung einer XML-Struktur, aber auch einen alternativen Ansatz, die so genannte *funktionale Konstruktion*. Bei der funktionalen Konstruktion werden zum Erstellen einer XML-Struktur die Konstruktoren <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XAttribute> verwendet.  
  
 Das folgende Beispiel zeigt, wie Sie dieselbe XML-Struktur wie oben mit der funktionalen Konstruktion in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] konstruieren können:  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144",
                new XAttribute("Type", "Home")),  
            new XElement("phone", "425-555-0145",  
                new XAttribute("Type", "Work")),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 Die Codeeinzüge verdeutlichen den Aufbau des der XML-Struktur zugrunde liegenden XML-Codes.  
  
 Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](./linq-to-xml-overview.md).  
  
## <a name="working-directly-with-xml-elements"></a>Direktes Arbeiten mit XML-Elementen  
 Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten. So können Sie z. B. Folgendes tun:  
  
- Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen. Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.  
  
- Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.  
  
- Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.  
  
 Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird. Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden. Das folgende Codefragment erstellt ein Namenselement im DOM:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vermeidet diese Ebene der Komplexität.  
  
 Bei der Verwendung von LINQ to XML müssen Sie die <xref:System.Xml.Linq.XDocument>-Klasse nur dann verwenden, wenn Sie der Stammebene des Dokuments einen Kommentar oder eine Verarbeitungsanweisung hinzufügen möchten.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Vereinfachte Handhabung von Namen und Namespaces  
 Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht Namen und Namespaces, weil der Umgang mit Namespacepräfixen nicht zwingend erforderlich ist. Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können. Wenn Sie sich aber dafür entscheiden, sich nicht mehr explizit um die Steuerung der Namespacepräfixe kümmern zu wollen, weist [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bei der Serialisierung, wo erforderlich, entsprechende Namespacepräfixe zu oder greift für die Serialisierung auf die Standardnamespaces zurück. Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe. Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt. Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vermeidet dieses Problem, indem es Ihnen ermöglicht wird, für einen Knoten die <xref:System.Xml.Linq.XName>-Eigenschaft festzulegen.  
  
## <a name="static-method-support-for-loading-xml"></a>Unterstützung statischer Methoden für das Laden von XML  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie zum Laden von XML anstelle von Instanzmethoden statische Methoden verwenden. Dadurch vereinfacht sich das Laden und das Analysieren. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von XML aus einer Datei (C#)](./how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Entfernung der Unterstützung für DTD-Konstrukte  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird. Die Verwaltung von Entitäten ist komplex und wird selten verwendet. Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht. Beim Auffüllen einer [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Struktur werden alle DTD-Entitäten erweitert.  
  
## <a name="support-for-fragments"></a>Unterstützung für Fragmente  
 In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gibt es keine Entsprechung für die Klasse `XmlDocumentFragment`. In vielen Fällen lassen sich aber mit dem Ergebnis einer Abfrage, die als `XmlDocumentFragment`-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> oder als <xref:System.Xml.Linq.XNode>-Schnittstelle von <xref:System.Collections.Generic.IEnumerable%601> typisiert ist, die gleichen Ergebnisse wie mit der <xref:System.Xml.Linq.XElement>-Klasse erzielen.  
  
## <a name="support-for-xpathnavigator"></a>Unterstützung für XPathNavigator  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet über die Erweiterungsmethoden im <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespace Unterstützung für <xref:System.Xml.XPath.XPathNavigator>. Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
## <a name="support-for-white-space-and-indentation"></a>Unterstützung für Leerraum und Einzüge  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] handhabt Leerzeichen einfacher als das DOM.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] speichert Leerraum als <xref:System.Xml.Linq.XText>-Knoten und nicht als speziellen <xref:System.Xml.XmlNodeType.Whitespace>-Knotentyp, wie dies im DOM der Fall ist.  
  
## <a name="support-for-annotations"></a>Unterstützung für Anmerkungen  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen. Dies ist hilfreich, wenn verschiedene Informationen zu einem Element nachverfolgt werden sollen, z.B. Schemainformationen, die Information, ob das Element an eine Benutzeroberfläche gebunden ist, oder andere anwendungsspezifische Informationen. Weitere Informationen finden Sie unter [Anmerkungen zu LINQ to XML](./linq-to-xml-annotations.md).  
  
## <a name="support-for-schema-information"></a>Unterstützung für Schemainformationen  
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] bietet über die Erweiterungsmethoden im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace Unterstützung für die XSD-Validierung. Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet. Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen. Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen mithilfe von XSD](./how-to-validate-using-xsd-linq-to-xml.md) und <xref:System.Xml.Schema.Extensions>.
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte (LINQ to XML)](./linq-to-xml-overview.md)
