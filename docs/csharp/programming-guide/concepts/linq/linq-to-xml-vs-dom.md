---
title: LINQ to XML im Vergleich zu DOM (C#) | Microsoft-Dokumentation
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
ms.assetid: 51c0e3d2-c047-4e6a-a423-d61a882400b7
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4734d82ef2f912e76a2e7a3dbc4ab3a2f45382b1
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-vs-dom-c"></a>LINQ to XML im Vergleich zu DOM (C#)
In diesem Abschnitt werden einige der wichtigsten Unterschiede zwischen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] und der derzeit verbreitetsten XML-Programmier-API, dem W3C-Dokumentobjektmodell (DOM), beschrieben.  
  
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
  
 Dieses Format der Codierung liefert keine ausführlichen visuellen Informationen zum Aufbau der XML-Struktur. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] unterstützt diesen Ansatz der Erstellung einer XML-Struktur, aber auch einen alternativen Ansatz, die so genannte *funktionale Konstruktion*. Die funktionale Konstruktion verwendet zum Erstellen einer XML-Struktur die Konstruktoren <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XAttribute>.  
  
 Das folgende Beispiel zeigt, wie Sie dieselbe XML-Struktur wie oben mit der funktionalen Konstruktion in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] konstruieren können:  
  
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
  
 Weitere Informationen finden Sie unter [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="working-directly-with-xml-elements"></a>Direktes Arbeiten mit XML-Elementen  
 Beim Programmieren mit XML liegt Ihr Hauptaugenmerk in der Regel auf XML-Elementen und vielleicht auch auf Attributen. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie direkt mit XML-Elementen und Attributen arbeiten. So können Sie z. B. Folgendes tun:  
  
-   Sie können XML-Elemente ohne jegliche Verwendung eines Dokumentobjekts erstellen. Dies vereinfacht beim Arbeiten mit Fragmenten von XML-Strukturen die Programmierung.  
  
-   Sie können `T:System.Xml.Linq.XElement`-Objekte direkt aus einer XML-Datei laden.  
  
-   Sie können `T:System.Xml.Linq.XElement`-Objekte in eine Datei oder einen Stream serialisieren.  
  
 Vergleichen Sie dies mit dem W3C-DOM, bei dem das XML-Dokument als logischer Container für die XML-Struktur verwendet wird. Im DOM müssen die XML-Knoten einschließlich der Elemente und Attribute im Kontext eines XML-Dokuments erstellt werden. Das folgende Codefragment erstellt ein Namenselement im DOM:  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlElement name = doc.CreateElement("Name");  
name.InnerText = "Patrick Hines";  
doc.AppendChild(name);  
```  
  
 Wenn Sie ein Element in mehreren Dokumenten verwenden möchten, müssen Sie die Knoten dokumentübergreifend importieren. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vermeidet diese Ebene der Komplexität.  
  
 Bei der Verwendung von LINQ to XML müssen Sie die Klasse <xref:System.Xml.Linq.XDocument> nur dann verwenden, wenn Sie der Stammebene des Dokuments einen Kommentar oder eine Verarbeitungsanweisung hinzufügen möchten.  
  
## <a name="simplified-handling-of-names-and-namespaces"></a>Vereinfachte Handhabung von Namen und Namespaces  
 Die Handhabung von Namen, Namespaces und Namespacepräfixen ist im Allgemeinen ein komplexer Teil der XML-Programmierung. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vereinfacht Namen und Namespaces, weil der Umgang mit Namespacepräfixen nicht zwingend erforderlich ist. Das heißt aber nicht, dass Sie die Namespacepräfixe nicht mehr selbst steuern können. Wenn Sie sich aber dafür entscheiden, sich nicht mehr explizit um die Steuerung der Namespacepräfixe kümmern zu wollen, weist [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bei der Serialisierung, wo erforderlich, entsprechende Namespacepräfixe zu oder greift für die Serialisierung auf die Standardnamespaces zurück. Wenn Standardnamespaces verwendet werden, gibt es im resultierenden Dokument keine Namespacepräfixe. Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Ein anderes Problem mit dem DOM besteht darin, dass es keine Änderung des Namens eines Knotens zulässt. Stattdessen müssen Sie einen neuen Knoten erstellen und alle untergeordneten Knoten kopieren, sodass die ursprüngliche Knotenidentität verloren geht. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vermeidet dieses Problem, indem es Ihnen die Möglichkeit gibt, für einen Knoten die Eigenschaft <xref:System.Xml.Linq.XName> festzulegen.  
  
## <a name="static-method-support-for-loading-xml"></a>Unterstützung statischer Methoden für das Laden von XML  
 In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie zum Laden von XML anstelle von Instanzmethoden statische Methoden verwenden. Dadurch vereinfacht sich das Laden und das Analysieren. Weitere Informationen finden Sie unter [Vorgehensweise: Laden von XML aus einer Datei](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md).  
  
## <a name="removal-of-support-for-dtd-constructs"></a>Entfernung der Unterstützung für DTD-Konstrukte  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vereinfacht die XML-Programmierung zusätzlich, indem die Unterstützung für Entitäten und Entitätsverweise entfernt wird. Die Verwaltung von Entitäten ist komplex und wird selten verwendet. Durch das Entfernen dieser Unterstützung wird die Leistung verbessert und die Programmierung vereinfacht. Beim Auffüllen einer [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Struktur werden alle DTD-Entitäten erweitert.  
  
## <a name="support-for-fragments"></a>Unterstützung für Fragmente  
 In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gibt es keine Entsprechung für die Klasse `XmlDocumentFragment`. In vielen Fällen kann jedoch das Konzept `XmlDocumentFragment` durch eine Abfrage behandelt werden, die als <xref:System.Collections.Generic.IEnumerable%601> des <xref:System.Xml.Linq.XNode> oder <xref:System.Collections.Generic.IEnumerable%601> des <xref:System.Xml.Linq.XElement> typisiert ist.  
  
## <a name="support-for-xpathnavigator"></a>Unterstützung für XPathNavigator  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet durch Erweiterungsmethoden im Namespace <xref:System.Xml.XPath?displayProperty=fullName> Unterstützung für <xref:System.Xml.XPath.XPathNavigator>. Weitere Informationen finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=fullName>.  
  
## <a name="support-for-white-space-and-indentation"></a>Unterstützung für Leerraum und Einzüge  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] handhabt Leerzeichen einfacher als das DOM.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] speichert Leerzeichen als <xref:System.Xml.Linq.XText>-Knoten, anstatt wie das DOM einen spezialisierten <xref:System.Xml.XmlNodeType>-Knoten zu haben.  
  
## <a name="support-for-annotations"></a>Unterstützung für Anmerkungen  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Elemente unterstützen einen erweiterbaren Satz von Anmerkungen. Dies ist hilfreich, wenn verschiedene Informationen zu einem Element nachverfolgt werden sollen, z.B. Schemainformationen, die Information, ob das Element an eine Benutzeroberfläche gebunden ist, oder andere anwendungsspezifische Informationen. Weitere Informationen finden Sie unter [Anmerkungen zu LINQ to XML](http://msdn.microsoft.com/library/e2f0052d-61e2-48d4-9ea4-356c9cab35d5).  
  
## <a name="support-for-schema-information"></a>Unterstützung für Schemainformationen  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] bietet durch Erweiterungsmethoden im Namespace <xref:System.Xml.Schema?displayProperty=fullName> Unterstützung für XSD-Überprüfung an. Sie können prüfen, ob sich eine XML-Struktur nach einer XSD richtet. Sie können die XML-Struktur mit dem Post-Schema-Validierungs-Infoset (PSVI) auffüllen. Weitere Informationen finden Sie unter [Vorgehensweise: Überprüfen mithilfe von XSD](http://msdn.microsoft.com/library/481a97fa-6e96-46f2-8c9a-415555fac33b) und <xref:System.Xml.Schema.Extensions>.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
