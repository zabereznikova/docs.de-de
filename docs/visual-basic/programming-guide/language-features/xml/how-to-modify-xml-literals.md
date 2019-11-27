---
title: 'Gewusst wie: Ändern von XML-Literalen'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 99ec35addcb9fc8d886c9151cde87227b5113eb9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330862"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a>Gewusst wie: Ändern von XML-Literalen (Visual Basic)

Visual Basic bietet bequeme Möglichkeiten zum Ändern von XML-Literalen. Sie können Elemente und Attribute hinzufügen oder löschen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen. Dieses Thema enthält mehrere Beispiele zum Ändern eines vorhandenen XML-Literals.

### <a name="to-modify-the-value-of-an-xml-literal"></a>So ändern Sie den Wert eines XML-Literals

1. Um den Wert eines XML-Literals zu ändern, rufen Sie einen Verweis auf das XML-wahrsten ab, und legen Sie die `Value`-Eigenschaft auf den gewünschten Wert fest

    Im folgenden Codebeispiel wird der Wert aller \<Price > Elemente in einem XML-Dokument aktualisiert.

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.

    Quell-XML:

    ```xml
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
    ```

    Geänderte XML-Daten:

    ```xml
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
    > Die `Value`-Eigenschaft verweist auf das erste XML-Element in einer Auflistung. Wenn mehr als ein Element mit demselben Namen in einer Auflistung vorhanden ist, wirkt sich das Festlegen der `Value` Eigenschaft nur auf das erste Element in der Auflistung aus.

### <a name="to-add-an-attribute-to-an-xml-literal"></a>So fügen Sie einem XML-Literalattribut ein Attribut hinzu

1. Zum Hinzufügen eines Attributs zu einem XML-Literalwert rufen Sie zuerst einen Verweis auf das XML-Literale ab Anschließend können Sie ein Attribut hinzufügen, indem Sie eine neue XML-Attribut Achsen Eigenschaft hinzufügen. Sie können dem XML-literalobjekt auch ein neues <xref:System.Xml.Linq.XAttribute> Objekt hinzufügen, indem Sie die <xref:System.Xml.Linq.XContainer.Add%2A>-Methode verwenden. Im folgenden Beispiel werden beide Optionen gezeigt.

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.

    Quell-XML:

    ```xml
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
    ```

    Geänderte XML-Daten:

    ```xml
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

    Weitere Informationen zu Eigenschaften von XML-Attribut Achsen finden Sie unter [XML-Attribut Achsen Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).

### <a name="to-add-an-element-to-an-xml-literal"></a>So fügen Sie einem XML-Literalelement ein Element hinzu

1. Um einem XML-Literalelement ein Element hinzuzufügen, müssen Sie zuerst einen Verweis auf das XML-Literalelement abrufen Sie können dann mit der <xref:System.Xml.Linq.XContainer.Add%2A>-Methode ein neues <xref:System.Xml.Linq.XElement>-Objekt als das letzte untergeordnete Element des-Elements hinzufügen. Mit der <xref:System.Xml.Linq.XContainer.AddFirst%2A>-Methode können Sie ein neues <xref:System.Xml.Linq.XElement> Objekt als erstes untergeordnetes Element hinzufügen.

    Wenn Sie ein neues Element an einer bestimmten Position relativ zu anderen untergeordneten Elementen hinzufügen möchten, rufen Sie zuerst einen Verweis auf ein benachbartes Unterelement ab. Anschließend können Sie das neue <xref:System.Xml.Linq.XElement> Objekt vor dem angrenzenden Unterelement hinzufügen, indem Sie die <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>-Methode verwenden. Sie können das neue <xref:System.Xml.Linq.XElement> Objekt auch nach dem angrenzenden Unterelement hinzufügen, indem Sie die <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>-Methode verwenden.

    Das folgende Beispiel zeigt Beispiele für jede dieser Techniken.

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.

    Quell-XML:

    ```xml
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
    ```

    Geänderte XML-Daten:

    ```xml
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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a>So entfernen Sie ein Element oder Attribut aus einem XML-Literalelement

1. Wenn Sie ein Element oder Attribut aus einem XML-Literalzeichen entfernen möchten, rufen Sie einen Verweis auf das Element oder Attribut ab, und rufen Sie die `Remove`-Methode auf, wie im folgenden Beispiel gezeigt.

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.

    Quell-XML:

    ```xml
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
    ```

    Geänderte XML-Daten:

    ```xml
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

    Wenn Sie alle Elemente oder Attribute aus einem XML-Literalzeichen entfernen möchten, rufen Sie einen Verweis auf das XML-wahrsten ab, und rufen Sie die <xref:System.Xml.Linq.XElement.RemoveAll%2A>

### <a name="to-modify-an-xml-literal"></a>So ändern Sie ein XML-wahrsten

1. Um den Namen eines XML-Elements zu ändern, rufen Sie zuerst einen Verweis auf das Element ab. Anschließend können Sie ein neues <xref:System.Xml.Linq.XElement> Objekt mit einem neuen Namen erstellen und das neue <xref:System.Xml.Linq.XElement>-Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A>-Methode des vorhandenen <xref:System.Xml.Linq.XElement>-Objekts übergeben.

    Wenn das Element, das Sie ersetzen, unter Elemente enthält, die beibehalten werden müssen, legen Sie den Wert des neuen <xref:System.Xml.Linq.XElement> Objekts auf die <xref:System.Xml.Linq.XContainer.Nodes%2A>-Eigenschaft des vorhandenen Elements fest. Dadurch wird der Wert des neuen Elements auf den inneren XML-Code des vorhandenen Elements festgelegt. Andernfalls können Sie den Wert des neuen Elements auf die `Value`-Eigenschaft des vorhandenen Elements festlegen.

    Im folgenden Codebeispiel werden alle \<Beschreibungs > Elemente durch ein \<abstraktes > Element ersetzt. Der Inhalt der \<Beschreibungs > Elements wird im neuen \<abstrakten > Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A>-Eigenschaft der \<Description > <xref:System.Xml.Linq.XElement>-Objekts beibehalten.

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.

    Quell-XML:

    ```xml
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
    ```

    Geänderte XML-Daten:

    ```xml
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
- [Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
