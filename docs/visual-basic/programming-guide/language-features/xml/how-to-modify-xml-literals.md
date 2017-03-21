---
title: "Gewusst wie: Ändern von XML-Literalen (Visual Basic) | Microsoft-Dokumentation"
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
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0ff2eba693862154d9c402748fb6797d10c4a1f8
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Gewusst wie: Ändern von XML-Literalen (Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]stellt einfache Methoden zum Ändern von XML-Literalen. Sie können das Hinzufügen oder Löschen von Elementen und Attributen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen. Dieses Thema enthält mehrere Beispiele für das Ändern eines vorhandenen XML-Literals.  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a>So ändern Sie den Wert des XML-literal  
  
1.  Ändern Sie den Wert eines XML-Literals, erhalten Sie einen Verweis auf das XML-literal aufrufen und die `Value` Eigenschaft auf den gewünschten Wert.  
  
     Im folgenden Codebeispiel wird den Wert aller updates den \<Preis > Elemente in einem XML-Dokument.  
  
     [!code-vb[VbXmlSamples2&4;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.  
  
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
    >  Die `Value` Eigenschaft bezieht sich auf das erste XML-Element in einer Auflistung. Wenn mehr als ein Element mit dem gleichen Namen in einer Auflistung vorhanden ist, wird durch Festlegen der `Value` Eigenschaft wirkt sich nur auf das erste Element in der Auflistung.  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a>Ein XML-Literal ein Attribut hinzufügen  
  
1.  Um ein XML-literal ein Attribut hinzuzufügen, erhalten Sie zunächst einen Verweis auf das XML-literal. Sie können ein Attribut dann durch Hinzufügen einer neuen XML-Attributachseneigenschaft hinzufügen. Sie können auch einen neuen hinzufügen <xref:System.Xml.Linq.XAttribute>-Objekt, das XML-literal mithilfe der <xref:System.Xml.Linq.XContainer.Add%2A>-Methode.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute> Im folgende Beispiel werden beide Optionen veranschaulicht.  
  
     [!code-vb[VbXmlSamples2&5;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.  
  
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
  
     Weitere Informationen zu XML-Attribut Achseneigenschaft, finden Sie unter [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).  
  
### <a name="to-add-an-element-to-an-xml-literal"></a>Hinzufügen eines Elements zu einem XML-literal  
  
1.  Um ein XML-literal ein Element hinzuzufügen, rufen Sie zuerst einen Verweis auf das XML-literal. Anschließend können Sie einen neuen hinzufügen <xref:System.Xml.Linq.XElement>Objekt als das letzte untergeordnete Element des Elements mithilfe der <xref:System.Xml.Linq.XContainer.Add%2A>-Methode.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement> Sie können einen neuen hinzufügen <xref:System.Xml.Linq.XElement>Objekt als das erste untergeordnete Element mit der <xref:System.Xml.Linq.XContainer.AddFirst%2A>-Methode.</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement>  
  
     Um ein neues Element in einem bestimmten Speicherort relativ zu anderen untergeordneten Elementen hinzuzufügen, müssen Sie zunächst erwerben Sie einen Verweis auf einen benachbarten Unterelement. Sie können dann die neue hinzufügen <xref:System.Xml.Linq.XElement>Objekt vor dem benachbarten Unterelement mithilfe der <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>-Methode.</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement> Sie können auch das neue hinzufügen <xref:System.Xml.Linq.XElement>Objekts nach dem benachbarten Unterelement mithilfe der <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>-Methode.</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement>  
  
     Das folgende Beispiel zeigt Beispiele für jede dieser Techniken.  
  
     [!code-vb[VbXmlSamples2&6;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.  
  
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
  
1.  Um ein Element oder Attribut aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das Element oder Attribut, und rufen die `Remove` Methode, wie im folgenden Beispiel gezeigt.  
  
     [!code-vb[VbXmlSamples&#2;7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.  
  
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
  
     Um alle Elemente oder Attribute aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das XML-literal und der <xref:System.Xml.Linq.XElement.RemoveAll%2A>-Methode.</xref:System.Xml.Linq.XElement.RemoveAll%2A>  
  
### <a name="to-modify-an-xml-literal"></a>So ändern Sie ein XML-literal  
  
1.  Um den Namen eines XML-Elements zu ändern, rufen Sie zuerst einen Verweis auf das Element. Anschließend können Sie eine neue erstellen <xref:System.Xml.Linq.XElement>-Objekt, das einem neuen Namen, und übergeben Sie das neue <xref:System.Xml.Linq.XElement>-Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A>Methode des vorhandenen <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
     Wenn das Element, das Sie ersetzen untergeordnete Elemente, die beibehalten werden müssen verfügt, legen Sie den Wert der neuen <xref:System.Xml.Linq.XElement>-Objekt an die <xref:System.Xml.Linq.XContainer.Nodes%2A>-Eigenschaft des vorhandenen Elements.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement> Dadurch wird den Wert des neuen Elements auf den inneren XML-Codes des vorhandenen Elements festgelegt. Andernfalls können Sie den Wert des neuen Elements, das Festlegen der `Value` -Eigenschaft des vorhandenen Elements.  
  
     Im folgenden Codebeispiel werden alle ersetzt \<Beschreibung > Elemente mit einer \<abstrakte > Element. Der Inhalt des der \<Beschreibung > Element wird in der neuen beibehalten \<abstrakte > Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A>Eigenschaft der \<Beschreibung > <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A>  
  
     [!code-vb[VbXmlSamples&#2;8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.  
  
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
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
