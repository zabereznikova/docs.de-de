---
title: 'Vorgehensweise: Ändern von XML-Literalen'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: a2ac2e9802d4c8ab522bb430d15cce5616430437
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374874"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="e24f8-102">Gewusst wie: Ändern von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e24f8-102">How to: Modify XML Literals (Visual Basic)</span></span>

<span data-ttu-id="e24f8-103">Visual Basic bietet bequeme Möglichkeiten zum Ändern von XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="e24f8-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="e24f8-104">Sie können Elemente und Attribute hinzufügen oder löschen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen.</span><span class="sxs-lookup"><span data-stu-id="e24f8-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="e24f8-105">Dieses Thema enthält mehrere Beispiele zum Ändern eines vorhandenen XML-Literals.</span><span class="sxs-lookup"><span data-stu-id="e24f8-105">This topic provides several examples of how to modify an existing XML literal.</span></span>

### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="e24f8-106">So ändern Sie den Wert eines XML-Literals</span><span class="sxs-lookup"><span data-stu-id="e24f8-106">To modify the value of an XML literal</span></span>

1. <span data-ttu-id="e24f8-107">Um den Wert eines XML-Literals zu ändern, rufen Sie einen Verweis auf das XML-wahrsten ab, und legen `Value` Sie die Eigenschaft auf den gewünschten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="e24f8-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>

    <span data-ttu-id="e24f8-108">Im folgenden Codebeispiel wird der Wert aller- \<Price> Elemente in einem XML-Dokument aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="e24f8-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>

    [!code-vb[VbXmlSamples2#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#4)]

    <span data-ttu-id="e24f8-109">Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="e24f8-109">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e24f8-110">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="e24f8-110">Source XML:</span></span>

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

    <span data-ttu-id="e24f8-111">Geänderte XML-Daten:</span><span class="sxs-lookup"><span data-stu-id="e24f8-111">Modified XML:</span></span>

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
    > <span data-ttu-id="e24f8-112">Die- `Value` Eigenschaft verweist auf das erste XML-Element in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e24f8-112">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="e24f8-113">Wenn mehr als ein Element mit demselben Namen in einer Auflistung vorhanden ist, wirkt sich das Festlegen der `Value` Eigenschaft nur auf das erste Element in der Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="e24f8-113">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>

### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="e24f8-114">So fügen Sie einem XML-Literalattribut ein Attribut hinzu</span><span class="sxs-lookup"><span data-stu-id="e24f8-114">To add an attribute to an XML literal</span></span>

1. <span data-ttu-id="e24f8-115">Zum Hinzufügen eines Attributs zu einem XML-Literalwert rufen Sie zuerst einen Verweis auf das XML-Literale ab</span><span class="sxs-lookup"><span data-stu-id="e24f8-115">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="e24f8-116">Anschließend können Sie ein Attribut hinzufügen, indem Sie eine neue XML-Attribut Achsen Eigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e24f8-116">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="e24f8-117">Sie können auch mit der-Methode ein neues- <xref:System.Xml.Linq.XAttribute> Objekt zum XML-Literaltyp hinzufügen <xref:System.Xml.Linq.XContainer.Add%2A> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-117">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="e24f8-118">Im folgenden Beispiel werden beide Optionen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e24f8-118">The following example shows both options.</span></span>

    [!code-vb[VbXmlSamples2#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#5)]

    <span data-ttu-id="e24f8-119">Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="e24f8-119">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e24f8-120">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="e24f8-120">Source XML:</span></span>

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

    <span data-ttu-id="e24f8-121">Geänderte XML-Daten:</span><span class="sxs-lookup"><span data-stu-id="e24f8-121">Modified XML:</span></span>

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

    <span data-ttu-id="e24f8-122">Weitere Informationen zu Eigenschaften von XML-Attribut Achsen finden Sie unter [XML-Attribut Achsen Eigenschaft](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="e24f8-122">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>

### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="e24f8-123">So fügen Sie einem XML-Literalelement ein Element hinzu</span><span class="sxs-lookup"><span data-stu-id="e24f8-123">To add an element to an XML literal</span></span>

1. <span data-ttu-id="e24f8-124">Um einem XML-Literalelement ein Element hinzuzufügen, müssen Sie zuerst einen Verweis auf das XML-Literalelement abrufen</span><span class="sxs-lookup"><span data-stu-id="e24f8-124">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="e24f8-125">Anschließend können Sie mithilfe der-Methode ein neues- <xref:System.Xml.Linq.XElement> Objekt als letztes Unterelement des-Elements hinzufügen <xref:System.Xml.Linq.XContainer.Add%2A> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-125">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="e24f8-126">Mithilfe der-Methode können Sie ein neues- <xref:System.Xml.Linq.XElement> Objekt als erstes untergeordnetes Element hinzufügen <xref:System.Xml.Linq.XContainer.AddFirst%2A> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-126">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>

    <span data-ttu-id="e24f8-127">Wenn Sie ein neues Element an einer bestimmten Position relativ zu anderen untergeordneten Elementen hinzufügen möchten, rufen Sie zuerst einen Verweis auf ein benachbartes Unterelement ab.</span><span class="sxs-lookup"><span data-stu-id="e24f8-127">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="e24f8-128">Anschließend können Sie das neue- <xref:System.Xml.Linq.XElement> Objekt vor dem angrenzenden Unterelement mithilfe der-Methode hinzufügen <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-128">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="e24f8-129">Sie können das neue- <xref:System.Xml.Linq.XElement> Objekt auch nach dem angrenzenden Unterelement mithilfe der-Methode hinzufügen <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-129">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>

    <span data-ttu-id="e24f8-130">Das folgende Beispiel zeigt Beispiele für jede dieser Techniken.</span><span class="sxs-lookup"><span data-stu-id="e24f8-130">The following example shows examples of each of these techniques.</span></span>

    [!code-vb[VbXmlSamples2#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#6)]

    <span data-ttu-id="e24f8-131">Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="e24f8-131">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e24f8-132">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="e24f8-132">Source XML:</span></span>

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

    <span data-ttu-id="e24f8-133">Geänderte XML-Daten:</span><span class="sxs-lookup"><span data-stu-id="e24f8-133">Modified XML:</span></span>

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

### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="e24f8-134">So entfernen Sie ein Element oder Attribut aus einem XML-Literalelement</span><span class="sxs-lookup"><span data-stu-id="e24f8-134">To remove an element or attribute from an XML literal</span></span>

1. <span data-ttu-id="e24f8-135">Wenn Sie ein Element oder Attribut aus einem XML-Literalzeichen entfernen möchten, rufen Sie einen Verweis auf das Element oder Attribut ab, und rufen Sie die- `Remove` Methode auf, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e24f8-135">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>

    [!code-vb[VbXmlSamples2#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#7)]

    <span data-ttu-id="e24f8-136">Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="e24f8-136">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e24f8-137">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="e24f8-137">Source XML:</span></span>

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

    <span data-ttu-id="e24f8-138">Geänderte XML-Daten:</span><span class="sxs-lookup"><span data-stu-id="e24f8-138">Modified XML:</span></span>

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

    <span data-ttu-id="e24f8-139">Wenn Sie alle Elemente oder Attribute aus einem XML-Literalzeichen entfernen möchten, rufen Sie einen Verweis auf das XML-wahrsten ab, und rufen <xref:System.Xml.Linq.XElement.RemoveAll%2A> Sie die</span><span class="sxs-lookup"><span data-stu-id="e24f8-139">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>

### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="e24f8-140">So ändern Sie ein XML-wahrsten</span><span class="sxs-lookup"><span data-stu-id="e24f8-140">To modify an XML literal</span></span>

1. <span data-ttu-id="e24f8-141">Um den Namen eines XML-Elements zu ändern, rufen Sie zuerst einen Verweis auf das Element ab.</span><span class="sxs-lookup"><span data-stu-id="e24f8-141">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="e24f8-142">Sie können dann ein neues <xref:System.Xml.Linq.XElement> -Objekt mit einem neuen Namen erstellen und das neue- <xref:System.Xml.Linq.XElement> Objekt an die- <xref:System.Xml.Linq.XNode.ReplaceWith%2A> Methode des vorhandenen- <xref:System.Xml.Linq.XElement> Objekts übergeben.</span><span class="sxs-lookup"><span data-stu-id="e24f8-142">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>

    <span data-ttu-id="e24f8-143">Wenn das Element, das Sie ersetzen, unter Elemente enthält, die beibehalten werden müssen, legen Sie den Wert des neuen- <xref:System.Xml.Linq.XElement> Objekts auf die- <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft des vorhandenen Elements fest.</span><span class="sxs-lookup"><span data-stu-id="e24f8-143">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="e24f8-144">Dadurch wird der Wert des neuen Elements auf den inneren XML-Code des vorhandenen Elements festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e24f8-144">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="e24f8-145">Andernfalls können Sie den Wert des neuen Elements auf die- `Value` Eigenschaft des vorhandenen-Elements festlegen.</span><span class="sxs-lookup"><span data-stu-id="e24f8-145">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>

    <span data-ttu-id="e24f8-146">Im folgenden Codebeispiel werden alle- \<Description> Elemente durch ein- \<Abstract> Element ersetzt.</span><span class="sxs-lookup"><span data-stu-id="e24f8-146">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="e24f8-147">Der Inhalt des- \<Description> Elements wird im neuen- \<Abstract> Element mithilfe der- <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft des-Objekts beibehalten \<Description> <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="e24f8-147">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>

    [!code-vb[VbXmlSamples2#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXmlSamples2/VB/Module2.vb#8)]

    <span data-ttu-id="e24f8-148">Das folgende Beispiel zeigt die XML-Beispieldatei und den geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="e24f8-148">The following shows sample source XML and modified XML from this code example.</span></span>

    <span data-ttu-id="e24f8-149">Quell-XML:</span><span class="sxs-lookup"><span data-stu-id="e24f8-149">Source XML:</span></span>

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

    <span data-ttu-id="e24f8-150">Geänderte XML-Daten:</span><span class="sxs-lookup"><span data-stu-id="e24f8-150">Modified XML:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e24f8-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e24f8-151">See also</span></span>

- [<span data-ttu-id="e24f8-152">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e24f8-152">Manipulating XML in Visual Basic</span></span>](manipulating-xml.md)
- [<span data-ttu-id="e24f8-153">XML</span><span class="sxs-lookup"><span data-stu-id="e24f8-153">XML</span></span>](index.md)
- [<span data-ttu-id="e24f8-154">Vorgehensweise: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="e24f8-154">How to: Load XML from a File, String, or Stream</span></span>](how-to-load-xml-from-a-file-string-or-stream.md)
- [<span data-ttu-id="e24f8-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="e24f8-155">LINQ</span></span>](../linq/index.md)
- [<span data-ttu-id="e24f8-156">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e24f8-156">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
