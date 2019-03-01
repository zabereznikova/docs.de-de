---
title: 'Vorgehensweise: Ändern von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 6e11c1ed4cfe4edc1c88dbbff2e9f555b1a028c4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974717"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Vorgehensweise: Ändern von XML-Literalen (Visual Basic)
Visual Basic bietet praktische Optionen zum Ändern von XML-Literale. Sie können das Hinzufügen oder Löschen von Elementen und Attributen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen. Dieses Thema enthält einige Beispiele für ein vorhandenes XML-literal zu ändern.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>Zum Ändern des Werts von einem XML-literal  
  
1.  Um den Wert eines XML-Literals zu ändern, erhalten Sie einen Verweis auf das XML-literal und legen die `Value` Eigenschaft auf den gewünschten Wert.  
  
     Im folgenden Codebeispiel wird aktualisiert den Wert aller der \<Preis >-Elemente in einem XML-Dokument.  
  
     [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]  
  
     Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.  
  
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
    >  Die `Value` Eigenschaft bezieht sich auf die erste XML-Element in einer Auflistung. Wenn mehr als ein Element mit dem gleichen Namen in einer Auflistung vorhanden ist, Festlegen der `Value` Eigenschaft wirkt sich nur das erste Element in der Auflistung.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>Ein Attribut hinzufügen, um ein XML-literal  
  
1.  Um ein XML-literal ein Attribut hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal. Sie können ein Attribut klicken Sie dann durch Hinzufügen einer neuen XML-Attributachseneigenschaft hinzufügen. Sie können auch einen neuen hinzufügen <xref:System.Xml.Linq.XAttribute> Objekt, das das XML-literal mit dem <xref:System.Xml.Linq.XContainer.Add%2A> Methode. Im folgende Beispiel werden beide Optionen veranschaulicht.  
  
     [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]  
  
     Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.  
  
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
  
     Weitere Informationen zu XML-Attribut-Achseneigenschaften, finden Sie unter [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>Ein Element ein XML-Literal hinzu  
  
1.  Um ein XML-literal ein Element hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal. Anschließend können Sie ein neues hinzufügen <xref:System.Xml.Linq.XElement> -Objekt als das letzte untergeordnete Element des Elements mit dem <xref:System.Xml.Linq.XContainer.Add%2A> Methode. Sie können ein neues hinzufügen <xref:System.Xml.Linq.XElement> -Objekt als das erste untergeordnete Element mit dem <xref:System.Xml.Linq.XContainer.AddFirst%2A> Methode.  
  
     Um ein neues Element in einem bestimmten Speicherort relativ zu anderen untergeordneten Elementen hinzuzufügen, rufen Sie zunächst einen Verweis auf eine benachbarte untergeordnete Element. Anschließend können Sie die neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt vor dem benachbarte untergeordnete Element mit dem <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> Methode. Sie können auch das neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt nach dem benachbarte untergeordnete Element mit dem <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> Methode.  
  
     Das folgende Beispiel zeigt Beispiele für die einzelnen Verfahren.  
  
     [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]  
  
     Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>So entfernen Sie ein Element oder Attribut aus einem XML-literal  
  
1.  Um ein Element oder Attribut eines XML-Literals zu entfernen, erhalten Sie einen Verweis auf das Element oder Attribut, und rufen die `Remove` Methode, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]  
  
     Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.  
  
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
      </Book></Catalog>  
    ```  
  
     Um alle Elemente oder Attribute aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf die XML-literal, und rufen Sie die <xref:System.Xml.Linq.XElement.RemoveAll%2A> Methode.  
  
### <a name="to-modify-an-xml-literal"></a>So ändern Sie ein XML-literal  
  
1.  Rufen Sie zuerst einen Verweis auf das Element, um den Namen eines XML-Elements zu ändern. Anschließend können Sie ein neues erstellen <xref:System.Xml.Linq.XElement> -Objekt, das hat den neuen Namen, und übergeben Sie das neue <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A> Methode des vorhandenen <xref:System.Xml.Linq.XElement> Objekt.  
  
     Wenn das Element, das Sie ersetzen möchten untergeordnete Elemente, die beibehalten werden sollen verfügt, legen Sie den Wert der neuen <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XContainer.Nodes%2A> -Eigenschaft des vorhandenen Elements. Dadurch wird den Wert des neuen Elements auf den inneren XML-Code des vorhandenen Elements festgelegt. Andernfalls können Sie den Wert des neuen Elements, das Festlegen der `Value` -Eigenschaft des vorhandenen Elements.  
  
     Im folgenden Codebeispiel wird ersetzt alle \<Beschreibung >-Elemente mit einem \<abstrakte > Element. Der Inhalt des der \<Beschreibung > Elements beibehalten wird, in der neuen \<abstrakte >-Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft der \<Beschreibung > <xref:System.Xml.Linq.XElement> Objekt.  
  
     [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]  
  
     Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.  
  
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
        <MSRP>44.95</MSRP>    <Abstract>  
          An in-depth look at creating applications  
          with <technology>XML</technology>. For   
          <audience>beginners</audience> or   
          <audience>advanced</audience> developers.  
        </Abstract>  
      </Book>  
      <Book id="bk331">  
        <Author>Spencer, Phil</Author>  
        <Title>Developing Applications with Visual Basic .NET</Title>  
        <MSRP>45.95</MSRP>    <Abstract>  
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
  
## <a name="see-also"></a>Siehe auch
- [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
