---
title: 'Vorgehensweise: Ändern von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 003715b04f3a5c0fb41e846beb189f117378ea58
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675328"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="44e17-102">Vorgehensweise: Ändern von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44e17-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="44e17-103">Visual Basic bietet praktische Optionen zum Ändern von XML-Literale.</span><span class="sxs-lookup"><span data-stu-id="44e17-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="44e17-104">Sie können das Hinzufügen oder Löschen von Elementen und Attributen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen.</span><span class="sxs-lookup"><span data-stu-id="44e17-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="44e17-105">Dieses Thema enthält einige Beispiele für ein vorhandenes XML-literal zu ändern.</span><span class="sxs-lookup"><span data-stu-id="44e17-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="44e17-106">Zum Ändern des Werts von einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="44e17-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="44e17-107">Um den Wert eines XML-Literals zu ändern, erhalten Sie einen Verweis auf das XML-literal und legen die `Value` Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="44e17-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="44e17-108">Im folgenden Codebeispiel wird aktualisiert den Wert aller der \<Preis >-Elemente in einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="44e17-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="44e17-109">Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.</span><span class="sxs-lookup"><span data-stu-id="44e17-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="44e17-110">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="44e17-110">Source XML:</span></span>

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

    <span data-ttu-id="44e17-111">Geänderte XML-Code:</span><span class="sxs-lookup"><span data-stu-id="44e17-111">Modified XML:</span></span>

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
    > <span data-ttu-id="44e17-112">Die `Value` Eigenschaft bezieht sich auf die erste XML-Element in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="44e17-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="44e17-113">Wenn mehr als ein Element mit dem gleichen Namen in einer Auflistung vorhanden ist, Festlegen der `Value` Eigenschaft wirkt sich nur das erste Element in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="44e17-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="44e17-114">Ein Attribut hinzufügen, um ein XML-literal</span><span class="sxs-lookup"><span data-stu-id="44e17-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="44e17-115">Um ein XML-literal ein Attribut hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="44e17-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="44e17-116">Sie können ein Attribut klicken Sie dann durch Hinzufügen einer neuen XML-Attributachseneigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="44e17-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="44e17-117">Sie können auch einen neuen hinzufügen <xref:System.Xml.Linq.XAttribute> Objekt, das das XML-literal mit dem <xref:System.Xml.Linq.XContainer.Add%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="44e17-118">Im folgende Beispiel werden beide Optionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="44e17-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="44e17-119">Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.</span><span class="sxs-lookup"><span data-stu-id="44e17-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="44e17-120">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="44e17-120">Source XML:</span></span>

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

    <span data-ttu-id="44e17-121">Geänderte XML-Code:</span><span class="sxs-lookup"><span data-stu-id="44e17-121">Modified XML:</span></span>

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

    <span data-ttu-id="44e17-122">Weitere Informationen zu XML-Attribut-Achseneigenschaften, finden Sie unter [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="44e17-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="44e17-123">Ein Element ein XML-Literal hinzu</span><span class="sxs-lookup"><span data-stu-id="44e17-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="44e17-124">Um ein XML-literal ein Element hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="44e17-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="44e17-125">Anschließend können Sie ein neues hinzufügen <xref:System.Xml.Linq.XElement> -Objekt als das letzte untergeordnete Element des Elements mit dem <xref:System.Xml.Linq.XContainer.Add%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="44e17-126">Sie können ein neues hinzufügen <xref:System.Xml.Linq.XElement> -Objekt als das erste untergeordnete Element mit dem <xref:System.Xml.Linq.XContainer.AddFirst%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="44e17-127">Um ein neues Element in einem bestimmten Speicherort relativ zu anderen untergeordneten Elementen hinzuzufügen, rufen Sie zunächst einen Verweis auf eine benachbarte untergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="44e17-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="44e17-128">Anschließend können Sie die neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt vor dem benachbarte untergeordnete Element mit dem <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="44e17-129">Sie können auch das neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt nach dem benachbarte untergeordnete Element mit dem <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="44e17-130">Das folgende Beispiel zeigt Beispiele für die einzelnen Verfahren.</span><span class="sxs-lookup"><span data-stu-id="44e17-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="44e17-131">Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.</span><span class="sxs-lookup"><span data-stu-id="44e17-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="44e17-132">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="44e17-132">Source XML:</span></span>

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

    <span data-ttu-id="44e17-133">Geänderte XML-Code:</span><span class="sxs-lookup"><span data-stu-id="44e17-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="44e17-134">So entfernen Sie ein Element oder Attribut aus einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="44e17-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="44e17-135">Um ein Element oder Attribut eines XML-Literals zu entfernen, erhalten Sie einen Verweis auf das Element oder Attribut, und rufen die `Remove` Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="44e17-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="44e17-136">Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.</span><span class="sxs-lookup"><span data-stu-id="44e17-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="44e17-137">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="44e17-137">Source XML:</span></span>

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

    <span data-ttu-id="44e17-138">Geänderte XML-Code:</span><span class="sxs-lookup"><span data-stu-id="44e17-138">Modified XML:</span></span>

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

    <span data-ttu-id="44e17-139">Um alle Elemente oder Attribute aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf die XML-literal, und rufen Sie die <xref:System.Xml.Linq.XElement.RemoveAll%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="44e17-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="44e17-140">So ändern Sie ein XML-literal</span><span class="sxs-lookup"><span data-stu-id="44e17-140">To modify an XML literal</span></span>

1. <span data-ttu-id="44e17-141">Rufen Sie zuerst einen Verweis auf das Element, um den Namen eines XML-Elements zu ändern.</span><span class="sxs-lookup"><span data-stu-id="44e17-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="44e17-142">Anschließend können Sie ein neues erstellen <xref:System.Xml.Linq.XElement> -Objekt, das hat den neuen Namen, und übergeben Sie das neue <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A> Methode des vorhandenen <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="44e17-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="44e17-143">Wenn das Element, das Sie ersetzen möchten untergeordnete Elemente, die beibehalten werden sollen verfügt, legen Sie den Wert der neuen <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XContainer.Nodes%2A> -Eigenschaft des vorhandenen Elements.</span><span class="sxs-lookup"><span data-stu-id="44e17-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="44e17-144">Dadurch wird den Wert des neuen Elements auf den inneren XML-Code des vorhandenen Elements festgelegt.</span><span class="sxs-lookup"><span data-stu-id="44e17-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="44e17-145">Andernfalls können Sie den Wert des neuen Elements, das Festlegen der `Value` -Eigenschaft des vorhandenen Elements.</span><span class="sxs-lookup"><span data-stu-id="44e17-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="44e17-146">Im folgenden Codebeispiel wird ersetzt alle \<Beschreibung >-Elemente mit einem \<abstrakte > Element.</span><span class="sxs-lookup"><span data-stu-id="44e17-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="44e17-147">Der Inhalt des der \<Beschreibung > Elements beibehalten wird, in der neuen \<abstrakte >-Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft der \<Beschreibung > <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="44e17-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="44e17-148">Die folgende zeigt Beispiel Quell-XML und XML in diesem Codebeispiel wird geändert.</span><span class="sxs-lookup"><span data-stu-id="44e17-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="44e17-149">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="44e17-149">Source XML:</span></span>

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

    <span data-ttu-id="44e17-150">Geänderte XML-Code:</span><span class="sxs-lookup"><span data-stu-id="44e17-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="44e17-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44e17-151">See also</span></span>

- [<span data-ttu-id="44e17-152">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44e17-152">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
- [<span data-ttu-id="44e17-153">XML</span><span class="sxs-lookup"><span data-stu-id="44e17-153">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="44e17-154">Vorgehensweise: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream</span><span class="sxs-lookup"><span data-stu-id="44e17-154">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="44e17-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="44e17-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="44e17-156">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="44e17-156">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
