---
title: Eingebettete Ausdrücke in XML (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: feb0168c216b23ff02ca9350f868e091fefca689
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965786"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="5aca1-102">Eingebettete Ausdrücke in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5aca1-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="5aca1-103">Eingebettete Ausdrücke ermöglichen Ihnen die Erstellung von XML-Literale, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="5aca1-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="5aca1-104">Die Syntax für einen eingebetteten Ausdruck ist `<%=` `expression` `%>`, das ist identisch mit der Syntax in verwendet [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aca1-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="5aca1-105">Beispielsweise können Sie ein XML-Element Zeichenliteral erstellen eingebettete Ausdrücke mit Inhalt für Literaltext kombinieren.</span><span class="sxs-lookup"><span data-stu-id="5aca1-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="5aca1-106">Wenn `isbnNumber` enthält die ganze Zahl 12345 und `modifiedDate` enthält das Datum, 3/5/2006, wenn dieser Code ausgeführt wird, den Wert der `book` ist:</span><span class="sxs-lookup"><span data-stu-id="5aca1-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="5aca1-107">Speicherort des eingebetteten Ausdrucks und Überprüfung</span><span class="sxs-lookup"><span data-stu-id="5aca1-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="5aca1-108">Eingebettete Ausdrücke können nur an bestimmten Speicherorten innerhalb der XML-Literale Ausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5aca1-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="5aca1-109">Position des Ausdrucks legt die Typen der Ausdruck zurückgeben können und wie `Nothing` erfolgt.</span><span class="sxs-lookup"><span data-stu-id="5aca1-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="5aca1-110">Die folgende Tabelle beschreibt die zulässigen Standorte und die Typen von eingebetteten Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="5aca1-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="5aca1-111">Position im literal</span><span class="sxs-lookup"><span data-stu-id="5aca1-111">Location in literal</span></span>|<span data-ttu-id="5aca1-112">Der Typ des Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="5aca1-112">Type of expression</span></span>|<span data-ttu-id="5aca1-113">Behandlung von `Nothing`</span><span class="sxs-lookup"><span data-stu-id="5aca1-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="5aca1-114">XML-Elementname</span><span class="sxs-lookup"><span data-stu-id="5aca1-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="5aca1-115">Fehler</span><span class="sxs-lookup"><span data-stu-id="5aca1-115">Error</span></span>|  
|<span data-ttu-id="5aca1-116">XML-Elementinhalt.</span><span class="sxs-lookup"><span data-stu-id="5aca1-116">XML element content</span></span>|<span data-ttu-id="5aca1-117">`Object` oder ein Array von `Object`</span><span class="sxs-lookup"><span data-stu-id="5aca1-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="5aca1-118">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="5aca1-118">Ignored</span></span>|  
|<span data-ttu-id="5aca1-119">XML-Elementname-Attribut</span><span class="sxs-lookup"><span data-stu-id="5aca1-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="5aca1-120">Fehler, es sei denn, der den Wert des Attributs auch ist `Nothing`</span><span class="sxs-lookup"><span data-stu-id="5aca1-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="5aca1-121">XML-Element-Attributwert</span><span class="sxs-lookup"><span data-stu-id="5aca1-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="5aca1-122">Attributdeklaration ignoriert</span><span class="sxs-lookup"><span data-stu-id="5aca1-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="5aca1-123">XML-Element-Attribut</span><span class="sxs-lookup"><span data-stu-id="5aca1-123">XML element attribute</span></span>|<span data-ttu-id="5aca1-124"><xref:System.Xml.Linq.XAttribute> oder eine Auflistung von <xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="5aca1-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="5aca1-125">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="5aca1-125">Ignored</span></span>|  
|<span data-ttu-id="5aca1-126">Stammelement des XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="5aca1-126">XML document root element</span></span>|<span data-ttu-id="5aca1-127"><xref:System.Xml.Linq.XElement> oder eine Auflistung von einem <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte</span><span class="sxs-lookup"><span data-stu-id="5aca1-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="5aca1-128">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="5aca1-128">Ignored</span></span>|  
  
-   <span data-ttu-id="5aca1-129">Beispiel für einen eingebetteten Ausdruck in ein XML-Elementname:</span><span class="sxs-lookup"><span data-stu-id="5aca1-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
-   <span data-ttu-id="5aca1-130">Beispiel für einen eingebetteten Ausdruck in den Inhalt eines XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="5aca1-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
-   <span data-ttu-id="5aca1-131">Beispiel für einen eingebetteten Ausdruck in eine XML-Elementname-Attribut:</span><span class="sxs-lookup"><span data-stu-id="5aca1-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
-   <span data-ttu-id="5aca1-132">Beispiel für einen eingebetteten Ausdruck in einem XML-Element-Attributwert:</span><span class="sxs-lookup"><span data-stu-id="5aca1-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
-   <span data-ttu-id="5aca1-133">Beispiel für einen eingebetteten Ausdruck in ein XML-Element-Attribut:</span><span class="sxs-lookup"><span data-stu-id="5aca1-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
-   <span data-ttu-id="5aca1-134">Beispiel für einen eingebetteten Ausdruck in das Stammelement eines XML-Dokuments:</span><span class="sxs-lookup"><span data-stu-id="5aca1-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="5aca1-135">Wenn Sie aktivieren `Option Strict`, überprüft der Compiler, dass der Typ jedes eingebetteten Ausdrucks in den erforderlichen Typ erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="5aca1-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="5aca1-136">Die einzige Ausnahme ist für das Stammelement eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5aca1-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="5aca1-137">Wenn Sie ohne Kompilieren `Option Strict`, können Sie Ausdrücke vom Typ einbetten `Object` und deren Typ wird zur Laufzeit überprüft.</span><span class="sxs-lookup"><span data-stu-id="5aca1-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="5aca1-138">An Standorten, in dem der Inhalt optional ist, eingebettete Ausdrücke, die enthalten `Nothing` werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5aca1-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="5aca1-139">Dies bedeutet, Sie haben keinen Elementinhalt, Attributwerte zu überprüfen und die Elemente des Arrays sind nicht `Nothing` vor der Verwendung eines XML-Literals.</span><span class="sxs-lookup"><span data-stu-id="5aca1-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="5aca1-140">Erforderlich, nicht möglich, Werte, z. B. Element- und Attributnamen, `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="5aca1-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="5aca1-141">Weitere Informationen zur Verwendung von eines eingebetteten Ausdrucks in einen bestimmten Typ eines Literals finden Sie unter [XML-Dokument-Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="5aca1-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="5aca1-142">Bereichsregeln</span><span class="sxs-lookup"><span data-stu-id="5aca1-142">Scoping Rules</span></span>  
 <span data-ttu-id="5aca1-143">Der Compiler konvertiert jedes XML-literal in einen Konstruktoraufruf für den entsprechenden literal.</span><span class="sxs-lookup"><span data-stu-id="5aca1-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="5aca1-144">Die literalen Inhalt und eingebettete Ausdrücke in einem XML-Literal werden als Argumente an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="5aca1-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="5aca1-145">Dies bedeutet, dass alle Programmierelemente Visual Basic zur Verfügung, um ein XML-literal auch für die eingebettete Ausdrücke verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5aca1-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="5aca1-146">Sie können in einem XML-literal, den XML-Namespace-Präfixe, die mit deklariert zugreifen der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5aca1-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="5aca1-147">Sie können ein neues XML-Namespacepräfix deklariert oder Shadowing für eine vorhandene XML-Namespacepräfix, in einem Element mit dem `xmlns` Attribut.</span><span class="sxs-lookup"><span data-stu-id="5aca1-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="5aca1-148">Der neue Namespace ist verfügbar, die untergeordneten Knoten dieses Elements, aber nicht auf XML-Literalen in eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="5aca1-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5aca1-149">Wenn Sie ein XML-Namespacepräfix deklarieren, indem die `xmlns` Namespace-Attribut den Wert des Attributs muss eine Konstante Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="5aca1-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="5aca1-150">In dieser Hinsicht mithilfe der `xmlns` Attribut ist, wie die Verwendung der `Imports` Anweisung, um ein XML-Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="5aca1-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="5aca1-151">Sie können keinen eingebetteten Ausdruck verwenden, um die XML-Namespacewert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5aca1-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aca1-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aca1-152">See also</span></span>
- [<span data-ttu-id="5aca1-153">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5aca1-153">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="5aca1-154">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="5aca1-154">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="5aca1-155">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="5aca1-155">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="5aca1-156">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5aca1-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="5aca1-157">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="5aca1-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="5aca1-158">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="5aca1-158">XML Literals Overview</span></span>](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
