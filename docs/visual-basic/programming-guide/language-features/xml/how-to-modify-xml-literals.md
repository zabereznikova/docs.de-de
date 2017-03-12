---
title: "How to: Modify XML Literals (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML axis [Visual Basic], Value"
  - "XML literals [Visual Basic]"
  - "XML literals [Visual Basic], modifying"
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# How to: Modify XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] bietet bequeme Möglichkeiten zum Ändern von XML\-Literalen.  Sie können Elemente und Attribute hinzufügen oder entfernen und bestehende Elemente durch neue XML\-Elemente ersetzen.  Dieses Thema enthält mehrere Beispiele für das Ändern eines vorhandenen XML\-Literals.  
  
### So ändern Sie den Wert eines XML\-Literals  
  
1.  Sie ändern den Wert eines XML\-Literals, indem Sie einen Verweis auf das XML\-Literal aufrufen und die `Value`\-Eigenschaft auf den gewünschten Wert festlegen.  
  
     Im folgenden Codebeispiel wird der Wert aller \<Price\>\-Elemente in einem XML\-Dokument aktualisiert.  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#4)]  
  
     Im Folgenden werden Beispiele für ursprünglichen und geänderten XML\-Code aus diesem Codebeispiel dargestellt.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>47.20</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>48.25</Price>  
      </Book>  
    </Catalog>  
    ```  
  
    > [!NOTE]
    >  Die `Value`\-Eigenschaft verweist auf das erste XML\-Element in einer Auflistung.  Wenn es innerhalb einer Auflistung mehrere Elemente mit dem gleichen Namen gibt, ist nur das erste Element in der Auflistung von der Festlegung der `Value`\-Eigenschaft betroffen.  
  
### So fügen Sie einem XML\-Literal ein Attribut hinzu  
  
1.  Um einem XML\-Literal ein Attribut hinzuzufügen, rufen Sie zunächst einen Verweis auf dieses XML\-Literal ab.  Sie können dann durch Hinzufügen einer neuen XML\-Attributachseneigenschaft ein Attribut hinzufügen.  Sie können dem XML\-Literal auch ein neues <xref:System.Xml.Linq.XAttribute>\-Objekt hinzufügen, indem Sie die <xref:System.Xml.Linq.XContainer.Add%2A>\-Methode verwenden.  Im folgenden Beispiel werden beide Optionen veranschaulicht.  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#5)]  
  
     Im Folgenden werden Beispiele für ursprünglichen und geänderten XML\-Code aus diesem Codebeispiel dargestellt.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
    ```  
  
     Weitere Informationen über XML\-Attributachseneigenschaften finden Sie unter [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### So fügen Sie einem XML\-Literal ein Element hinzu  
  
1.  Um einem XML\-Literal ein Element hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML\-Literal ab.  Sie können dann ein neues <xref:System.Xml.Linq.XElement>\-Objekt als letztes Unterelement des Elements anfügen, indem Sie die <xref:System.Xml.Linq.XContainer.Add%2A>\-Methode verwenden.  Sie können ein neues <xref:System.Xml.Linq.XElement>\-Objekt als erstes Unterelement hinzufügen, indem Sie die <xref:System.Xml.Linq.XContainer.AddFirst%2A>\-Methode verwenden.  
  
     Rufen Sie zunächst einen Verweis auf ein benachbartes Unterelement ab, um ein neues Element an einem bestimmten Speicherort relativ zu anderen Unterelementen hinzuzufügen.  Das neue <xref:System.Xml.Linq.XElement>\-Objekt kann dann mit der <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>\-Methode vor dem benachbarten Unterelement hinzugefügt werden.  Das neue <xref:System.Xml.Linq.XElement>\-Objekt kann auch hinter dem benachbarten Unterelement hinzugefügt werden, wenn die <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>\-Methode verwendet wird.  
  
     Im folgenden Beispiel werden beide Verfahren veranschaulicht.  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#6)]  
  
     Im Folgenden werden Beispiele für ursprünglichen und geänderten XML\-Code aus diesem Codebeispiel dargestellt.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" >  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331">  
        <Publisher>Microsoft Press</Publisher>  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <PublishDate>2005-2-14</PublishDate>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
    ```  
  
### So entfernen Sie ein Element oder ein Attribut aus einem XML\-Literal  
  
1.  Um ein Element oder ein Attribut aus einem XML\-Literal zu entfernen, rufen Sie einen Verweis auf das Element oder das Attribut ab, und rufen Sie die `Remove`\-Methode auf, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#7)]  
  
     Im Folgenden werden Beispiele für ursprünglichen und geänderten XML\-Code aus diesem Codebeispiel dargestellt.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" genre="Computer" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" genre="Computer" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book>  
      <Book id="bk999"></Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101" editorEmail="someone@example.com">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
      </Book>  
      <Book id="bk000"></Book>  
      <Book id="bk331" editorEmail="someone@example.com">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
      </Book> </Catalog>  
    ```  
  
     Um alle Elemente oder Attribute aus einem XML\-Literal zu entfernen, rufen Sie einen Verweis auf das XML\-Literal ab und die <xref:System.Xml.Linq.XElement.RemoveAll%2A>\-Methode auf.  
  
### So ändern Sie ein XML\-Literal  
  
1.  Um den Namen eines XML\-Elements zu ändern, rufen Sie zunächst einen Verweis auf das Element ab.  Sie können dann eine neues <xref:System.Xml.Linq.XElement>\-Objekt mit einem neuen Namen erstellen und das neue <xref:System.Xml.Linq.XElement>\-Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A>\-Methode des bestehenden <xref:System.Xml.Linq.XElement>\-Objekts übergeben.  
  
     Wenn das zu ersetzende Element Unterelemente hat, die beibehalten werden müssen, legen Sie den Wert des neuen <xref:System.Xml.Linq.XElement>\-Objekts auf die <xref:System.Xml.Linq.XContainer.Nodes%2A>\-Eigenschaft des bestehende Elements fest.  Dadurch wird der Wert des neuen Elements auf den inneren XML\-Code des bestehenden Elements festgelegt.  Andernfalls können Sie den Wert des neuen Elements auf die `Value`\-Eigenschaft des vorhandenen Elements festlegen.  
  
     Im folgenden Codebeispiel werden alle \<Description\>\-Elemente durch ein \<Abstract\>\-Element ersetzt.  Der Inhalt des \<Description\>\-Elements wird im neuen \<Abstract\>\-Element beibehalten, wenn die <xref:System.Xml.Linq.XContainer.Nodes%2A>\-Eigenschaft des \<Description\>\-<xref:System.Xml.Linq.XElement>\-Objekts verwendet wird.  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/visualbasic/VbXmlSamples2/Module2.vb#8)]  
  
     Im Folgenden werden Beispiele für ursprünglichen und geänderten XML\-Code aus diesem Codebeispiel dargestellt.  
  
    ```  
    Source XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <Price>44.95</Price>  
        <Description>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Description>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <Price>45.95</Price>  
        <Description>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Description>  
      </Book>  
    </Catalog>  
  
    Modified XML:  
    <?xml version="1.0"?>  
    <Catalog>  
      <Book id="bk101">  
        <Author>Garghentini, Davide</Author>  
        <Title>XML Developer's Guide</Title>  
        <MSRP>44.95</MSRP>     <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>     <Abstract>  
          Get the expert insights, practical code samples, and best  
          practices you need to advance your expertise with   
          <technology>Visual Basic .NET</technology>.   
          Learn how to create faster, more reliable applications  
          based on professional, pragmatic guidance by today's top  
          <audience>developers</audience>.  
        </Abstract>  
      </Book>  
    </Catalog>  
    ```  
  
## Siehe auch  
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)