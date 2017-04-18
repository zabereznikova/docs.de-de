---
title: "Übersicht über die XDocument-Klasse (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 31111b23adb019aad3ad55787c073dc02446291d
ms.lasthandoff: 03/13/2017

---
# <a name="xdocument-class-overview-visual-basic"></a>Übersicht über die XDocument-Klasse (Visual Basic)
In diesem Abschnitt wird die <xref:System.Xml.Linq.XDocument>Klasse.</xref:System.Xml.Linq.XDocument>  
  
## <a name="overview-of-the-xdocument-class"></a>Allgemeines  
 Die <xref:System.Xml.Linq.XDocument>-Klasse enthält die notwendigen Informationen für ein gültiges XML-Dokument.</xref:System.Xml.Linq.XDocument> Dazu gehören eine XML-Deklaration, Verarbeitungsanweisungen und Kommentare.  
  
 Beachten Sie, dass Sie nur erstellen, <xref:System.Xml.Linq.XDocument>Objekte, wenn Sie die spezifische Funktionalität benötigen von der <xref:System.Xml.Linq.XDocument>-Klasse</xref:System.Xml.Linq.XDocument> bereitgestellt müssen</xref:System.Xml.Linq.XDocument> In vielen Fällen können Sie arbeiten direkt mit <xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement> Direktes Arbeiten mit <xref:System.Xml.Linq.XElement>ist ein einfacheres Programmiermodell.</xref:System.Xml.Linq.XElement>  
  
 <xref:System.Xml.Linq.XDocument><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> abgeleitet ist.</xref:System.Xml.Linq.XDocument> Deshalb kann es untergeordnete Knoten enthalten. Allerdings <xref:System.Xml.Linq.XDocument>können nur ein untergeordnetes Element besitzen <xref:System.Xml.Linq.XElement>Knoten.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> Dies spiegelt den XML-Standard wider, demzufolge in einem XML-Dokument nur ein Stammelement vorhanden sein darf.  
  
## <a name="components-of-xdocument"></a>Komponenten von "XDocument"  
 Ein <xref:System.Xml.Linq.XDocument>kann die folgenden Elemente enthalten:</xref:System.Xml.Linq.XDocument>  
  
-   Ein <xref:System.Xml.Linq.XDeclaration>Objekt.</xref:System.Xml.Linq.XDeclaration> <xref:System.Xml.Linq.XDeclaration>ermöglicht es Ihnen, die wichtigen Teile einer XML-Deklaration angeben: die XML-Version, die Codierung des Dokuments, und gibt an, ob das XML-Dokument eigenständig ist.</xref:System.Xml.Linq.XDeclaration>  
  
-   Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> Dies ist der Stammknoten des XML-Dokuments.  
  
-   Eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>Objekte.</xref:System.Xml.Linq.XProcessingInstruction> Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.  
  
-   Eine beliebige Anzahl von <xref:System.Xml.Linq.XComment>Objekte.</xref:System.Xml.Linq.XComment> Die Kommentare sind dem Stammelement nebengeordnet. Das <xref:System.Xml.Linq.XComment>Objekt darf nicht das erste Argument in der Liste sein, da nicht für ein XML-Dokument mit einem Kommentar beginnen darf.</xref:System.Xml.Linq.XComment>  
  
-   Eine <xref:System.Xml.Linq.XDocumentType>für die DTD.</xref:System.Xml.Linq.XDocumentType>  
  
 Beim Serialisieren einer <xref:System.Xml.Linq.XDocument>, selbst wenn `XDocument.Declaration` ist `null`, haben die Ausgabe eine XML-Deklaration, wenn der Writer `Writer.Settings.OmitXmlDeclaration` festgelegt `false` (Standard).</xref:System.Xml.Linq.XDocument>  
  
 Standardmäßig legt [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Version auf "1.0" und die Codierung auf "utf-8" fest.  
  
## <a name="using-xelement-without-xdocument"></a>Verwenden von "XElement" ohne "XDocument"  
 Wie bereits erwähnt, die <xref:System.Xml.Linq.XElement>-Klasse ist die Hauptklasse in der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Programmierschnittstelle.</xref:System.Xml.Linq.XElement> In vielen Fällen wird es für Ihre Anwendung nicht notwendig sein, ein Dokument zu erstellen. Mithilfe der <xref:System.Xml.Linq.XElement>-Klasse, Sie können eine XML-Struktur andere XML-Strukturen hinzufügen, ändern und die XML-Struktur und it. speichern</xref:System.Xml.Linq.XElement>  
  
## <a name="using-xdocument"></a>Verwenden von "XDocument"  
 Erstellt eine <xref:System.Xml.Linq.XDocument>, die funktionale Konstruktion wie zum Konstruieren verwenden <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument>  
  
 Der folgende Code erstellt ein <xref:System.Xml.Linq.XDocument>-Objekt und die zugehörigen enthaltenen Objekte.</xref:System.Xml.Linq.XDocument>  
  
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
 [LINQ to XML-Programmierung (Übersicht) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
