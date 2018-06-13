---
title: 'Gewusst wie: Ändern von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], Value
- XML literals [Visual Basic]
- XML literals [Visual Basic], modifying
ms.assetid: 4e864522-a37a-43a2-8236-af80277c5482
ms.openlocfilehash: 17da86d6d10fb1602c16fc2a8c4d6f9f8acf8ff7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656044"
---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="bf968-102">Gewusst wie: Ändern von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf968-102">How to: Modify XML Literals (Visual Basic)</span></span>
<span data-ttu-id="bf968-103">Visual Basic bietet bequeme Möglichkeiten zum Ändern von XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="bf968-103">Visual Basic provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="bf968-104">Sie können das Hinzufügen oder Löschen von Elementen und Attributen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen.</span><span class="sxs-lookup"><span data-stu-id="bf968-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="bf968-105">Dieses Thema enthält mehrere Beispiele für die Vorgehensweise beim Ändern einer vorhandenen XML-literal.</span><span class="sxs-lookup"><span data-stu-id="bf968-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="bf968-106">Zum Ändern des Werts eines XML-Literals</span><span class="sxs-lookup"><span data-stu-id="bf968-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="bf968-107">Um den Wert eines XML-Literals zu ändern, erhalten Sie einen Verweis auf die XML-Literale und legen die `Value` Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="bf968-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="bf968-108">Im folgenden Codebeispiel wird der Wert aller aktualisiert die \<Price >-Elemente in einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="bf968-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     [!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]  
  
     <span data-ttu-id="bf968-109">Der folgende Code zeigt XML-Beispielquelle und geänderten XML-Code aus diesem Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="bf968-109">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
    >  <span data-ttu-id="bf968-110">Die `Value` Eigenschaft bezieht sich auf das erste XML-Element in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="bf968-110">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="bf968-111">Wenn mehr als ein Element mit dem gleichen Namen in einer Auflistung vorhanden ist, wird durch Festlegen der `Value` Eigenschaft wirkt sich nur das erste Element in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="bf968-111">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="bf968-112">Ein XML-Literal ein Attribut hinzufügen</span><span class="sxs-lookup"><span data-stu-id="bf968-112">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="bf968-113">Um ein XML-literal ein Attribut hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="bf968-113">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="bf968-114">Sie können ein Attribut klicken Sie dann durch Hinzufügen einer neuen XML-Attributachseneigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bf968-114">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="bf968-115">Sie können auch einen neuen hinzufügen <xref:System.Xml.Linq.XAttribute> -Objekt, das XML-literal mit dem <xref:System.Xml.Linq.XContainer.Add%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-115">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="bf968-116">Im folgende Beispiel werden beide Optionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bf968-116">The following example shows both options.</span></span>  
  
     [!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]  
  
     <span data-ttu-id="bf968-117">Der folgende Code zeigt XML-Beispielquelle und geänderten XML-Code aus diesem Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="bf968-117">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="bf968-118">Weitere Informationen zu XML-Achse Attributeigenschaften finden Sie unter [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="bf968-118">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="bf968-119">Hinzufügen eines Elements zu einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="bf968-119">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="bf968-120">Um ein XML-literal ein Element hinzuzufügen, rufen Sie zunächst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="bf968-120">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="bf968-121">Anschließend können Sie ein neues hinzufügen <xref:System.Xml.Linq.XElement> Objekt als das letzte untergeordnete Element des Elements mithilfe der <xref:System.Xml.Linq.XContainer.Add%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-121">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="bf968-122">Sie können ein neues hinzufügen <xref:System.Xml.Linq.XElement> Objekt als das erste untergeordnete Element mithilfe der <xref:System.Xml.Linq.XContainer.AddFirst%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-122">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="bf968-123">Um ein neues Element in einem bestimmten Speicherort relativ zu anderen untergeordneten Elementen hinzuzufügen, rufen Sie zunächst einen Verweis auf ein benachbarte untergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="bf968-123">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="bf968-124">Sie können dann die neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt vor dem benachbarten untergeordneten Element mithilfe der <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-124">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="bf968-125">Sie können auch das neue hinzufügen <xref:System.Xml.Linq.XElement> Objekt nach dem benachbarten untergeordneten Element mithilfe der <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-125">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="bf968-126">Das folgende Beispiel zeigt Beispiele für jeden dieser Techniken.</span><span class="sxs-lookup"><span data-stu-id="bf968-126">The following example shows examples of each of these techniques.</span></span>  
  
     [!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]  
  
     <span data-ttu-id="bf968-127">Der folgende Code zeigt XML-Beispielquelle und geänderten XML-Code aus diesem Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="bf968-127">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="bf968-128">So entfernen Sie ein Element oder Attribut aus einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="bf968-128">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="bf968-129">Um ein Element oder Attribut aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das Element oder Attribut, und rufen die `Remove` Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf968-129">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     [!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]  
  
     <span data-ttu-id="bf968-130">Der folgende Code zeigt XML-Beispielquelle und geänderten XML-Code aus diesem Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="bf968-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="bf968-131">Um alle Elemente oder Attribute aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das XML-literal und die <xref:System.Xml.Linq.XElement.RemoveAll%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="bf968-131">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="bf968-132">So ändern Sie ein XML-literal</span><span class="sxs-lookup"><span data-stu-id="bf968-132">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="bf968-133">Um den Namen eines XML-Elements zu ändern, rufen Sie zunächst einen Verweis auf das Element.</span><span class="sxs-lookup"><span data-stu-id="bf968-133">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="bf968-134">Sie können dann ein neues erstellen <xref:System.Xml.Linq.XElement> -Objekt, das hat den neuen Namen ein, und übergeben Sie das neue <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A> Methode des vorhandenen <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bf968-134">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="bf968-135">Wenn das Element, das Sie ersetzen untergeordnete Elemente, die beibehalten werden sollen verfügt, legen Sie den Wert der neuen <xref:System.Xml.Linq.XElement> -Objekt an die <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft des vorhandenen Elements.</span><span class="sxs-lookup"><span data-stu-id="bf968-135">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="bf968-136">Dies legt den Wert des neuen Elements in der inneren XML des vorhandenen Elements fest.</span><span class="sxs-lookup"><span data-stu-id="bf968-136">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="bf968-137">Andernfalls können Sie legen Sie den Wert des neuen Elements, das die `Value` Eigenschaft des vorhandenen Elements.</span><span class="sxs-lookup"><span data-stu-id="bf968-137">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="bf968-138">Im folgenden Codebeispiel wird ersetzt alle \<Beschreibung >-Elemente mit einer \<abstrakte > Element.</span><span class="sxs-lookup"><span data-stu-id="bf968-138">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="bf968-139">Den Inhalt der \<Beschreibung > Element wird in der neuen beibehalten \<abstrakte >-Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A> Eigenschaft der \<Beschreibung > <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bf968-139">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     [!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]  
  
     <span data-ttu-id="bf968-140">Der folgende Code zeigt XML-Beispielquelle und geänderten XML-Code aus diesem Codebeispiel wird.</span><span class="sxs-lookup"><span data-stu-id="bf968-140">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bf968-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf968-141">See Also</span></span>  
 [<span data-ttu-id="bf968-142">Bearbeiten von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf968-142">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 [<span data-ttu-id="bf968-143">XML</span><span class="sxs-lookup"><span data-stu-id="bf968-143">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="bf968-144">Gewusst wie: Laden von XML aus einer Datei, einer Zeichenfolge oder einem Stream</span><span class="sxs-lookup"><span data-stu-id="bf968-144">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 [<span data-ttu-id="bf968-145">LINQ</span><span class="sxs-lookup"><span data-stu-id="bf968-145">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="bf968-146">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf968-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
