---
title: Übersicht über die XDocument-Klasse (C#)
description: Die XDocument-Klasse in C# enthält die Informationen, die für ein gültiges XML-Dokument erforderlich sind, einschließlich einer XML-Deklaration, Verarbeitungsanweisungen und Kommentaren.
ms.date: 07/20/2015
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
ms.openlocfilehash: 6d522cef25e99e4a5ea54e644855c8dfa7a05f4a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302190"
---
# <a name="xdocument-class-overview-c"></a>Übersicht über die XDocument-Klasse (C#)
Dieses Thema enthält eine Einführung in die <xref:System.Xml.Linq.XDocument>-Klasse.  
  
## <a name="overview-of-the-xdocument-class"></a>Allgemeines  
 Die <xref:System.Xml.Linq.XDocument>-Klasse enthält die für ein gültiges XML-Dokument erforderlichen Informationen. Dazu gehören eine XML-Deklaration, Verarbeitungsanweisungen und Kommentare.  
  
 Beachten Sie, dass Sie <xref:System.Xml.Linq.XDocument>-Objekte nur erstellen müssen, wenn Sie die spezifische Funktionalität benötigen, die von der <xref:System.Xml.Linq.XDocument>-Klasse bereitgestellt wird. In vielen Fällen können Sie direkt mit <xref:System.Xml.Linq.XElement> arbeiten. Das direkte Arbeiten mit <xref:System.Xml.Linq.XElement> ist ein einfacheres Programmiermodell.  
  
 <xref:System.Xml.Linq.XDocument> wird von <xref:System.Xml.Linq.XContainer> abgeleitet. Deshalb kann es untergeordnete Knoten enthalten. <xref:System.Xml.Linq.XDocument>-Objekte können aber nur einen untergeordneten <xref:System.Xml.Linq.XElement>-Knoten besitzen. Dies spiegelt den XML-Standard wider, demzufolge in einem XML-Dokument nur ein Stammelement vorhanden sein darf.  
  
## <a name="components-of-xdocument"></a>Komponenten von "XDocument"  
 Ein <xref:System.Xml.Linq.XDocument> kann die folgenden Elemente enthalten:  
  
- genau ein <xref:System.Xml.Linq.XDeclaration>-Objekt: Mit <xref:System.Xml.Linq.XDeclaration> können Sie die wichtigen Teile einer XML-Deklaration angeben: die XML-Version, die Codierung des Dokuments und die Angabe, ob das XML-Dokument eigenständig ist.  
  
- genau ein <xref:System.Xml.Linq.XElement>-Objekt: Dies ist der Stammknoten des XML-Dokuments.  
  
- eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>-Objekten: Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.  
  
- eine beliebige Anzahl von <xref:System.Xml.Linq.XComment>-Objekten: Die Kommentare sind dem Stammelement nebengeordnet. Das <xref:System.Xml.Linq.XComment>-Objekt kann nicht das erste Argument in der Liste sein, da ein XML-Dokument nicht mit einem Kommentar beginnen darf.  
  
- genau ein <xref:System.Xml.Linq.XDocumentType> für die DTD  
  
 Beim Serialisieren eines <xref:System.Xml.Linq.XDocument>-Objekts enthält die Ausgabe eine XML-Deklaration. Dies gilt auch dann, wenn `XDocument.Declaration` auf `null` gesetzt ist, solange der Writer für `Writer.Settings.OmitXmlDeclaration` den Standardwert `false` festgelegt hat.  
  
 Standardmäßig legt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Version auf "1.0" und die Codierung auf "utf-8" fest.  
  
## <a name="using-xelement-without-xdocument"></a>Verwenden von "XElement" ohne "XDocument"  
 Wie bereits erwähnt, ist die <xref:System.Xml.Linq.XElement>-Klasse die Hauptklasse in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Programmierschnittstelle. In vielen Fällen wird es für Ihre Anwendung nicht notwendig sein, ein Dokument zu erstellen. Dank der <xref:System.Xml.Linq.XElement>-Klasse können Sie eine XML-Struktur erstellen, dieser Struktur andere XML-Strukturen hinzufügen, die XML-Struktur ändern und die XML-Struktur speichern.  
  
## <a name="using-xdocument"></a>Verwenden von "XDocument"  
 Zum Konstruieren eines <xref:System.Xml.Linq.XDocument> können Sie genauso die funktionale Konstruktion verwenden wie zum Konstruieren von <xref:System.Xml.Linq.XElement>-Objekten.  
  
 Der folgende Code erstellt ein <xref:System.Xml.Linq.XDocument>-Objekt und die zugehörigen in ihm enthaltenen Objekte.  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 Wenn Sie sich die Datei <legacyBold>test.xml</legacyBold> ansehen, erhalten Sie die folgende Ausgabe:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))](./linq-to-xml-overview.md)
