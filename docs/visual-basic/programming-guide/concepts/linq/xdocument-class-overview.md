---
title: Übersicht über die XDocument-Klasse
ms.date: 07/20/2015
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
ms.openlocfilehash: cbc1ccca53978da07f31c0ba7e54eca9f06b0e72
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349288"
---
# <a name="xdocument-class-overview-visual-basic"></a>XDocument Class Overview (Visual Basic)
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
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
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

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
