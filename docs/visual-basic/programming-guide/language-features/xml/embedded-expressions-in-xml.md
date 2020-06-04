---
title: Eingebettete Ausdrücke in XML
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: d4ff9442aa82a3eb46d56500159562174646ea58
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410256"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a><span data-ttu-id="24d37-102">Eingebettete Ausdrücke in XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24d37-102">Embedded Expressions in XML (Visual Basic)</span></span>
<span data-ttu-id="24d37-103">Mit eingebetteten Ausdrücken können Sie XML-Literale erstellen, die Ausdrücke enthalten, die zur Laufzeit ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="24d37-103">Embedded expressions enable you to create XML literals that contain expressions that are evaluated at run time.</span></span> <span data-ttu-id="24d37-104">Die Syntax für einen eingebetteten Ausdruck ist `<%=` `expression` `%>` , was mit der in ASP.NET verwendeten Syntax identisch ist.</span><span class="sxs-lookup"><span data-stu-id="24d37-104">The syntax for an embedded expression is `<%=` `expression` `%>`, which is the same as the syntax used in ASP.NET.</span></span>  
  
 <span data-ttu-id="24d37-105">Sie können z. b. ein XML-Elementliteral erstellen, indem Sie eingebettete Ausdrücke mit literalem Text Inhalt kombinieren.</span><span class="sxs-lookup"><span data-stu-id="24d37-105">For example, you can create an XML element literal, combining embedded expressions with literal text content.</span></span>  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 <span data-ttu-id="24d37-106">Wenn `isbnNumber` die Ganzzahl 12345 enthält und `modifiedDate` das Datum 3/5/2006 enthält, ist der Wert von, wenn dieser Code ausgeführt wird, `book` :</span><span class="sxs-lookup"><span data-stu-id="24d37-106">If `isbnNumber` contains the integer 12345 and `modifiedDate` contains the date 3/5/2006, when this code executes, the value of `book` is:</span></span>  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a><span data-ttu-id="24d37-107">Speicherort und Validierung des eingebetteten Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="24d37-107">Embedded Expression Location and Validation</span></span>  
 <span data-ttu-id="24d37-108">Eingebettete Ausdrücke können nur an bestimmten Positionen innerhalb von XML-Literalausdrücken vorkommen.</span><span class="sxs-lookup"><span data-stu-id="24d37-108">Embedded expressions can appear only at certain locations within XML literal expressions.</span></span> <span data-ttu-id="24d37-109">Der Ausdrucks Speicherort steuert, welche Typen der Ausdruck zurückgeben kann und wie `Nothing` verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="24d37-109">The expression location controls which types the expression can return and how `Nothing` is handled.</span></span> <span data-ttu-id="24d37-110">In der folgenden Tabelle werden die zulässigen Speicherorte und Typen von eingebetteten Ausdrücken beschrieben.</span><span class="sxs-lookup"><span data-stu-id="24d37-110">The following table describes the allowed locations and types of embedded expressions.</span></span>  
  
|<span data-ttu-id="24d37-111">Speicherort in Literalen</span><span class="sxs-lookup"><span data-stu-id="24d37-111">Location in literal</span></span>|<span data-ttu-id="24d37-112">Typ des Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="24d37-112">Type of expression</span></span>|<span data-ttu-id="24d37-113">Behandlung von`Nothing`</span><span class="sxs-lookup"><span data-stu-id="24d37-113">Handling of `Nothing`</span></span>|  
|---|---|---|  
|<span data-ttu-id="24d37-114">XML-Elementname</span><span class="sxs-lookup"><span data-stu-id="24d37-114">XML element name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="24d37-115">Fehler</span><span class="sxs-lookup"><span data-stu-id="24d37-115">Error</span></span>|  
|<span data-ttu-id="24d37-116">Inhalt des XML-Elements</span><span class="sxs-lookup"><span data-stu-id="24d37-116">XML element content</span></span>|<span data-ttu-id="24d37-117">`Object`oder Array von`Object`</span><span class="sxs-lookup"><span data-stu-id="24d37-117">`Object` or array of `Object`</span></span>|<span data-ttu-id="24d37-118">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="24d37-118">Ignored</span></span>|  
|<span data-ttu-id="24d37-119">Name des XML-Element Attributs</span><span class="sxs-lookup"><span data-stu-id="24d37-119">XML element attribute name</span></span>|<xref:System.Xml.Linq.XName>|<span data-ttu-id="24d37-120">Fehler, es sei denn, der Attribut Wert ist ebenfalls`Nothing`</span><span class="sxs-lookup"><span data-stu-id="24d37-120">Error, unless the attribute value is also `Nothing`</span></span>|  
|<span data-ttu-id="24d37-121">XML-Element Attribut Wert</span><span class="sxs-lookup"><span data-stu-id="24d37-121">XML element attribute value</span></span>|`Object`|<span data-ttu-id="24d37-122">Attribut Deklaration wird ignoriert</span><span class="sxs-lookup"><span data-stu-id="24d37-122">Attribute declaration ignored</span></span>|  
|<span data-ttu-id="24d37-123">XML-Element Attribut</span><span class="sxs-lookup"><span data-stu-id="24d37-123">XML element attribute</span></span>|<span data-ttu-id="24d37-124"><xref:System.Xml.Linq.XAttribute>oder eine Auflistung von<xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="24d37-124"><xref:System.Xml.Linq.XAttribute> or a collection of <xref:System.Xml.Linq.XAttribute></span></span>|<span data-ttu-id="24d37-125">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="24d37-125">Ignored</span></span>|  
|<span data-ttu-id="24d37-126">Stamm Element des XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="24d37-126">XML document root element</span></span>|<span data-ttu-id="24d37-127"><xref:System.Xml.Linq.XElement>oder eine Auflistung von einem- <xref:System.Xml.Linq.XElement> Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> -Objekten und- <xref:System.Xml.Linq.XComment> Objekten</span><span class="sxs-lookup"><span data-stu-id="24d37-127"><xref:System.Xml.Linq.XElement> or a collection of one <xref:System.Xml.Linq.XElement> object and an arbitrary number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects</span></span>|<span data-ttu-id="24d37-128">Ignoriert</span><span class="sxs-lookup"><span data-stu-id="24d37-128">Ignored</span></span>|  
  
- <span data-ttu-id="24d37-129">Beispiel für einen eingebetteten Ausdruck in einem XML-Elementnamen:</span><span class="sxs-lookup"><span data-stu-id="24d37-129">Example of an embedded expression in an XML element name:</span></span>  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- <span data-ttu-id="24d37-130">Beispiel eines eingebetteten Ausdrucks im Inhalt eines XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="24d37-130">Example of an embedded expression in the content of an XML element:</span></span>  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- <span data-ttu-id="24d37-131">Beispiel für einen eingebetteten Ausdruck in einem XML-Element Attributnamen:</span><span class="sxs-lookup"><span data-stu-id="24d37-131">Example of an embedded expression in an XML element attribute name:</span></span>  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- <span data-ttu-id="24d37-132">Beispiel für einen eingebetteten Ausdruck in einem Attribut Wert des XML-Elements:</span><span class="sxs-lookup"><span data-stu-id="24d37-132">Example of an embedded expression in an XML element attribute value:</span></span>  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- <span data-ttu-id="24d37-133">Beispiel für einen eingebetteten Ausdruck in einem XML-Element Attribut:</span><span class="sxs-lookup"><span data-stu-id="24d37-133">Example of an embedded expression in an XML element attribute:</span></span>  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- <span data-ttu-id="24d37-134">Beispiel eines eingebetteten Ausdrucks in einem XML-Dokument Stamm Element:</span><span class="sxs-lookup"><span data-stu-id="24d37-134">Example of an embedded expression in an XML document root element:</span></span>  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 <span data-ttu-id="24d37-135">Wenn Sie aktivieren `Option Strict` , prüft der Compiler, ob der Typ jedes eingebetteten Ausdrucks auf den erforderlichen Typ erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="24d37-135">If you enable `Option Strict`, the compiler checks that the type of each embedded expression widens to the required type.</span></span> <span data-ttu-id="24d37-136">Die einzige Ausnahme gilt für das Stamm Element eines XML-Dokuments, das überprüft wird, wenn der Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="24d37-136">The only exception is for the root element of an XML document, which is verified when the code runs.</span></span> <span data-ttu-id="24d37-137">Wenn Sie ohne kompilieren `Option Strict` , können Sie Ausdrücke vom Typ einbetten, `Object` und der Typ wird zur Laufzeit überprüft.</span><span class="sxs-lookup"><span data-stu-id="24d37-137">If you compile without `Option Strict`, you can embed expressions of type `Object` and their type is verified at run time.</span></span>  
  
 <span data-ttu-id="24d37-138">An Standorten, an denen Inhalt optional ist, werden eingebettete Ausdrücke, die enthalten, `Nothing` ignoriert.</span><span class="sxs-lookup"><span data-stu-id="24d37-138">In locations where content is optional, embedded expressions that contain `Nothing` are ignored.</span></span> <span data-ttu-id="24d37-139">Dies bedeutet, dass Sie nicht überprüfen müssen, ob Element Inhalt, Attributwerte und Array Elemente nicht `Nothing` vor der Verwendung eines XML-Literals vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="24d37-139">This means you do not have to check that element content, attribute values, and array elements are not `Nothing` before you use an XML literal.</span></span> <span data-ttu-id="24d37-140">Erforderliche Werte, z. b. Element-und Attributnamen, dürfen nicht sein `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="24d37-140">Required values, such as element and attribute names, cannot be `Nothing`.</span></span>  
  
 <span data-ttu-id="24d37-141">Weitere Informationen zum Verwenden eines eingebetteten Ausdrucks in einem bestimmten Literaltyp finden Sie unter [XML-dokumentliterale](../../../language-reference/xml-literals/xml-document-literal.md), [XML-Elementliterale](../../../language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="24d37-141">For more information about using an embedded expression in a particular type of literal, see [XML Document Literal](../../../language-reference/xml-literals/xml-document-literal.md), [XML Element Literal](../../../language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="scoping-rules"></a><span data-ttu-id="24d37-142">Bereichsregeln</span><span class="sxs-lookup"><span data-stu-id="24d37-142">Scoping Rules</span></span>  
 <span data-ttu-id="24d37-143">Der Compiler konvertiert alle XML-Literale in einen konstruktorrückruf für den entsprechenden Literaltyp.</span><span class="sxs-lookup"><span data-stu-id="24d37-143">The compiler converts each XML literal into a constructor call for the appropriate literal type.</span></span> <span data-ttu-id="24d37-144">Der Literale Inhalt und eingebettete Ausdrücke in einem XML-Literalformat werden als Argumente an den Konstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="24d37-144">The literal content and embedded expressions in an XML literal are passed as arguments to the constructor.</span></span> <span data-ttu-id="24d37-145">Dies bedeutet, dass alle Visual Basic Programmier Elemente, die für ein XML-wahrsten verfügbar sind, auch für eingebettete Ausdrücke verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="24d37-145">This means that all Visual Basic programming elements available to an XML literal are also available to its embedded expressions.</span></span>  
  
 <span data-ttu-id="24d37-146">Innerhalb eines XML-Literals können Sie auf die XML-Namespace Präfixe zugreifen, die mit der-Anweisung deklariert werden `Imports` .</span><span class="sxs-lookup"><span data-stu-id="24d37-146">Within an XML literal, you can access the XML namespace prefixes declared with the `Imports` statement.</span></span> <span data-ttu-id="24d37-147">Mithilfe des-Attributs können Sie ein neues XML-Namespace Präfix oder einen Schatten für ein vorhandenes XML-Namespace Präfix in einem-Element deklarieren `xmlns` .</span><span class="sxs-lookup"><span data-stu-id="24d37-147">You can declare a new XML namespace prefix, or shadow an existing XML namespace prefix, in an element by using the `xmlns` attribute.</span></span> <span data-ttu-id="24d37-148">Der neue Namespace ist für die untergeordneten Knoten dieses Elements verfügbar, jedoch nicht für XML-Literale in eingebetteten Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="24d37-148">The new namespace is available to the child nodes of that element, but not to XML literals in embedded expressions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24d37-149">Wenn Sie ein XML-Namespace Präfix mithilfe des `xmlns` Namespace-Attributs deklarieren, muss der Attribut Wert eine Konstante Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="24d37-149">When you declare an XML namespace prefix by using the `xmlns` namespace attribute, the attribute value must be a constant string.</span></span> <span data-ttu-id="24d37-150">In dieser Hinsicht ähnelt die Verwendung des- `xmlns` Attributs der Verwendung der- `Imports` Anweisung, um einen XML-Namespace zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="24d37-150">In this regard, using the `xmlns` attribute is like using the `Imports` statement to declare an XML namespace.</span></span> <span data-ttu-id="24d37-151">Sie können keinen eingebetteten Ausdruck verwenden, um den XML-Namespace Wert anzugeben.</span><span class="sxs-lookup"><span data-stu-id="24d37-151">You cannot use an embedded expression to specify the XML namespace value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d37-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24d37-152">See also</span></span>

- [<span data-ttu-id="24d37-153">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24d37-153">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="24d37-154">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="24d37-154">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="24d37-155">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="24d37-155">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="24d37-156">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="24d37-156">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="24d37-157">Imports-Anweisung (.NET-Namespace und Typ)</span><span class="sxs-lookup"><span data-stu-id="24d37-157">Imports Statement (.NET Namespace and Type)</span></span>](../../../language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="24d37-158">Übersicht über XML-Literale</span><span class="sxs-lookup"><span data-stu-id="24d37-158">XML Literals Overview</span></span>](xml-literals-overview.md)
