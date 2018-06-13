---
title: XML-Elementliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: 55d5d1410a65ea8c800bbd2b310907a6d6a61c61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605133"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="bd5fa-102">XML-Elementliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="bd5fa-103">Ein Literal, das stellt ein <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd5fa-104">Syntax</span></span>  
  
```xml  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="bd5fa-105">Teile</span><span class="sxs-lookup"><span data-stu-id="bd5fa-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="bd5fa-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-106">Required.</span></span> <span data-ttu-id="bd5fa-107">Öffnet beginnend Element-Tag.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="bd5fa-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-108">Required.</span></span> <span data-ttu-id="bd5fa-109">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-109">Name of the element.</span></span> <span data-ttu-id="bd5fa-110">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="bd5fa-111">Literaltext für den Elementnamen des Formulars `[ePrefix:]eName`, wobei:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>  
  
        |<span data-ttu-id="bd5fa-112">Segment</span><span class="sxs-lookup"><span data-stu-id="bd5fa-112">Part</span></span>|<span data-ttu-id="bd5fa-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd5fa-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="bd5fa-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-114">Optional.</span></span> <span data-ttu-id="bd5fa-115">XML-Namespacepräfix für das Element.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="bd5fa-116">Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung in der Datei oder auf Projektebene oder eine lokale XML-Namespace, die in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="bd5fa-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-117">Required.</span></span> <span data-ttu-id="bd5fa-118">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-118">Name of the element.</span></span> <span data-ttu-id="bd5fa-119">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bd5fa-120">-Literaltext.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-120">-   Literal text.</span></span> <span data-ttu-id="bd5fa-121">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="bd5fa-122">-Eingebetteter Ausdruck der Form `<%= eNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-122">-   Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="bd5fa-123">Der Typ des `eNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="bd5fa-124">Eingebetteter Ausdruck der Form `<%= nameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="bd5fa-125">Der Typ des `nameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="bd5fa-126">Ein eingebetteter Ausdruck wird in ein Endtag eines Elements nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="bd5fa-127">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-127">Optional.</span></span> <span data-ttu-id="bd5fa-128">Liste der Attribute, die in das Literal deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="bd5fa-129">Jede `attribute` verfügt über einen der folgenden Syntaxangaben:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="bd5fa-130">Zuweisung des Formulars-Attribut `[aPrefix:]aName=aValue`, wobei:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>  
  
        |<span data-ttu-id="bd5fa-131">Segment</span><span class="sxs-lookup"><span data-stu-id="bd5fa-131">Part</span></span>|<span data-ttu-id="bd5fa-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bd5fa-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="bd5fa-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-133">Optional.</span></span> <span data-ttu-id="bd5fa-134">XML-Namespacepräfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="bd5fa-135">Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung oder ein lokaler XML-Namespace, die in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="bd5fa-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-136">Required.</span></span> <span data-ttu-id="bd5fa-137">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-137">Name of the attribute.</span></span> <span data-ttu-id="bd5fa-138">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bd5fa-139">-Literaltext.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-139">-   Literal text.</span></span> <span data-ttu-id="bd5fa-140">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="bd5fa-141">-Eingebetteter Ausdruck der Form `<%= aNameExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-141">-   Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="bd5fa-142">Der Typ des `aNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="bd5fa-143">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-143">Optional.</span></span> <span data-ttu-id="bd5fa-144">Der Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-144">Value of the attribute.</span></span> <span data-ttu-id="bd5fa-145">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="bd5fa-146">-Wörtlichen Text, in Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="bd5fa-147">-Eingebetteter Ausdruck der Form `<%= aValueExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-147">-   Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="bd5fa-148">Jeder Typ ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="bd5fa-149">Eingebetteter Ausdruck der Form `<%= aExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-149">Embedded expression of the form `<%= aExp %>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="bd5fa-150">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-150">Optional.</span></span> <span data-ttu-id="bd5fa-151">Gibt an, dass das Element ein leeres Element ohne Inhalt ist.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="bd5fa-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-152">Required.</span></span> <span data-ttu-id="bd5fa-153">Beendet die Element-Tag ab oder leer sein.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="bd5fa-154">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-154">Optional.</span></span> <span data-ttu-id="bd5fa-155">Der Inhalt des Elements.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="bd5fa-156">Jede `content` kann eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="bd5fa-157">Literaltext.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-157">Literal text.</span></span> <span data-ttu-id="bd5fa-158">Der Leerraum in `elementContents` ist wichtig, wenn Literaltext vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="bd5fa-159">Eingebetteter Ausdruck der Form `<%= contentExp %>`.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-159">Embedded expression of the form `<%= contentExp %>`.</span></span>  
  
    -   <span data-ttu-id="bd5fa-160">XML-Elementliteral.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="bd5fa-161">XML-Kommentarliteral.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-161">XML comment literal.</span></span> <span data-ttu-id="bd5fa-162">Finden Sie unter [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="bd5fa-163">XML-Verarbeitungsanweisungsliteral.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-163">XML processing instruction literal.</span></span> <span data-ttu-id="bd5fa-164">Finden Sie unter [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="bd5fa-165">XML CDATA-literal.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-165">XML CDATA literal.</span></span> <span data-ttu-id="bd5fa-166">Finden Sie unter [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   `</[name]>`  
  
     <span data-ttu-id="bd5fa-167">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-167">Optional.</span></span> <span data-ttu-id="bd5fa-168">Stellt das Endtag für das Element an.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="bd5fa-169">Das optionale `name` Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks ist.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd5fa-170">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bd5fa-170">Return Value</span></span>  
 <span data-ttu-id="bd5fa-171">Ein <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-171">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd5fa-172">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd5fa-172">Remarks</span></span>  
 <span data-ttu-id="bd5fa-173">Sie können mit der Syntax des XML-Elementliterals erstellen <xref:System.Xml.Linq.XElement> Objekte in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd5fa-174">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="bd5fa-175">Diese Funktion können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="bd5fa-176">Eingebettete Ausdrücke des Formulars `<%= exp %>` ermöglichen es Ihnen, einem XML-Elementliteral dynamische Informationen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="bd5fa-177">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-177">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="bd5fa-178">Visual Basic-Compiler konvertiert das XML-Elementliteral in Aufrufe an die <xref:System.Xml.Linq.XElement.%23ctor%2A> Konstruktor und, falls erforderlich, die <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="bd5fa-179">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="bd5fa-179">XML Namespaces</span></span>  
 <span data-ttu-id="bd5fa-180">XML-Namespacepräfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus dem gleichen Namespace oft im Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="bd5fa-181">Können Sie globale XML-Namespacepräfixe verwenden, die Sie definieren, mit der `Imports` -Anweisung oder lokale Präfixe, die Sie definieren, mit der `xmlns:xmlPrefix="xmlNamespace"` Attributsyntax.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="bd5fa-182">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="bd5fa-182">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="bd5fa-183">Gemäß den Bereichsregeln für XML-Namespaces haben lokale Präfixe Vorrang vor globalen Präfixen.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="bd5fa-184">Wenn ein XML-Literal einen XML-Namespace definiert, ist dieser Namespace nicht verfügbar für Ausdrücke, die in einem eingebetteten Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="bd5fa-185">Die eingebettete Ausdruck kann nur die globalen XML-Namespace zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-185">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="bd5fa-186">Visual Basic-Compiler konvertiert jedes globale XML-Namespace, der von einem XML-literal in eine lokale Namespacedefinition im generierten Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="bd5fa-187">Globale XML-Namespaces, die nicht verwendet werden, erscheinen nicht im generierten Code.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd5fa-188">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd5fa-188">Example</span></span>  
 <span data-ttu-id="bd5fa-189">Im folgende Beispiel wird gezeigt, wie ein einfaches XML-Element erstellt, die zwei geschachtelte leere Elemente.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 [!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]  
  
 <span data-ttu-id="bd5fa-190">Das Beispiel zeigt den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-190">The example displays the following text.</span></span> <span data-ttu-id="bd5fa-191">Beachten Sie, dass das Literal, die Struktur der leeren Elemente beibehält.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-191">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```xml  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="bd5fa-192">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd5fa-192">Example</span></span>  
 <span data-ttu-id="bd5fa-193">Das folgende Beispiel zeigt, wie mit eingebetteten Ausdrücken erstellen Attribute und benennen ein Element.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 [!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]  
  
 <span data-ttu-id="bd5fa-194">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-194">This code displays the following text:</span></span>  
  
```xml  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="bd5fa-195">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bd5fa-195">Example</span></span>  
 <span data-ttu-id="bd5fa-196">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="bd5fa-197">Klicken Sie dann das Präfix des Namespace zum Erstellen von XML-literal verwendet, und zeigt die endgültige Form des Elements an.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]  
  
 <span data-ttu-id="bd5fa-198">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bd5fa-198">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="bd5fa-199">Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfixdefinition für den XML-Namespace konvertiert.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="bd5fa-200">Die \<Ns:middle >-Element definiert das XML-Namespacepräfix für die \<Ns:inner1 > Element.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="bd5fa-201">Allerdings die \<Ns:inner2 >-Element verwendet den Namespace definiert, durch die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bd5fa-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5fa-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd5fa-202">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="bd5fa-203">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="bd5fa-203">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)  
 [<span data-ttu-id="bd5fa-204">XML-Kommentarliteral</span><span class="sxs-lookup"><span data-stu-id="bd5fa-204">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="bd5fa-205">XML-CDATA-Literal</span><span class="sxs-lookup"><span data-stu-id="bd5fa-205">XML CDATA Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md)  
 [<span data-ttu-id="bd5fa-206">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="bd5fa-206">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="bd5fa-207">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd5fa-207">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="bd5fa-208">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="bd5fa-208">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="bd5fa-209">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-209">Imports Statement (XML Namespace)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)
