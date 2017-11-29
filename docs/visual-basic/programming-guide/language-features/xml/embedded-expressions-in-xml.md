---
title: "Eingebettete Ausdrücke in XML (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b1cdba0a39a932f143ac98c2514240e1696a8fe0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="19ca2-102">Eingebettete Ausdrücke in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19ca2-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="19ca2-103">Mit eingebetteten können Ausdrücken Sie XML-Literale erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="19ca2-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="19ca2-104">Die Syntax für einen eingebetteten Ausdruck `<%=` `expression` `%>`, denen ist identisch, verwendet die Syntax in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19ca2-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="19ca2-105">Beispielsweise können Sie ein XML-Element literal erstellen eingebettete Ausdrücke mit Literaltext kombinieren.</span><span class="sxs-lookup"><span data-stu-id="19ca2-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]  
  
 <span data-ttu-id="19ca2-106">Wenn `isbnNumber` enthält die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert des `book` ist:</span><span class="sxs-lookup"><span data-stu-id="19ca2-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="19ca2-107">Speicherort der eingebetteten Ausdruck und Überprüfung</span><span class="sxs-lookup"><span data-stu-id="19ca2-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="19ca2-108">Eingebettete Ausdrücke können nur an bestimmten Positionen im XML-Literale Ausdrücke angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="19ca2-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="19ca2-109">Der Ausdruck Speicherort-steuert, welche die Typen der Ausdruck zurückgeben können und wie `Nothing` behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="19ca2-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="19ca2-110">Die folgende Tabelle beschreibt die zulässigen Positionen und Typen von eingebetteten Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="19ca2-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="19ca2-111">Position im literal</span><span class="sxs-lookup"><span data-stu-id="19ca2-111">Location in literal</span></span>|<span data-ttu-id="19ca2-112">Der Typ des Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="19ca2-112">Type of expression</span></span>|<span data-ttu-id="19ca2-113">Behandlung von`Nothing`</span><span class="sxs-lookup"><span data-stu-id="19ca2-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="19ca2-114">XML-Elementnamen</span><span class="sxs-lookup"><span data-stu-id="19ca2-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="19ca2-115">Fehler</span><span class="sxs-lookup"><span data-stu-id="19ca2-115">Error</span></span>|  
|<span data-ttu-id="19ca2-116">XML-Elementinhalt.</span><span class="sxs-lookup"><span data-stu-id="19ca2-116">XML element content</span></span>|<span data-ttu-id="19ca2-117">`Object`oder ein Array von`Object`</span><span class="sxs-lookup"><span data-stu-id="19ca2-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="19ca2-118">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="19ca2-118">Ignored</span></span>|  
|<span data-ttu-id="19ca2-119">XML-Element-Attributnamen</span><span class="sxs-lookup"><span data-stu-id="19ca2-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="19ca2-120">Fehler, es sei denn, Sie auch den Wert des Attributs ist`Nothing`</span><span class="sxs-lookup"><span data-stu-id="19ca2-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="19ca2-121">XML-Element-Attributwert</span><span class="sxs-lookup"><span data-stu-id="19ca2-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="19ca2-122">Attributdeklaration ignoriert</span><span class="sxs-lookup"><span data-stu-id="19ca2-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="19ca2-123">XML-Element-Attribut</span><span class="sxs-lookup"><span data-stu-id="19ca2-123">XML element attribute</span></span>|<span data-ttu-id="19ca2-124"><xref:System.Xml.Linq.XAttribute>oder eine Auflistung von<xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="19ca2-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="19ca2-125">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="19ca2-125">Ignored</span></span>|  
|<span data-ttu-id="19ca2-126">Stammelement des XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="19ca2-126">XML document root element</span></span>|<span data-ttu-id="19ca2-127"><xref:System.Xml.Linq.XElement>oder eine Auflistung von einem <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte</span><span class="sxs-lookup"><span data-stu-id="19ca2-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="19ca2-128">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="19ca2-128">Ignored</span></span>|  
  
-   <span data-ttu-id="19ca2-129">Beispiel für einen eingebetteten Ausdruck in den Namen eines XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="19ca2-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]  
  
-   <span data-ttu-id="19ca2-130">Beispiel für einen eingebetteten Ausdruck im Inhalt eines XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="19ca2-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]  
  
-   <span data-ttu-id="19ca2-131">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut-Namen:</span><span class="sxs-lookup"><span data-stu-id="19ca2-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]  
  
-   <span data-ttu-id="19ca2-132">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:</span><span class="sxs-lookup"><span data-stu-id="19ca2-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]  
  
-   <span data-ttu-id="19ca2-133">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut:</span><span class="sxs-lookup"><span data-stu-id="19ca2-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]  
  
-   <span data-ttu-id="19ca2-134">Beispiel für einen eingebetteten Ausdruck in ein XML-Dokument-Stammelement:</span><span class="sxs-lookup"><span data-stu-id="19ca2-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]  
  
 <span data-ttu-id="19ca2-135">Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks in den erforderlichen Typ erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="19ca2-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="19ca2-136">Die einzige Ausnahme ist für das Stammelement eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="19ca2-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="19ca2-137">Wenn Sie bei der Kompilierung ohne `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.</span><span class="sxs-lookup"><span data-stu-id="19ca2-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="19ca2-138">An Standorten, in dem der Inhalt optional ist, eingebettete Ausdrücke, die enthalten `Nothing` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="19ca2-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="19ca2-139">Dies bedeutet, dass Sie keine Elementinhalt, Attributwerte, überprüfen und Elemente des Arrays sind nicht `Nothing` vor der Verwendung eines XML-Literals.</span><span class="sxs-lookup"><span data-stu-id="19ca2-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="19ca2-140">Erforderlich, nicht mit Werten, z. B. Element- und Attributnamen verwendet, `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="19ca2-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="19ca2-141">Weitere Informationen zur Verwendung von eines eingebetteten Ausdrucks in einen bestimmten Typ eines Literals finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="19ca2-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="19ca2-142">Bereichsregeln</span><span class="sxs-lookup"><span data-stu-id="19ca2-142">Scoping Rules</span></span>  
 <span data-ttu-id="19ca2-143">Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den jeweiligen literal.</span><span class="sxs-lookup"><span data-stu-id="19ca2-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="19ca2-144">Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="19ca2-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="19ca2-145">Dies bedeutet, dass alle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Programmierelemente, die ein XML-Literal zur Verfügung stehen auch für deren eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="19ca2-145">This means that all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="19ca2-146">In einem XML-literal, erreichen Sie den deklarierten XML-Namespacepräfixe mit der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="19ca2-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="19ca2-147">Sie können ein neue XML-Namespacepräfix deklariert oder Shadowing für eine vorhandene XML-Namespacepräfix in einem Element mit dem `xmlns` Attribut.</span><span class="sxs-lookup"><span data-stu-id="19ca2-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="19ca2-148">Der neue Namespace ist verfügbar, um die untergeordneten Knoten des jeweiligen Elements, jedoch nicht in XML-Literale in eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="19ca2-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19ca2-149">Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="19ca2-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="19ca2-150">In dieser Hinsicht mithilfe der `xmlns` Attribut ist, wie die Verwendung der `Imports` -Anweisung zum Deklarieren eines XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="19ca2-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="19ca2-151">Einen eingebetteten Ausdruck können Sie die XML-Namespacewert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="19ca2-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ca2-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19ca2-152">See Also</span></span>  
 [<span data-ttu-id="19ca2-153">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19ca2-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="19ca2-154">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="19ca2-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="19ca2-155">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="19ca2-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="19ca2-156">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="19ca2-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="19ca2-157">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="19ca2-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="19ca2-158">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="19ca2-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
