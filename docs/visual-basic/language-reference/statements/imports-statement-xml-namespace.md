---
title: Imports-Anweisung (XML-Namespace)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 52864e4d1c8183b6243025e72368d23627049c84
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351063"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="8ac50-102">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="8ac50-102">Imports Statement (XML Namespace)</span></span>

<span data-ttu-id="8ac50-103">Importiert XML-Namespace Präfixe zur Verwendung in XML-Literalen und XML-Achsen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8ac50-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ac50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ac50-104">Syntax</span></span>

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a><span data-ttu-id="8ac50-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="8ac50-105">Parts</span></span>

`xmlNamespacePrefix`  
<span data-ttu-id="8ac50-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="8ac50-106">Optional.</span></span> <span data-ttu-id="8ac50-107">Die Zeichenfolge, mit der XML-Elemente und-Attribute auf `xmlNamespaceName`verweisen können.</span><span class="sxs-lookup"><span data-stu-id="8ac50-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="8ac50-108">Wenn keine `xmlNamespacePrefix` angegeben wird, ist der importierte XML-Namespace der Standard-XML-Namespace.</span><span class="sxs-lookup"><span data-stu-id="8ac50-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="8ac50-109">Muss ein gültiger XML-Bezeichner sein.</span><span class="sxs-lookup"><span data-stu-id="8ac50-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="8ac50-110">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="8ac50-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>

`xmlNamespaceName`  
<span data-ttu-id="8ac50-111">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="8ac50-111">Required.</span></span> <span data-ttu-id="8ac50-112">Die Zeichenfolge, die den importierten XML-Namespace identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8ac50-112">The string identifying the XML namespace being imported.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ac50-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ac50-113">Remarks</span></span>

<span data-ttu-id="8ac50-114">Sie können die `Imports`-Anweisung verwenden, um globale XML-Namespaces zu definieren, die Sie mit XML-Literalen und XML-Achsen Eigenschaften verwenden können, oder als Parameter, die an den `GetXmlNamespace` Operator weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="8ac50-115">(Informationen zur Verwendung der `Imports`-Anweisung zum Importieren eines Alias, der verwendet werden kann, wo Typnamen in Ihrem Code verwendet werden, finden Sie unter [Imports-Anweisung (.NET-Namespace und-Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespace mit der `Imports`-Anweisung ist identisch mit der Syntax, die in XML verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ac50-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="8ac50-116">Daher können Sie eine Namespace Deklaration aus einer XML-Datei kopieren und in einer `Imports`-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>

<span data-ttu-id="8ac50-117">XML-Namespace Präfixe sind nützlich, wenn Sie wiederholt XML-Elemente aus demselben Namespace erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ac50-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="8ac50-118">Das mit der `Imports`-Anweisung deklarierte XML-Namespace Präfix ist in dem Sinne Global, dass es für den gesamten Code in der Datei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8ac50-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="8ac50-119">Sie können Sie verwenden, wenn Sie XML-Element Literale erstellen und auf XML-Achsen Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8ac50-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="8ac50-120">Weitere Informationen finden Sie unter [XML-Elementliterale](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achsen Eigenschaften](../../../visual-basic/language-reference/xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ac50-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>

<span data-ttu-id="8ac50-121">Wenn Sie einen globalen XML-Namespace ohne Namespace Präfix (z. b. `Imports <xmlns="http://SomeNameSpace>"`) definieren, wird dieser Namespace als Standard-XML-Namespace betrachtet.</span><span class="sxs-lookup"><span data-stu-id="8ac50-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="8ac50-122">Der Standard-XML-Namespace wird für alle XML-Element Literale oder XML-Attribut Achsen Eigenschaften verwendet, die nicht explizit einen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="8ac50-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="8ac50-123">Der Standard Namespace wird auch verwendet, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="8ac50-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="8ac50-124">Der Standard-XML-Namespace gilt nicht für XML-Attribute in XML-Literalen oder XML-Attribut Achsen Eigenschaften, die keinen Namespace aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8ac50-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>

<span data-ttu-id="8ac50-125">XML-Namespaces, die in einem XML-Literaltyp definiert sind, die als *lokale XML-Namespaces*bezeichnet werden, haben Vorrang vor XML-Namespaces, die von der `Imports`-Anweisung als Global definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="8ac50-126">XML-Namespaces, die durch die `Imports`-Anweisung definiert werden, haben Vorrang vor XML-Namespaces, die für ein Visual Basic Projekt importiert werden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="8ac50-127">Wenn ein XML-Literale einen XML-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="8ac50-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>

<span data-ttu-id="8ac50-128">Globale XML-Namespaces befolgen dieselben Bereichs-und Definitions Regeln wie .NET Framework Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8ac50-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="8ac50-129">Daher können Sie eine `Imports`-Anweisung einschließen, um einen globalen XML-Namespace zu definieren, wo Sie einen .NET Framework Namespace importieren können.</span><span class="sxs-lookup"><span data-stu-id="8ac50-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="8ac50-130">Dies gilt sowohl für Code Dateien als auch für importierte Namespaces auf Projektebene.</span><span class="sxs-lookup"><span data-stu-id="8ac50-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="8ac50-131">Weitere Informationen zu importierten Namespaces auf Projektebene finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="8ac50-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="8ac50-132">Jede Quelldatei kann eine beliebige Anzahl von `Imports`-Anweisungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ac50-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="8ac50-133">Diese müssen auf Options Deklarationen folgen, wie z. b. die `Option Strict`-Anweisung, und Sie müssen vor Programmierungs Element Deklarationen wie `Module` oder `Class`-Anweisungen stehen.</span><span class="sxs-lookup"><span data-stu-id="8ac50-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>

## <a name="example"></a><span data-ttu-id="8ac50-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ac50-134">Example</span></span>

<span data-ttu-id="8ac50-135">Im folgenden Beispiel werden ein Standard-XML-Namespace und ein XML-Namespace importiert, die mit dem Präfix `ns`identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="8ac50-136">Anschließend werden XML-Literale erstellt, die beide Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ac50-136">It then creates XML literals that use both namespaces.</span></span>

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

<span data-ttu-id="8ac50-137">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8ac50-137">This code displays the following text:</span></span>

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a><span data-ttu-id="8ac50-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ac50-138">Example</span></span>

<span data-ttu-id="8ac50-139">Im folgenden Beispiel wird das XML-Namespace Präfix `ns`importiert.</span><span class="sxs-lookup"><span data-stu-id="8ac50-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="8ac50-140">Anschließend wird ein XML-wahrsten erstellt, das das Namespace Präfix verwendet und die endgültige Form des Elements anzeigt.</span><span class="sxs-lookup"><span data-stu-id="8ac50-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

<span data-ttu-id="8ac50-141">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8ac50-141">This code displays the following text:</span></span>

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

<span data-ttu-id="8ac50-142">Beachten Sie, dass der Compiler das XML-Namespace Präfix aus einem globalen Präfix in eine lokale Präfix Definition konvertiert hat.</span><span class="sxs-lookup"><span data-stu-id="8ac50-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>

## <a name="example"></a><span data-ttu-id="8ac50-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ac50-143">Example</span></span>

<span data-ttu-id="8ac50-144">Im folgenden Beispiel wird das XML-Namespace Präfix `ns`importiert.</span><span class="sxs-lookup"><span data-stu-id="8ac50-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="8ac50-145">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="8ac50-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

<span data-ttu-id="8ac50-146">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8ac50-146">This code displays the following text:</span></span>

`Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="8ac50-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ac50-147">See also</span></span>

- [<span data-ttu-id="8ac50-148">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="8ac50-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="8ac50-149">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8ac50-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="8ac50-150">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="8ac50-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="8ac50-151">GetXmlNamespace-Operator</span><span class="sxs-lookup"><span data-stu-id="8ac50-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
