---
title: XML-Elementliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralElement
helpviewer_keywords:
- XML element literal [Visual Basic]
- element literal [Visual Basic]
- XML literals [Visual Basic], element
ms.assetid: 95039642-7893-48b7-b23f-45a6c55d8f67
ms.openlocfilehash: d6a91de4e279816bafd29f46bb4f5422cbd934ff
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400188"
---
# <a name="xml-element-literal-visual-basic"></a><span data-ttu-id="fa680-102">XML-Elementliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa680-102">XML Element Literal (Visual Basic)</span></span>

<span data-ttu-id="fa680-103">Ein Literalwert, der ein <xref:System.Xml.Linq.XElement> Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="fa680-103">A literal that represents an <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa680-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa680-104">Syntax</span></span>

```xml
<name [ attributeList ] />
-or-
<name [ attributeList ] > [ elementContents ] </[ name ]>
```

## <a name="parts"></a><span data-ttu-id="fa680-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="fa680-105">Parts</span></span>

- `<`

  <span data-ttu-id="fa680-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa680-106">Required.</span></span> <span data-ttu-id="fa680-107">Öffnet das Startelementtag.</span><span class="sxs-lookup"><span data-stu-id="fa680-107">Opens the starting element tag.</span></span>

- `name`

  <span data-ttu-id="fa680-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa680-108">Required.</span></span> <span data-ttu-id="fa680-109">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="fa680-109">Name of the element.</span></span> <span data-ttu-id="fa680-110">Das Format ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="fa680-110">The format is one of the following:</span></span>

  - <span data-ttu-id="fa680-111">Literaltext für den Elementnamen der Form `[ePrefix:]eName` , wobei Folgendes gilt:</span><span class="sxs-lookup"><span data-stu-id="fa680-111">Literal text for the element name, of the form `[ePrefix:]eName`, where:</span></span>

    |<span data-ttu-id="fa680-112">Teil</span><span class="sxs-lookup"><span data-stu-id="fa680-112">Part</span></span>|<span data-ttu-id="fa680-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa680-113">Description</span></span>|
    |---|---|
    |`ePrefix`|<span data-ttu-id="fa680-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-114">Optional.</span></span> <span data-ttu-id="fa680-115">Das XML-Namespace Präfix für das Element.</span><span class="sxs-lookup"><span data-stu-id="fa680-115">XML namespace prefix for the element.</span></span> <span data-ttu-id="fa680-116">Muss ein globaler XML-Namespace sein, der mit einer- `Imports` Anweisung in der Datei oder auf Projektebene definiert ist, oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fa680-116">Must be a global XML namespace that is defined with an `Imports` statement in the file or at the project level, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`eName`|<span data-ttu-id="fa680-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa680-117">Required.</span></span> <span data-ttu-id="fa680-118">Name des Elements.</span><span class="sxs-lookup"><span data-stu-id="fa680-118">Name of the element.</span></span> <span data-ttu-id="fa680-119">Das Format ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="fa680-119">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="fa680-120">-LiteralText.</span><span class="sxs-lookup"><span data-stu-id="fa680-120">- Literal text.</span></span> <span data-ttu-id="fa680-121">Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-121">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="fa680-122">-Eingebetteter Ausdruck des Formulars `<%= eNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-122">- Embedded expression of the form `<%= eNameExp %>`.</span></span> <span data-ttu-id="fa680-123">Der Typ von `eNameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="fa680-123">The type of `eNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|

  - <span data-ttu-id="fa680-124">Eingebetteter Ausdruck des Formulars `<%= nameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-124">Embedded expression of the form `<%= nameExp %>`.</span></span> <span data-ttu-id="fa680-125">Der Typ von `nameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="fa680-125">The type of `nameExp` must be `String` or a type implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span> <span data-ttu-id="fa680-126">Ein eingebetteter Ausdruck ist in einem schließenden Tag eines Elements nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="fa680-126">An embedded expression is not allowed in a closing tag of an element.</span></span>

- `attributeList`

  <span data-ttu-id="fa680-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-127">Optional.</span></span> <span data-ttu-id="fa680-128">Die Liste der im Literalformat deklarierten Attribute.</span><span class="sxs-lookup"><span data-stu-id="fa680-128">List of attributes declared in the literal.</span></span>

  `attribute [ attribute ... ]`

  <span data-ttu-id="fa680-129">Jede `attribute` verfügt über eine der folgenden Syntaxen:</span><span class="sxs-lookup"><span data-stu-id="fa680-129">Each `attribute` has one of the following syntaxes:</span></span>

  - <span data-ttu-id="fa680-130">Attribut Zuweisung im Format `[aPrefix:]aName=aValue` , wobei:</span><span class="sxs-lookup"><span data-stu-id="fa680-130">Attribute assignment, of the form `[aPrefix:]aName=aValue`, where:</span></span>

    |<span data-ttu-id="fa680-131">Teil</span><span class="sxs-lookup"><span data-stu-id="fa680-131">Part</span></span>|<span data-ttu-id="fa680-132">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa680-132">Description</span></span>|
    |---|---|
    |`aPrefix`|<span data-ttu-id="fa680-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-133">Optional.</span></span> <span data-ttu-id="fa680-134">Das XML-Namespace Präfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="fa680-134">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="fa680-135">Muss ein globaler XML-Namespace sein, der mit einer-Anweisung definiert ist `Imports` , oder ein lokaler XML-Namespace, der in diesem Element oder einem übergeordneten Element definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fa680-135">Must be a global XML namespace that is defined with an `Imports` statement, or a local XML namespace that is defined in this element or a parent element.</span></span>|
    |`aName`|<span data-ttu-id="fa680-136">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa680-136">Required.</span></span> <span data-ttu-id="fa680-137">Der Name des Attributs.</span><span class="sxs-lookup"><span data-stu-id="fa680-137">Name of the attribute.</span></span> <span data-ttu-id="fa680-138">Das Format ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="fa680-138">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="fa680-139">-LiteralText.</span><span class="sxs-lookup"><span data-stu-id="fa680-139">- Literal text.</span></span> <span data-ttu-id="fa680-140">Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-140">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span><br /><span data-ttu-id="fa680-141">-Eingebetteter Ausdruck des Formulars `<%= aNameExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-141">- Embedded expression of the form `<%= aNameExp %>`.</span></span> <span data-ttu-id="fa680-142">Der Typ von `aNameExp` muss `String` oder ein Typ sein, der implizit in konvertierbar ist <xref:System.Xml.Linq.XName> .</span><span class="sxs-lookup"><span data-stu-id="fa680-142">The type of `aNameExp` must be `String` or a type that is implicitly convertible to <xref:System.Xml.Linq.XName>.</span></span>|
    |`aValue`|<span data-ttu-id="fa680-143">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-143">Optional.</span></span> <span data-ttu-id="fa680-144">Der Wert des Attributs.</span><span class="sxs-lookup"><span data-stu-id="fa680-144">Value of the attribute.</span></span> <span data-ttu-id="fa680-145">Das Format ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="fa680-145">The format is one of the following:</span></span><br /><br /> <span data-ttu-id="fa680-146">-Literaler Text, der in Anführungszeichen eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fa680-146">- Literal text, enclosed in quotation marks.</span></span><br /><span data-ttu-id="fa680-147">-Eingebetteter Ausdruck des Formulars `<%= aValueExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-147">- Embedded expression of the form `<%= aValueExp %>`.</span></span> <span data-ttu-id="fa680-148">Jeder Typ ist zulässig.</span><span class="sxs-lookup"><span data-stu-id="fa680-148">Any type is allowed.</span></span>|

  - <span data-ttu-id="fa680-149">Eingebetteter Ausdruck des Formulars `<%= aExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-149">Embedded expression of the form `<%= aExp %>`.</span></span>

- `/>`

  <span data-ttu-id="fa680-150">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-150">Optional.</span></span> <span data-ttu-id="fa680-151">Gibt an, dass das Element ein leeres Element ohne Inhalt ist.</span><span class="sxs-lookup"><span data-stu-id="fa680-151">Indicates that the element is an empty element, without content.</span></span>

- `>`

  <span data-ttu-id="fa680-152">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fa680-152">Required.</span></span> <span data-ttu-id="fa680-153">Beendet den Anfang oder das leere Elementtag.</span><span class="sxs-lookup"><span data-stu-id="fa680-153">Ends the beginning or empty element tag.</span></span>

- `elementContents`

  <span data-ttu-id="fa680-154">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-154">Optional.</span></span> <span data-ttu-id="fa680-155">Der Inhalt des Elements.</span><span class="sxs-lookup"><span data-stu-id="fa680-155">Content of the element.</span></span>

  `content [ content ... ]`

  <span data-ttu-id="fa680-156">Dabei kann es sich um `content` einen der folgenden handeln:</span><span class="sxs-lookup"><span data-stu-id="fa680-156">Each `content` can be one of the following:</span></span>

  - <span data-ttu-id="fa680-157">LiteralText.</span><span class="sxs-lookup"><span data-stu-id="fa680-157">Literal text.</span></span> <span data-ttu-id="fa680-158">Alle Leerzeichen in `elementContents` werden signifikant, wenn Literaltext vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fa680-158">All the white space in `elementContents` becomes significant if there is any literal text.</span></span>

  - <span data-ttu-id="fa680-159">Eingebetteter Ausdruck des Formulars `<%= contentExp %>` .</span><span class="sxs-lookup"><span data-stu-id="fa680-159">Embedded expression of the form `<%= contentExp %>`.</span></span>

  - <span data-ttu-id="fa680-160">XML-Elementliterale.</span><span class="sxs-lookup"><span data-stu-id="fa680-160">XML element literal.</span></span>

  - <span data-ttu-id="fa680-161">XML-Kommentarliteral.</span><span class="sxs-lookup"><span data-stu-id="fa680-161">XML comment literal.</span></span> <span data-ttu-id="fa680-162">Siehe [XML comment Literal.](xml-comment-literal.md)</span><span class="sxs-lookup"><span data-stu-id="fa680-162">See [XML Comment Literal](xml-comment-literal.md).</span></span>

  - <span data-ttu-id="fa680-163">XML-Verarbeitungs Anweisungs Literale.</span><span class="sxs-lookup"><span data-stu-id="fa680-163">XML processing instruction literal.</span></span> <span data-ttu-id="fa680-164">Siehe [XML Processing Instruction Literale](xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-164">See [XML Processing Instruction Literal](xml-processing-instruction-literal.md).</span></span>

  - <span data-ttu-id="fa680-165">XML-CDATA-Literale.</span><span class="sxs-lookup"><span data-stu-id="fa680-165">XML CDATA literal.</span></span> <span data-ttu-id="fa680-166">Siehe [XML-CDATA-Literale](xml-cdata-literal.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-166">See [XML CDATA Literal](xml-cdata-literal.md).</span></span>

- `</[name]>`

  <span data-ttu-id="fa680-167">Optional.</span><span class="sxs-lookup"><span data-stu-id="fa680-167">Optional.</span></span> <span data-ttu-id="fa680-168">Stellt das Endtag für das Element dar.</span><span class="sxs-lookup"><span data-stu-id="fa680-168">Represents the closing tag for the element.</span></span> <span data-ttu-id="fa680-169">Der optionale- `name` Parameter ist nicht zulässig, wenn es sich um das Ergebnis eines eingebetteten Ausdrucks handelt.</span><span class="sxs-lookup"><span data-stu-id="fa680-169">The optional `name` parameter is not allowed when it is the result of an embedded expression.</span></span>

## <a name="return-value"></a><span data-ttu-id="fa680-170">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa680-170">Return Value</span></span>

<span data-ttu-id="fa680-171">Ein <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="fa680-171">An <xref:System.Xml.Linq.XElement> object.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa680-172">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fa680-172">Remarks</span></span>

<span data-ttu-id="fa680-173">Sie können die Literalsyntax des XML-Elements verwenden, um- <xref:System.Xml.Linq.XElement> Objekte in Ihrem Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa680-173">You can use the XML element literal syntax to create <xref:System.Xml.Linq.XElement> objects in your code.</span></span>

> [!NOTE]
> <span data-ttu-id="fa680-174">Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa680-174">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="fa680-175">Mit dieser Funktion können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.</span><span class="sxs-lookup"><span data-stu-id="fa680-175">This feature enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>

<span data-ttu-id="fa680-176">Mit eingebetteten Ausdrücken des Formulars `<%= exp %>` können Sie einem XML-Elementliteral dynamische Informationen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa680-176">Embedded expressions of the form `<%= exp %>` enable you to add dynamic information to an XML element literal.</span></span> <span data-ttu-id="fa680-177">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-177">For more information, see [Embedded Expressions in XML](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>

<span data-ttu-id="fa680-178">Der Visual Basic Compiler konvertiert das XML-Elementliteral in Aufrufe des <xref:System.Xml.Linq.XElement.%23ctor%2A> Konstruktors und, falls erforderlich, den <xref:System.Xml.Linq.XAttribute.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="fa680-178">The Visual Basic compiler converts the XML element literal into calls to the <xref:System.Xml.Linq.XElement.%23ctor%2A> constructor and, if it is required, the <xref:System.Xml.Linq.XAttribute.%23ctor%2A> constructor.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="fa680-179">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="fa680-179">XML Namespaces</span></span>

<span data-ttu-id="fa680-180">XML-Namespace Präfixe sind nützlich, wenn Sie XML-Literale mit Elementen aus dem gleichen Namespace mehrmals im Code erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="fa680-180">XML namespace prefixes are useful when you have to create XML literals with elements from the same namespace many times in code.</span></span> <span data-ttu-id="fa680-181">Sie können globale XML-Namespace Präfixe verwenden, die Sie mithilfe der- `Imports` Anweisung definieren, oder lokale Präfixe, die Sie mithilfe der- `xmlns:xmlPrefix="xmlNamespace"` Attribut Syntax definieren.</span><span class="sxs-lookup"><span data-stu-id="fa680-181">You can use global XML namespace prefixes, which you define by using the `Imports` statement, or local prefixes, which you define by using the `xmlns:xmlPrefix="xmlNamespace"` attribute syntax.</span></span> <span data-ttu-id="fa680-182">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="fa680-182">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>

<span data-ttu-id="fa680-183">In Übereinstimmung mit den Bereichs Regeln für XML-Namespaces haben lokale Präfixe Vorrang vor globalen Präfixen.</span><span class="sxs-lookup"><span data-stu-id="fa680-183">In accordance with the scoping rules for XML namespaces, local prefixes take precedence over global prefixes.</span></span> <span data-ttu-id="fa680-184">Wenn ein XML-Literale jedoch einen XML-Namespace definiert, ist dieser Namespace für Ausdrücke, die in einem eingebetteten Ausdruck vorkommen, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fa680-184">However, if an XML literal defines an XML namespace, that namespace is not available to expressions that appear in an embedded expression.</span></span> <span data-ttu-id="fa680-185">Der eingebettete Ausdruck kann nur auf den globalen XML-Namespace zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fa680-185">The embedded expression can access only the global XML namespace.</span></span>

<span data-ttu-id="fa680-186">Der Visual Basic Compiler konvertiert jeden globalen XML-Namespace, der von einem XML-Literalwert verwendet wird, in eine lokale Namespace Definition im generierten Code.</span><span class="sxs-lookup"><span data-stu-id="fa680-186">The Visual Basic compiler converts each global XML namespace that is used by an XML literal into a one local namespace definition in the generated code.</span></span> <span data-ttu-id="fa680-187">Globale XML-Namespaces, die nicht verwendet werden, werden im generierten Code nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa680-187">Global XML namespaces that are not used do not appear in the generated code.</span></span>

## <a name="example"></a><span data-ttu-id="fa680-188">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa680-188">Example</span></span>

<span data-ttu-id="fa680-189">Im folgenden Beispiel wird gezeigt, wie ein einfaches XML-Element erstellt wird, das über zwei in der Tabelle leere Elemente verfügt.</span><span class="sxs-lookup"><span data-stu-id="fa680-189">The following example shows how to create a simple XML element that has two nested empty elements.</span></span>

[!code-vb[VbXMLSamples#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#20)]

<span data-ttu-id="fa680-190">Im Beispiel wird der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa680-190">The example displays the following text.</span></span> <span data-ttu-id="fa680-191">Beachten Sie, dass das Literale die Struktur der leeren Elemente beibehält.</span><span class="sxs-lookup"><span data-stu-id="fa680-191">Notice that the literal preserves the structure of the empty elements.</span></span>

```xml
<outer>
  <inner1></inner1>
  <inner2 />
</outer>
```

## <a name="example"></a><span data-ttu-id="fa680-192">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa680-192">Example</span></span>

<span data-ttu-id="fa680-193">Im folgenden Beispiel wird gezeigt, wie eingebettete Ausdrücke verwendet werden, um ein Element zu benennen und Attribute zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa680-193">The following example shows how to use embedded expressions to name an element and create attributes.</span></span>

[!code-vb[VbXMLSamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples9.vb#21)]

<span data-ttu-id="fa680-194">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fa680-194">This code displays the following text:</span></span>

```xml
<book isbn="1234" author="My Author" year="1999" title="My Book" />
```

## <a name="example"></a><span data-ttu-id="fa680-195">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa680-195">Example</span></span>

<span data-ttu-id="fa680-196">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="fa680-196">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="fa680-197">Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalformat zu erstellen, und zeigt die endgültige Form des Elements an.</span><span class="sxs-lookup"><span data-stu-id="fa680-197">It then uses the prefix of the namespace to create an XML literal and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="fa680-198">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fa680-198">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="fa680-199">Beachten Sie, dass der Compiler das Präfix des globalen XML-Namespace in eine Präfix Definition für den XML-Namespace konvertiert hat.</span><span class="sxs-lookup"><span data-stu-id="fa680-199">Notice that the compiler converted the prefix of the global XML namespace into a prefix definition for the XML namespace.</span></span> <span data-ttu-id="fa680-200">Das- \<ns:middle> Element definiert das XML-Namespace Präfix für das \<ns:inner1> Element neu.</span><span class="sxs-lookup"><span data-stu-id="fa680-200">The \<ns:middle> element redefines the XML namespace prefix for the \<ns:inner1> element.</span></span> <span data-ttu-id="fa680-201">Das- \<ns:inner2> Element verwendet jedoch den Namespace, der durch die-Anweisung definiert wird `Imports` .</span><span class="sxs-lookup"><span data-stu-id="fa680-201">However, the \<ns:inner2> element uses the namespace defined by the `Imports` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa680-202">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa680-202">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="fa680-203">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="fa680-203">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="fa680-204">XML-Kommentarliteral</span><span class="sxs-lookup"><span data-stu-id="fa680-204">XML Comment Literal</span></span>](xml-comment-literal.md)
- [<span data-ttu-id="fa680-205">XML-CDATA-Literal</span><span class="sxs-lookup"><span data-stu-id="fa680-205">XML CDATA Literal</span></span>](xml-cdata-literal.md)
- [<span data-ttu-id="fa680-206">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="fa680-206">XML Literals</span></span>](index.md)
- [<span data-ttu-id="fa680-207">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa680-207">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="fa680-208">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="fa680-208">Embedded Expressions in XML</span></span>](../../programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [<span data-ttu-id="fa680-209">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="fa680-209">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
