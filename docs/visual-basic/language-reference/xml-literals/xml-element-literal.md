---
title: XML-Elementliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralElement
dev_langs:
- VB
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
caps.latest.revision: 32
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
ms.openlocfilehash: d5cf769a1e3f668652d1eb4551058deba38a8acf
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="afb39-102">XML-Elementliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="afb39-102">XML Element Literal (Visual Basic)</span></span>
<span data-ttu-id="afb39-103">Ein Literal, das stellt ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="afb39-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afb39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afb39-104">Syntax</span></span>  
  
```  
<name [ attributeList ] />  
-or-  
<name [ attributeList ] > [ elementContents ] </[ name ]>  
```  
  
## <a name="parts"></a><span data-ttu-id="afb39-105">Teile</span><span class="sxs-lookup"><span data-stu-id="afb39-105">Parts</span></span>  
  
-   `<`  
  
     <span data-ttu-id="afb39-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afb39-106">Required.</span></span> <span data-ttu-id="afb39-107">Öffnet das Startkennzeichen-Element.</span><span class="sxs-lookup"><span data-stu-id="afb39-107">Opens the starting element tag.</span></span>  
  
-   `name`  
  
     <span data-ttu-id="afb39-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afb39-108">Required.</span></span> <span data-ttu-id="afb39-109">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="afb39-109">Name of the element.</span></span> <span data-ttu-id="afb39-110">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="afb39-110">The format is one of the following:</span></span>  
  
    -   <span data-ttu-id="afb39-111">Literaltext für den Elementnamen in der Form [`ePrefix``:`]`eName`, wobei:</span><span class="sxs-lookup"><span data-stu-id="afb39-111">Literal text for the element name, of the form [`ePrefix``:`]`eName`, where:</span></span>  
  
        |<span data-ttu-id="afb39-112">Segment</span><span class="sxs-lookup"><span data-stu-id="afb39-112">Part</span></span>|<span data-ttu-id="afb39-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afb39-113">Description</span></span>|  
        |---|---|  
        |`ePrefix`|<span data-ttu-id="afb39-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-114">Optional.</span></span> <span data-ttu-id="afb39-115">XML-Namespacepräfix für das Element.</span><span class="sxs-lookup"><span data-stu-id="afb39-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="afb39-116">Muss ein globaler XML-Namespace, die mit definiert ist eine `Imports` -Anweisung in der Datei oder auf Projektebene oder ein lokaler XML‑Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="afb39-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`eName`|<span data-ttu-id="afb39-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afb39-117">Required.</span></span> <span data-ttu-id="afb39-118">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="afb39-118">Name of the element.</span></span> <span data-ttu-id="afb39-119">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="afb39-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="afb39-120">-Literaltext.</span><span class="sxs-lookup"><span data-stu-id="afb39-120">-   Literal text.</span></span> <span data-ttu-id="afb39-121">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-121">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="afb39-122">-Eingebetteter Ausdruck der Form `<%=` e`NameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-122">-   Embedded expression of the form `<%=` e`NameExp` `%>`.</span></span> <span data-ttu-id="afb39-123">Der Typ des `eNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="afb39-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
  
    -   <span data-ttu-id="afb39-124">Eingebetteter Ausdruck der Form `<%=` `nameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-124">Embedded expression of the form `<%=` `nameExp` `%>`.</span></span> <span data-ttu-id="afb39-125">Der Typ des `nameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="afb39-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="afb39-126">Ein eingebetteter Ausdruck wird in ein Endtag eines Elements nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="afb39-126">An embedded expression is not allowed in a closing tag of an element.</span></span>  
  
-   `attributeList`  
  
     <span data-ttu-id="afb39-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-127">Optional.</span></span> <span data-ttu-id="afb39-128">Liste der Attribute, die in das Literal deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="afb39-128">List of attributes declared in the literal.</span></span>  
  
     `attribute [ attribute ... ]`  
  
     <span data-ttu-id="afb39-129">Jede `attribute` verfügt über einen der folgenden Syntaxformen:</span><span class="sxs-lookup"><span data-stu-id="afb39-129">Each `attribute` has one of the following syntaxes:</span></span>  
  
    -   <span data-ttu-id="afb39-130">-Attributzuweisung des Formulars [`aPrefix``:`]`aName``=``aValue`, wobei:</span><span class="sxs-lookup"><span data-stu-id="afb39-130">Attribute assignment, of the form [`aPrefix``:`]`aName``=``aValue`, where:</span></span>  
  
        |<span data-ttu-id="afb39-131">Segment</span><span class="sxs-lookup"><span data-stu-id="afb39-131">Part</span></span>|<span data-ttu-id="afb39-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="afb39-132">Description</span></span>|  
        |---|---|  
        |`aPrefix`|<span data-ttu-id="afb39-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-133">Optional.</span></span> <span data-ttu-id="afb39-134">XML-Namespacepräfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="afb39-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="afb39-135">Muss ein globaler XML-Namespace, die mit definiert ist ein `Imports` -Anweisung oder ein lokaler XML‑Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="afb39-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|  
        |`aName`|<span data-ttu-id="afb39-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afb39-136">Required.</span></span> <span data-ttu-id="afb39-137">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="afb39-137">Name of the attribute.</span></span> <span data-ttu-id="afb39-138">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="afb39-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="afb39-139">-Literaltext.</span><span class="sxs-lookup"><span data-stu-id="afb39-139">-   Literal text.</span></span> <span data-ttu-id="afb39-140">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-140">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="afb39-141">-Eingebetteter Ausdruck der Form `<%=` `aNameExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-141">-   Embedded expression of the form `<%=` `aNameExp` `%>`.</span></span> <span data-ttu-id="afb39-142">Der Typ des `aNameExp` muss `String` oder ein Typ, der implizit in <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="afb39-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|  
        |`aValue`|<span data-ttu-id="afb39-143">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-143">Optional.</span></span> <span data-ttu-id="afb39-144">Der Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="afb39-144">Value of the attribute.</span></span> <span data-ttu-id="afb39-145">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="afb39-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="afb39-146">-Literalen Text in Anführungszeichen eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="afb39-146">-   Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="afb39-147">-Eingebetteter Ausdruck der Form `<%=` `aValueExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-147">-   Embedded expression of the form `<%=` `aValueExp` `%>`.</span></span> <span data-ttu-id="afb39-148">Jeder Typ ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="afb39-148">Any type is allowed.</span></span>|  
  
    -   <span data-ttu-id="afb39-149">Eingebetteter Ausdruck der Form `<%=` `aExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-149">Embedded expression of the form `<%=` `aExp` `%>`.</span></span>  
  
-   `/>`  
  
     <span data-ttu-id="afb39-150">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-150">Optional.</span></span> <span data-ttu-id="afb39-151">Gibt an, dass das Element ein leeres Element ohne Inhalt.</span><span class="sxs-lookup"><span data-stu-id="afb39-151">Indicates that the element is an empty element, without content.</span></span>  
  
-   `>`  
  
     <span data-ttu-id="afb39-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="afb39-152">Required.</span></span> <span data-ttu-id="afb39-153">Beendet das Elementtag ab oder leer.</span><span class="sxs-lookup"><span data-stu-id="afb39-153">Ends the beginning or empty element tag.</span></span>  
  
-   `elementContents`  
  
     <span data-ttu-id="afb39-154">Optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-154">Optional.</span></span> <span data-ttu-id="afb39-155">Der Inhalt des Elements.</span><span class="sxs-lookup"><span data-stu-id="afb39-155">Content of the element.</span></span>  
  
     `content [ content ... ]`  
  
     <span data-ttu-id="afb39-156">Jede `content` kann einer der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="afb39-156">Each `content` can be one of the following:</span></span>  
  
    -   <span data-ttu-id="afb39-157">Normaler Text.</span><span class="sxs-lookup"><span data-stu-id="afb39-157">Literal text.</span></span> <span data-ttu-id="afb39-158">Der gesamte Leerraum in `elementContents` wird bedeutend, wenn Literaltext vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="afb39-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>  
  
    -   <span data-ttu-id="afb39-159">Eingebetteter Ausdruck der Form `<%=` `contentExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="afb39-159">Embedded expression of the form `<%=` `contentExp` `%>`.</span></span>  
  
    -   <span data-ttu-id="afb39-160">XML-Elementliteral.</span><span class="sxs-lookup"><span data-stu-id="afb39-160">XML element literal.</span></span>  
  
    -   <span data-ttu-id="afb39-161">XML-Kommentarliteral.</span><span class="sxs-lookup"><span data-stu-id="afb39-161">XML comment literal.</span></span> <span data-ttu-id="afb39-162">Finden Sie unter [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-162">See [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>  
  
    -   <span data-ttu-id="afb39-163">XML-Verarbeitungsanweisungsliteral.</span><span class="sxs-lookup"><span data-stu-id="afb39-163">XML processing instruction literal.</span></span> <span data-ttu-id="afb39-164">Finden Sie unter [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-164">See [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span>  
  
    -   <span data-ttu-id="afb39-165">XML CDATA-literal.</span><span class="sxs-lookup"><span data-stu-id="afb39-165">XML CDATA literal.</span></span> <span data-ttu-id="afb39-166">Finden Sie unter [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-166">See [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md).</span></span>  
  
-   <span data-ttu-id="afb39-167">`</`[`name`]`>`</span><span class="sxs-lookup"><span data-stu-id="afb39-167">`</`[`name`]`>`</span></span>  
  
     <span data-ttu-id="afb39-168">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="afb39-168">Optional.</span></span> <span data-ttu-id="afb39-169">Stellt das Endtag für das Element dar.</span><span class="sxs-lookup"><span data-stu-id="afb39-169">Represents the closing tag for the element.</span></span> <span data-ttu-id="afb39-170">Das optionale `name` -Parameter ist nicht zulässig, wenn er für einen eingebetteten Ausdruck resultiert.</span><span class="sxs-lookup"><span data-stu-id="afb39-170">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="afb39-171">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="afb39-171">Return Value</span></span>  
 <span data-ttu-id="afb39-172">Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="afb39-172">An <xref:System.Xml.Linq.XElement> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afb39-173">Hinweise</span><span class="sxs-lookup"><span data-stu-id="afb39-173">Remarks</span></span>  
 <span data-ttu-id="afb39-174">Sie können die XML-Literale Syntax erstellen <xref:System.Xml.Linq.XElement>Objekte in Ihrem Code.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="afb39-174">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afb39-175">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="afb39-175">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="afb39-176">Dieses Feature können Sie Inhalt aus einem XML-Dokument kopieren und Einfügen direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="afb39-176">This feature enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="afb39-177">Eingebettete Ausdrücke der Form `<%=` `exp` `%>` ermöglichen es Ihnen, einem XML-Elementliteral dynamische Informationen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="afb39-177">Embedded expressions of the form `<%=` `exp` `%>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="afb39-178">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-178">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="afb39-179">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Elementliteral in Aufrufe an die <xref:System.Xml.Linq.XElement.%23ctor%2A>Konstruktor und, falls erforderlich, die <xref:System.Xml.Linq.XAttribute.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XAttribute.%23ctor%2A> </xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="afb39-179">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="afb39-180">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="afb39-180">XML Namespaces</span></span>  
 <span data-ttu-id="afb39-181">XML-Namespacepräfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus demselben Namespace oft in Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="afb39-181">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="afb39-182">Können Sie globale XML-Namespacepräfixe verwenden, die mit der `Imports` -Anweisung oder lokale Präfixe, die mit der `xmlns:``xmlPrefix`= "`xmlNamespace`" Attributsyntax.</span><span class="sxs-lookup"><span data-stu-id="afb39-182">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:``xmlPrefix`="`xmlNamespace`" attribute syntax.</span></span> <span data-ttu-id="afb39-183">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="afb39-183">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
 <span data-ttu-id="afb39-184">Gemäß den Bereichsregeln für XML-Namespaces haben lokale Präfixe Vorrang gegenüber globalen Präfixen.</span><span class="sxs-lookup"><span data-stu-id="afb39-184">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="afb39-185">Wenn ein XML-Literal einen XML-Namespace definiert sind, steht jedoch diesem Namespace nicht auf Ausdrücke, die in einem eingebetteten Ausdruck angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="afb39-185">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="afb39-186">Die eingebettete Ausdruck kann nur auf den globalen XML-Namespace zugreifen.</span><span class="sxs-lookup"><span data-stu-id="afb39-186">The embedded expression can access only the global XML namespace.</span></span>  
  
 <span data-ttu-id="afb39-187">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert jeden globalen XML-Namespace, die von einem XML-literal in eine lokale Namespacedefinition im generierten Code verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="afb39-187">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="afb39-188">Globale XML-Namespaces, die nicht verwendet werden, erscheinen nicht im generierten Code.</span><span class="sxs-lookup"><span data-stu-id="afb39-188">Global XML namespaces that are not used do not appear in the generated code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afb39-189">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afb39-189">Example</span></span>  
 <span data-ttu-id="afb39-190">Im folgenden Beispiel wird veranschaulicht, wie ein einfaches XML-Element zu erstellen, die zwei geschachtelte leere Elemente.</span><span class="sxs-lookup"><span data-stu-id="afb39-190">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>  
  
 <span data-ttu-id="afb39-191">[!code-vb[VbXMLSamples&20;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="afb39-191">[!code-vb[VbXMLSamples#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_1.vb)]</span></span>  
  
 <span data-ttu-id="afb39-192">Das Beispiel zeigt den folgenden Text.</span><span class="sxs-lookup"><span data-stu-id="afb39-192">The example displays the following text.</span></span> <span data-ttu-id="afb39-193">Beachten Sie, dass das Literal die Struktur der leeren Elemente beibehält.</span><span class="sxs-lookup"><span data-stu-id="afb39-193">Notice that the literal preserves the structure of the empty elements.</span></span>  
  
```  
<outer>  
  <inner1></inner1>  
  <inner2 />  
</outer>  
```  
  
## <a name="example"></a><span data-ttu-id="afb39-194">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afb39-194">Example</span></span>  
 <span data-ttu-id="afb39-195">Im folgende Beispiel wird das Verwenden von eingebetteter Ausdrücken erstellen Attribute und benennen ein Element veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="afb39-195">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>  
  
 <span data-ttu-id="afb39-196">[!code-vb[VbXMLSamples&21;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="afb39-196">[!code-vb[VbXMLSamples#21](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_2.vb)]</span></span>  
  
 <span data-ttu-id="afb39-197">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="afb39-197">This code displays the following text:</span></span>  
  
```  
<book isbn="1234" author="My Author" year="1999" title="My Book" />  
```  
  
## <a name="example"></a><span data-ttu-id="afb39-198">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afb39-198">Example</span></span>  
 <span data-ttu-id="afb39-199">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="afb39-199">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="afb39-200">Anschließend wird das Namespacepräfix verwendet, zum Erstellen von XML-Literalen und abschließende Form des Elements anzeigt.</span><span class="sxs-lookup"><span data-stu-id="afb39-200">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>  
  
 <span data-ttu-id="afb39-201">[!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="afb39-201">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-element-literal_3.vb)]</span></span>  
  
 <span data-ttu-id="afb39-202">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="afb39-202">This code displays the following text:</span></span>  
  
```  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="afb39-203">Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespaces in einer Präfixdefinition für den XML-Namespace konvertiert.</span><span class="sxs-lookup"><span data-stu-id="afb39-203">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="afb39-204">Die \<Ns:middle >-Element definiert das XML-Namespacepräfix für den \<Ns:inner1 > Element.</span><span class="sxs-lookup"><span data-stu-id="afb39-204">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="afb39-205">Allerdings die \<Ns:inner2 > Element verwendet die von der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="afb39-205">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afb39-206">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afb39-206">See Also</span></span>  
 <span data-ttu-id="afb39-207"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="afb39-207"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="afb39-208"> [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-208"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="afb39-209"> [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-209"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="afb39-210"> [XML-CDATA-Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-210"> [XML CDATA Literal](../../../visual-basic/language-reference/xml-literals/xml-cdata-literal.md) </span></span>  
<span data-ttu-id="afb39-211"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-211"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="afb39-212"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-212"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="afb39-213"> [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="afb39-213"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="afb39-214"> [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span><span class="sxs-lookup"><span data-stu-id="afb39-214"> [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)</span></span>
