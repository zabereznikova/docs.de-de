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
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c21ded9fdd8f49b469b9a712be304c0d4cabb8c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-xml-literals-visual-basic"></a><span data-ttu-id="a291a-102">Gewusst wie: Ändern von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a291a-102">How to: Modify XML Literals (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="a291a-103">stellt einfache Methoden zum Ändern von XML-Literalen.</span><span class="sxs-lookup"><span data-stu-id="a291a-103"> provides convenient ways to modify XML literals.</span></span> <span data-ttu-id="a291a-104">Sie können das Hinzufügen oder Löschen von Elementen und Attributen, und Sie können auch ein vorhandenes Element durch ein neues XML-Element ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a291a-104">You can add or delete elements and attributes, and you can also replace an existing element with a new XML element.</span></span> <span data-ttu-id="a291a-105">Dieses Thema enthält mehrere Beispiele für das Ändern eines vorhandenen XML-Literals.</span><span class="sxs-lookup"><span data-stu-id="a291a-105">This topic provides several examples of how to modify an existing XML literal.</span></span>  
  
### <a name="to-modify-the-value-of-an-xml-literal"></a><span data-ttu-id="a291a-106">So ändern Sie den Wert des XML-literal</span><span class="sxs-lookup"><span data-stu-id="a291a-106">To modify the value of an XML literal</span></span>  
  
1.  <span data-ttu-id="a291a-107">Ändern Sie den Wert eines XML-Literals, erhalten Sie einen Verweis auf das XML-literal aufrufen und die `Value` Eigenschaft auf den gewünschten Wert.</span><span class="sxs-lookup"><span data-stu-id="a291a-107">To modify the value of an XML literal, obtain a reference to the XML literal and set the `Value` property to the desired value.</span></span>  
  
     <span data-ttu-id="a291a-108">Im folgenden Codebeispiel wird den Wert aller updates den \<Preis > Elemente in einem XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="a291a-108">The following code example updates the value of all the \<Price> elements in an XML document.</span></span>  
  
     <span data-ttu-id="a291a-109">[!code-vb[VbXmlSamples2&4;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a291a-109">[!code-vb[VbXmlSamples2#4](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="a291a-110">Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="a291a-110">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
    >  <span data-ttu-id="a291a-111">Die `Value` Eigenschaft bezieht sich auf das erste XML-Element in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a291a-111">The `Value` property refers to the first XML element in a collection.</span></span> <span data-ttu-id="a291a-112">Wenn mehr als ein Element mit dem gleichen Namen in einer Auflistung vorhanden ist, wird durch Festlegen der `Value` Eigenschaft wirkt sich nur auf das erste Element in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="a291a-112">If there is more than one element that has the same name in a collection, setting the `Value` property affects only the first element in the collection.</span></span>  
  
### <a name="to-add-an-attribute-to-an-xml-literal"></a><span data-ttu-id="a291a-113">Ein XML-Literal ein Attribut hinzufügen</span><span class="sxs-lookup"><span data-stu-id="a291a-113">To add an attribute to an XML literal</span></span>  
  
1.  <span data-ttu-id="a291a-114">Um ein XML-literal ein Attribut hinzuzufügen, erhalten Sie zunächst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="a291a-114">To add an attribute to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="a291a-115">Sie können ein Attribut dann durch Hinzufügen einer neuen XML-Attributachseneigenschaft hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a291a-115">You can then add an attribute by adding a new XML attribute axis property.</span></span> <span data-ttu-id="a291a-116">Sie können auch einen neuen hinzufügen <xref:System.Xml.Linq.XAttribute>-Objekt, das XML-literal mithilfe der <xref:System.Xml.Linq.XContainer.Add%2A>-Methode.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="a291a-116">You can also add a new <xref:System.Xml.Linq.XAttribute> object to the XML literal by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="a291a-117">Im folgende Beispiel werden beide Optionen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a291a-117">The following example shows both options.</span></span>  
  
     <span data-ttu-id="a291a-118">[!code-vb[VbXmlSamples2&5;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a291a-118">[!code-vb[VbXmlSamples2#5](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="a291a-119">Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="a291a-119">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="a291a-120">Weitere Informationen zu XML-Attribut Achseneigenschaft, finden Sie unter [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span><span class="sxs-lookup"><span data-stu-id="a291a-120">For more information about XML attribute axis properties, see [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md).</span></span>  
  
### <a name="to-add-an-element-to-an-xml-literal"></a><span data-ttu-id="a291a-121">Hinzufügen eines Elements zu einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="a291a-121">To add an element to an XML literal</span></span>  
  
1.  <span data-ttu-id="a291a-122">Um ein XML-literal ein Element hinzuzufügen, rufen Sie zuerst einen Verweis auf das XML-literal.</span><span class="sxs-lookup"><span data-stu-id="a291a-122">To add an element to an XML literal, first obtain a reference to the XML literal.</span></span> <span data-ttu-id="a291a-123">Anschließend können Sie einen neuen hinzufügen <xref:System.Xml.Linq.XElement>Objekt als das letzte untergeordnete Element des Elements mithilfe der <xref:System.Xml.Linq.XContainer.Add%2A>-Methode.</xref:System.Xml.Linq.XContainer.Add%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-123">You can then add a new <xref:System.Xml.Linq.XElement> object as the last sub-element of the element by using the <xref:System.Xml.Linq.XContainer.Add%2A> method.</span></span> <span data-ttu-id="a291a-124">Sie können einen neuen hinzufügen <xref:System.Xml.Linq.XElement>Objekt als das erste untergeordnete Element mit der <xref:System.Xml.Linq.XContainer.AddFirst%2A>-Methode.</xref:System.Xml.Linq.XContainer.AddFirst%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-124">You can add a new <xref:System.Xml.Linq.XElement> object as the first sub-element by using the <xref:System.Xml.Linq.XContainer.AddFirst%2A> method.</span></span>  
  
     <span data-ttu-id="a291a-125">Um ein neues Element in einem bestimmten Speicherort relativ zu anderen untergeordneten Elementen hinzuzufügen, müssen Sie zunächst erwerben Sie einen Verweis auf einen benachbarten Unterelement.</span><span class="sxs-lookup"><span data-stu-id="a291a-125">To add a new element in a specific location relative to other sub-elements, first obtain a reference to an adjacent sub-element.</span></span> <span data-ttu-id="a291a-126">Sie können dann die neue hinzufügen <xref:System.Xml.Linq.XElement>Objekt vor dem benachbarten Unterelement mithilfe der <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>-Methode.</xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-126">You can then add the new <xref:System.Xml.Linq.XElement> object before the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddBeforeSelf%2A> method.</span></span> <span data-ttu-id="a291a-127">Sie können auch das neue hinzufügen <xref:System.Xml.Linq.XElement>Objekts nach dem benachbarten Unterelement mithilfe der <xref:System.Xml.Linq.XNode.AddAfterSelf%2A>-Methode.</xref:System.Xml.Linq.XNode.AddAfterSelf%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-127">You can also add the new <xref:System.Xml.Linq.XElement> object after the adjacent sub-element by using the <xref:System.Xml.Linq.XNode.AddAfterSelf%2A> method.</span></span>  
  
     <span data-ttu-id="a291a-128">Das folgende Beispiel zeigt Beispiele für jede dieser Techniken.</span><span class="sxs-lookup"><span data-stu-id="a291a-128">The following example shows examples of each of these techniques.</span></span>  
  
     <span data-ttu-id="a291a-129">[!code-vb[VbXmlSamples2&6;](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a291a-129">[!code-vb[VbXmlSamples2#6](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="a291a-130">Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="a291a-130">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
### <a name="to-remove-an-element-or-attribute-from-an-xml-literal"></a><span data-ttu-id="a291a-131">So entfernen Sie ein Element oder Attribut aus einem XML-literal</span><span class="sxs-lookup"><span data-stu-id="a291a-131">To remove an element or attribute from an XML literal</span></span>  
  
1.  <span data-ttu-id="a291a-132">Um ein Element oder Attribut aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das Element oder Attribut, und rufen die `Remove` Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a291a-132">To remove an element or an attribute from an XML literal, obtain a reference to the element or attribute and call the `Remove` method, as shown in the following example.</span></span>  
  
     <span data-ttu-id="a291a-133">[!code-vb[VbXmlSamples&#2;7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a291a-133">[!code-vb[VbXmlSamples2#7](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_4.vb)]</span></span>  
  
     <span data-ttu-id="a291a-134">Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="a291a-134">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
     <span data-ttu-id="a291a-135">Um alle Elemente oder Attribute aus einem XML-Literal zu entfernen, rufen Sie einen Verweis auf das XML-literal und der <xref:System.Xml.Linq.XElement.RemoveAll%2A>-Methode.</xref:System.Xml.Linq.XElement.RemoveAll%2A></span><span class="sxs-lookup"><span data-stu-id="a291a-135">To remove all elements or attributes from an XML literal, obtain a reference to the XML literal and call the <xref:System.Xml.Linq.XElement.RemoveAll%2A> method.</span></span>  
  
### <a name="to-modify-an-xml-literal"></a><span data-ttu-id="a291a-136">So ändern Sie ein XML-literal</span><span class="sxs-lookup"><span data-stu-id="a291a-136">To modify an XML literal</span></span>  
  
1.  <span data-ttu-id="a291a-137">Um den Namen eines XML-Elements zu ändern, rufen Sie zuerst einen Verweis auf das Element.</span><span class="sxs-lookup"><span data-stu-id="a291a-137">To change the name of an XML element, first obtain a reference to the element.</span></span> <span data-ttu-id="a291a-138">Anschließend können Sie eine neue erstellen <xref:System.Xml.Linq.XElement>-Objekt, das einem neuen Namen, und übergeben Sie das neue <xref:System.Xml.Linq.XElement>-Objekt an die <xref:System.Xml.Linq.XNode.ReplaceWith%2A>Methode des vorhandenen <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-138">You can then create a new <xref:System.Xml.Linq.XElement> object that has a new name and pass the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XNode.ReplaceWith%2A> method of the existing <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="a291a-139">Wenn das Element, das Sie ersetzen untergeordnete Elemente, die beibehalten werden müssen verfügt, legen Sie den Wert der neuen <xref:System.Xml.Linq.XElement>-Objekt an die <xref:System.Xml.Linq.XContainer.Nodes%2A>-Eigenschaft des vorhandenen Elements.</xref:System.Xml.Linq.XContainer.Nodes%2A> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="a291a-139">If the element that you are replacing has sub-elements that must be preserved, set the value of the new <xref:System.Xml.Linq.XElement> object to the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the existing element.</span></span> <span data-ttu-id="a291a-140">Dadurch wird den Wert des neuen Elements auf den inneren XML-Codes des vorhandenen Elements festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a291a-140">This will set the value of the new element to the inner XML of the existing element.</span></span> <span data-ttu-id="a291a-141">Andernfalls können Sie den Wert des neuen Elements, das Festlegen der `Value` -Eigenschaft des vorhandenen Elements.</span><span class="sxs-lookup"><span data-stu-id="a291a-141">Otherwise, you can set the value of the new element to the `Value` property of the existing element.</span></span>  
  
     <span data-ttu-id="a291a-142">Im folgenden Codebeispiel werden alle ersetzt \<Beschreibung > Elemente mit einer \<abstrakte > Element.</span><span class="sxs-lookup"><span data-stu-id="a291a-142">The following code example replaces all \<Description> elements with an \<Abstract> element.</span></span> <span data-ttu-id="a291a-143">Der Inhalt des der \<Beschreibung > Element wird in der neuen beibehalten \<abstrakte > Element mithilfe der <xref:System.Xml.Linq.XContainer.Nodes%2A>Eigenschaft der \<Beschreibung > <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Nodes%2A></span><span class="sxs-lookup"><span data-stu-id="a291a-143">The content of the \<Description> element is preserved in the new \<Abstract> element by using the <xref:System.Xml.Linq.XContainer.Nodes%2A> property of the \<Description> <xref:System.Xml.Linq.XElement> object.</span></span>  
  
     <span data-ttu-id="a291a-144">[!code-vb[VbXmlSamples&#2;8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a291a-144">[!code-vb[VbXmlSamples2#8](../../../../visual-basic/programming-guide/language-features/xml/codesnippet/VisualBasic/how-to-modify-xml-literals_5.vb)]</span></span>  
  
     <span data-ttu-id="a291a-145">Im folgenden werden Beispiele für ursprünglichen und geänderten XML-Code aus diesem Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="a291a-145">The following shows sample source XML and modified XML from this code example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a291a-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a291a-146">See Also</span></span>  
 <span data-ttu-id="a291a-147">[Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="a291a-147">[Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md) </span></span>  
<span data-ttu-id="a291a-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="a291a-148"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="a291a-149"> [Gewusst wie: Laden von XML aus einer Datei, die Zeichenfolge oder den Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span><span class="sxs-lookup"><span data-stu-id="a291a-149"> [How to: Load XML from a File, String, or Stream](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md) </span></span>  
<span data-ttu-id="a291a-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="a291a-150"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="a291a-151"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="a291a-151"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
