---
title: "Übersicht über die XDocument-Klasse (C#) | Microsoft-Dokumentation"
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
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
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
ms.openlocfilehash: f3233a634e358ee227b0adbe30cb05d1efbf8fe0
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-c"></a>Übersicht über die XDocument-Klasse (C#)
In diesem Thema wird die Klasse <xref:System.Xml.Linq.XDocument> eingeführt.  
  
## <a name="overview-of-the-xdocument-class"></a>Allgemeines  
 Die Klasse <xref:System.Xml.Linq.XDocument> enthält die für ein gültiges XML-Dokument erforderlichen Informationen. Dazu gehören eine XML-Deklaration, Verarbeitungsanweisungen und Kommentare.  
  
 Beachten Sie, dass Sie <xref:System.Xml.Linq.XDocument>-Objekte erstellen müssen, wenn Sie die spezifischen Funktionen der <xref:System.Xml.Linq.XDocument>-Klasse benötigen. In vielen Fällen können Sie direkt mit <xref:System.Xml.Linq.XElement> arbeiten. Das direkte Arbeiten mit <xref:System.Xml.Linq.XElement> ist ein einfacheres Programmiermodell.  
  
 <xref:System.Xml.Linq.XDocument> wird von <xref:System.Xml.Linq.XContainer> abgeleitet. Deshalb kann es untergeordnete Knoten enthalten. Allerdings können <xref:System.Xml.Linq.XDocument>-Objekte nur über einen untergeordneten <xref:System.Xml.Linq.XElement>-Knoten verfügen. Dies spiegelt den XML-Standard wider, demzufolge in einem XML-Dokument nur ein Stammelement vorhanden sein darf.  
  
## <a name="components-of-xdocument"></a>Komponenten von "XDocument"  
 <xref:System.Xml.Linq.XDocument> kann die folgenden Elemente enthalten:  
  
-   Ein <xref:System.Xml.Linq.XDeclaration>-Objekt. Mit <xref:System.Xml.Linq.XDeclaration> können Sie die wichtigen Teile einer XML-Deklaration angeben: die XML-Version, die Codierung des Dokuments und die Angabe, ob das XML-Dokument eigenständig ist.  
  
-   Ein <xref:System.Xml.Linq.XElement>-Objekt. Dies ist der Stammknoten des XML-Dokuments.  
  
-   Eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>-Objekten Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.  
  
-   Eine beliebige Anzahl von <xref:System.Xml.Linq.XComment>-Objekten. Die Kommentare sind dem Stammelement nebengeordnet. Das <xref:System.Xml.Linq.XComment>-Objekt kann nicht das erste Argument in der Liste sein, da ein XML-Dokument nicht mit einem Kommentar beginnen darf.  
  
-   Ein <xref:System.Xml.Linq.XDocumentType für die DTD  
  
 Beim Serialisieren von <xref:System.Xml.Linq.XDocumentType> enthält die Ausgabe eine XML-Deklaration. Dies gilt auch dann, wenn `XDocument.Declaration` auf `null` gesetzt ist, solange der Writer für `Writer.Settings.OmitXmlDeclaration` den Standardwert `false` festgelegt hat.  
  
 Standardmäßig legt [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Version auf "1.0" und die Codierung auf "utf-8" fest.  
  
## <a name="using-xelement-without-xdocument"></a>Verwenden von "XElement" ohne "XDocument"  
 Wie bereits erwähnt, ist die <xref:System.Xml.Linq.XElement>-Klasse die Hauptklasse in der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Programmierschnittstelle. In vielen Fällen wird es für Ihre Anwendung nicht notwendig sein, ein Dokument zu erstellen. Dank der <xref:System.Xml.Linq.XElement>-Klasse können Sie eine XML-Struktur erstellen, dieser Struktur andere XML-Strukturen hinzufügen, die XML-Struktur ändern und die XML-Struktur speichern.  
  
## <a name="using-xdocument"></a>Verwenden von "XDocument"  
 Verwenden Sie beim Konstruieren von <xref:System.Xml.Linq.XDocument>-Objekten die funktionale Konstruktion wie beim Konstruieren von <xref:System.Xml.Linq.XElement>.  
  
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
 [Working with XML Namespaces (C#) (Übersicht der LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
