---
title: Speichern und Ausgeben eines Dokuments
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
ms.openlocfilehash: 0cb83935b4175060a04f4be48e6b4eee2f44ed7d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823497"
---
# <a name="saving-and-writing-a-document"></a>Speichern und Ausgeben eines Dokuments
Ein geladenes und dann gespeichertes <xref:System.Xml.XmlDocument> kann in den folgenden Punkten vom Original abweichen:  
  
- Wenn die <xref:System.Xml.XmlDocument.PreserveWhitespace%2A>-Eigenschaft vor dem Aufruf der `true`-Methode auf <xref:System.Xml.XmlDocument.Save%2A> festgelegt wurde, bleibt im Dokument enthaltener Leerraum in der Ausgabe erhalten. Wenn diese Eigenschaft `false` ist, wird die Ausgabe automatisch von <xref:System.Xml.XmlDocument> eingerückt.  
  
- Der gesamte Leerraum zwischen Attributen wird zu einem einzigen Leerzeichen zusammengefasst.  
  
- Leerraum zwischen Elementen wird verändert. Signifikanter Leerraum bleibt im Gegensatz zu nicht signifikantem Leerraum erhalten. Beim Speichern des Dokuments wird allerdings standardmäßig der besseren Lesbarkeit wegen der **Indenting**-Modus von <xref:System.Xml.XmlTextWriter> verwendet.  
  
- Einfache Anführungszeichen für Attributwerte werden standardmäßig in doppelte Anführungszeichen umgewandelt. Das Anführungszeichen kann mit der <xref:System.Xml.XmlTextReader.QuoteChar%2A>-Eigenschaft des <xref:System.Xml.XmlTextWriter> als einfaches oder doppeltes Anführungszeichen festgelegt werden.  
  
- Numerische Zeichenentitäten wie `{` werden standardmäßig erweitert.  
  
- Die Bytereihenfolgenmarkierung im Ausgangsdokument bleibt nicht erhalten. UCS-2 wird als UTF-8 gespeichert, wenn keine XML-Deklaration erstellt wird, die eine andere Codierung angibt.  
  
- Wenn das <xref:System.Xml.XmlDocument> als Datei oder als Stream ausgegeben wird, entspricht die Ausgabe dem Inhalt des Dokuments. Eine <xref:System.Xml.XmlDeclaration> wird also nur dann ausgegeben, wenn eine solche im Dokument vorhanden ist, und die für die Ausgabe verwendete Codierung entspricht der im Deklarationsknoten angegebenen Codierung.  
  
## <a name="writing-an-xmldeclaration"></a>Schreiben einer "XmlDeclaration"  
 Außer der <xref:System.Xml.XmlDocument>-Methode und der <xref:System.Xml.XmlDeclaration>-Methode von <xref:System.Xml.XmlNode.OuterXml%2A> erstellen die Methoden <xref:System.Xml.XmlNode.InnerXml%2A>, <xref:System.Xml.XmlNode.WriteTo%2A> und <xref:System.Xml.XmlDocument> von <xref:System.Xml.XmlDocument.Save%2A> und <xref:System.Xml.XmlDocument.WriteContentTo%2A> eine XML-Deklaration.  
  
 Bei der <xref:System.Xml.XmlDocument>-Eigenschaft und der <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft von <xref:System.Xml.XmlDocument.InnerXml%2A> und den Methoden <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A> und <xref:System.Xml.XmlDocument.WriteContentTo%2A> wird die in der XML-Deklaration ausgegebene Codierung dem <xref:System.Xml.XmlDeclaration>-Knoten entnommen. Wenn kein <xref:System.Xml.XmlDeclaration>-Knoten vorhanden ist, wird keine <xref:System.Xml.XmlDeclaration> ausgegeben. Wenn der <xref:System.Xml.XmlDeclaration>-Knoten keine Codierung enthält, wird in der XML-Deklaration keine Codierung ausgegeben.  
  
 Die <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType>-Methode und die <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType>-Methode schreiben immer eine <xref:System.Xml.XmlDeclaration>. Diese Methoden übernehmen die Codierung des Writers, in den sie schreiben. Der Codierungswert des Writers überschreibt also die Codierung im Dokument und in der <xref:System.Xml.XmlDeclaration>. Bei dem folgenden Codebeispiel wird z. B. keine Codierung innerhalb der XML-Deklaration in die Ausgabedatei `out.xml` geschrieben.  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 Bei der <xref:System.Xml.XmlDocument.Save%2A>-Methode wird die XML-Deklaration mit der <xref:System.Xml.XmlWriter.WriteStartDocument%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse geschrieben. Ein Überschreiben der <xref:System.Xml.XmlWriter.WriteStartDocument%2A>-Methode ändert daher die Ausgabe des Dokumentanfangs.  
  
 Bei den Membern <xref:System.Xml.XmlDeclaration>, <xref:System.Xml.XmlNode.OuterXml%2A> und <xref:System.Xml.XmlDeclaration.WriteTo%2A> von <xref:System.Xml.XmlNode.InnerXml%2A> wird keine Codierung geschrieben, wenn die <xref:System.Xml.XmlDeclaration.Encoding%2A>-Eigenschaft nicht festgelegt ist. Andernfalls entspricht die in der XML-Deklaration ausgegebenen Codierung der in der <xref:System.Xml.XmlDeclaration.Encoding%2A>-Eigenschaft angegebenen Codierung.  
  
## <a name="writing-document-content-using-the-outerxml-property"></a>Schreiben des Dokumentinhalts mit der "OuterXml"-Eigenschaft  
 Die <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft ist eine Erweiterung von Microsoft des XML-DOM-Standards (Document Object Model) des W3C (Word Wide Web Consortium). Die <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft wird zum Abrufen des Markups des ganzen XML-Dokuments oder eines Knotens und seiner untergeordneten Knoten verwendet. <xref:System.Xml.XmlNode.OuterXml%2A> gibt das Markup zurück, das diesen Knoten und alle ihm untergeordneten Knoten darstellt.  
  
 Im folgenden Codebeispiel wird ein Dokument vollständig als Zeichenfolge gespeichert.  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 Im folgenden Codebeispiel wird nur das Dokument-Element gespeichert.  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 Sie können dagegen die <xref:System.Xml.XmlNode.InnerText%2A>-Eigenschaft zum Speichern des Inhalts der untergeordneten Knoten verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
