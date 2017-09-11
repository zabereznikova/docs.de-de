---
title: "Eingebettete Ausdrücke in XML (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vb.XmlEmbeddedExpression
dev_langs:
- VB
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
caps.latest.revision: 22
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
ms.openlocfilehash: d24a49f2fa6fd66fe6e4c7724bd4298d65fb7a59
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="e7578-102">Eingebettete Ausdrücke in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7578-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="e7578-103">Mit eingebetteten können Ausdrücken Sie XML-Literale zu erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="e7578-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="e7578-104">Die Syntax für einen eingebetteten Ausdruck lautet `<%=` `expression` `%>`, das ist identisch mit der Syntax in verwendet [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7578-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].</span></span>  
  
 <span data-ttu-id="e7578-105">Beispielsweise können Sie ein XML-Element literal erstellen eingebettete Ausdrücke mit Literaltext kombinieren.</span><span class="sxs-lookup"><span data-stu-id="e7578-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 <span data-ttu-id="e7578-106">[!code-vb[VbXMLSamples&#27;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-106">[!code-vb[VbXMLSamples#27](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="e7578-107">Wenn `isbnNumber` die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert des `book` ist:</span><span class="sxs-lookup"><span data-stu-id="e7578-107">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="e7578-108">Eingebettete Ausdrücke Positionierung und Validierung</span><span class="sxs-lookup"><span data-stu-id="e7578-108">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="e7578-109">Eingebettete Ausdrücke können nur an bestimmten Positionen in XML-Literale Ausdrücke angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e7578-109">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="e7578-110">Position des Ausdrucks legt die Typen der Ausdruck zurückgeben können und wie `Nothing` behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="e7578-110">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="e7578-111">Die folgende Tabelle beschreibt die zulässigen Positionen und Typen von eingebetteten Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="e7578-111">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="e7578-112">Position im literal</span><span class="sxs-lookup"><span data-stu-id="e7578-112">Location in literal</span></span>|<span data-ttu-id="e7578-113">Der Typ des Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="e7578-113">Type of expression</span></span>|<span data-ttu-id="e7578-114">Behandlung von`Nothing`</span><span class="sxs-lookup"><span data-stu-id="e7578-114">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="e7578-115">XML-Elementnamen</span><span class="sxs-lookup"><span data-stu-id="e7578-115">XML element name</span></span>|<span data-ttu-id="e7578-116"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e7578-116"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="e7578-117">Fehler</span><span class="sxs-lookup"><span data-stu-id="e7578-117">Error</span></span>|  
|<span data-ttu-id="e7578-118">XML-Elementinhalt.</span><span class="sxs-lookup"><span data-stu-id="e7578-118">XML element content</span></span>|<span data-ttu-id="e7578-119">`Object`oder ein Array von`Object`</span><span class="sxs-lookup"><span data-stu-id="e7578-119">`Object` or array of `Object`</span></span>|<span data-ttu-id="e7578-120">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="e7578-120">Ignored</span></span>|  
|<span data-ttu-id="e7578-121">XML-Elementname-Attribut</span><span class="sxs-lookup"><span data-stu-id="e7578-121">XML element attribute name</span></span>|<span data-ttu-id="e7578-122"><xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="e7578-122"><xref:System.Xml.Linq.XName></span></span>|<span data-ttu-id="e7578-123">Fehler, es sei denn, Sie auch den Wert des Attributs ist`Nothing`</span><span class="sxs-lookup"><span data-stu-id="e7578-123">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="e7578-124">XML-Element-Attributwert</span><span class="sxs-lookup"><span data-stu-id="e7578-124">XML element attribute value</span></span>|`Object`|<span data-ttu-id="e7578-125">Attributdeklaration wird ignoriert</span><span class="sxs-lookup"><span data-stu-id="e7578-125">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="e7578-126">XML-Element-Attribut</span><span class="sxs-lookup"><span data-stu-id="e7578-126">XML element attribute</span></span>|<span data-ttu-id="e7578-127"><xref:System.Xml.Linq.XAttribute>oder eine Auflistung von<xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="e7578-127"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="e7578-128">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="e7578-128">Ignored</span></span>|  
|<span data-ttu-id="e7578-129">Stammelement des XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="e7578-129">XML document root element</span></span>|<span data-ttu-id="e7578-130"><xref:System.Xml.Linq.XElement>oder eine Auflistung von einem <xref:System.Xml.Linq.XElement>Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> <xref:System.Xml.Linq.XComment>Objekten</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e7578-130"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="e7578-131">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="e7578-131">Ignored</span></span>|  
  
-   <span data-ttu-id="e7578-132">Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname:</span><span class="sxs-lookup"><span data-stu-id="e7578-132">Example of an embedded expression in an XML element name:</span></span>  
  
     <span data-ttu-id="e7578-133">[!code-vb[VbXMLSamples&#32;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-133">[!code-vb[VbXMLSamples#32](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_2.vb)]</span></span>  
  
-   <span data-ttu-id="e7578-134">Beispiel für einen eingebetteten Ausdruck im Inhalt eines XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="e7578-134">Example of an embedded expression in the content of an XML element:</span></span>  
  
     <span data-ttu-id="e7578-135">[!code-vb[VbXMLSamples&33;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-135">[!code-vb[VbXMLSamples#33](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_3.vb)]</span></span>  
  
-   <span data-ttu-id="e7578-136">Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname-Attribut:</span><span class="sxs-lookup"><span data-stu-id="e7578-136">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     <span data-ttu-id="e7578-137">[!code-vb[VbXMLSamples&#34;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-137">[!code-vb[VbXMLSamples#34](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_4.vb)]</span></span>  
  
-   <span data-ttu-id="e7578-138">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:</span><span class="sxs-lookup"><span data-stu-id="e7578-138">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     <span data-ttu-id="e7578-139">[!code-vb[VbXMLSamples&#35;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-139">[!code-vb[VbXMLSamples#35](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_5.vb)]</span></span>  
  
-   <span data-ttu-id="e7578-140">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attribut:</span><span class="sxs-lookup"><span data-stu-id="e7578-140">Example of an embedded expression in an XML element attribute:</span></span>  
  
     <span data-ttu-id="e7578-141">[!code-vb[VbXMLSamples Nr.&36;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-141">[!code-vb[VbXMLSamples#36](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_6.vb)]</span></span>  
  
-   <span data-ttu-id="e7578-142">Beispiel für einen eingebetteten Ausdruck in einem XML-Dokument-Stammelement:</span><span class="sxs-lookup"><span data-stu-id="e7578-142">Example of an embedded expression in an XML document root element:</span></span>  
  
     <span data-ttu-id="e7578-143">[!code-vb[VbXMLSamples&#37;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="e7578-143">[!code-vb[VbXMLSamples#37](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/embedded-expressions-in-xml_7.vb)]</span></span>  
  
 <span data-ttu-id="e7578-144">Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks auf den erforderlichen Typ erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="e7578-144">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="e7578-145">Die einzige Ausnahme gilt für das Stammelement eines XML-Dokuments, die überprüft wird, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7578-145">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="e7578-146">Wenn Sie ohne Kompilieren `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.</span><span class="sxs-lookup"><span data-stu-id="e7578-146">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="e7578-147">An Standorten, in dem Inhalte optional und ist, eingebetteten Ausdrücken, die enthalten `Nothing` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="e7578-147">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="e7578-148">Dies bedeutet, dass Sie keinen Elementinhalt, Attributwerte zu überprüfen und Arrayelemente sind nicht `Nothing` vor der Verwendung von XML-Literal.</span><span class="sxs-lookup"><span data-stu-id="e7578-148">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="e7578-149">Erforderliche Werte, z. B. Element- und Attributnamen, nicht `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e7578-149">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="e7578-150">Weitere Informationen zur Verwendung von eingebetteten Ausdrücken in Literalen eines bestimmten Typs finden Sie unter [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e7578-150">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="e7578-151">Bereichsregeln</span><span class="sxs-lookup"><span data-stu-id="e7578-151">Scoping Rules</span></span>  
 <span data-ttu-id="e7578-152">Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den entsprechenden literal.</span><span class="sxs-lookup"><span data-stu-id="e7578-152">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="e7578-153">Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="e7578-153">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="e7578-154">Dies bedeutet, dass alle [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] XML-Literale verfügbaren Programmierelemente sind auch für deren eingebettete Ausdrücke verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7578-154">This means that all [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="e7578-155">Sie können in einem XML-literal der deklarierten XML-Namespacepräfixe mit zugreifen der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e7578-155">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="e7578-156">Sie können ein neue XML-Namespacepräfix deklariert oder Shadowing ein vorhandenen XML-Namespacepräfix, in einem Element mit dem `xmlns` Attribut.</span><span class="sxs-lookup"><span data-stu-id="e7578-156">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="e7578-157">Der neue Namespace ist auch die untergeordneten Knoten des Elements, jedoch nicht für XML-Literale in eingebetteten Ausdrücken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7578-157">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7578-158">Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="e7578-158">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="e7578-159">In dieser Hinsicht mithilfe der `xmlns` -Attribut ist vergleichbar mit der `Imports` -Anweisung zum Deklarieren eines XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="e7578-159">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="e7578-160">Einen eingebetteten Ausdruck können Sie den Wert des XML-Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="e7578-160">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7578-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7578-161">See Also</span></span>  
 <span data-ttu-id="e7578-162">[Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e7578-162">[Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="e7578-163"> [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e7578-163"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="e7578-164"> [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e7578-164"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="e7578-165"> [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e7578-165"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="e7578-166"> [Imports-Anweisung (.NET-Namespace und -Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="e7578-166"> [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="e7578-167"> [Übersicht über XML-Literale](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e7578-167"> [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)</span></span>
