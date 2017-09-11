---
title: Imports-Anweisung (XML-Namespace) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ImportsXmlns
dev_langs:
- VB
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
caps.latest.revision: 18
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
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 66ac2bd947328dab9df812709525b43fb27145ac
ms.contentlocale: de-de
ms.lasthandoff: 06/01/2017

---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="7654e-102">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="7654e-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="7654e-103">Importiert XML-Namespacepräfixe zur Verwendung in XML-Literale und XML-Achseneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7654e-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7654e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7654e-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="7654e-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7654e-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="7654e-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="7654e-106">Optional.</span></span> <span data-ttu-id="7654e-107">Die Zeichenfolge, die durch die XML-Elemente und Attribute erhalten `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="7654e-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="7654e-108">Wenn keine `xmlNamespacePrefix` wird angegeben, wird der importierten XML-Namespace der XML-Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="7654e-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="7654e-109">Ein gültiger XML-Bezeichner muss sein.</span><span class="sxs-lookup"><span data-stu-id="7654e-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="7654e-110">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7654e-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="7654e-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7654e-111">Required.</span></span> <span data-ttu-id="7654e-112">Die Zeichenfolge identifiziert den XML-Namespace importiert wird.</span><span class="sxs-lookup"><span data-stu-id="7654e-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7654e-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7654e-113">Remarks</span></span>  
 <span data-ttu-id="7654e-114">Sie können die `Imports` -Anweisung können Sie globale XML-Namespaces definieren, mit denen Sie mit XML-Literale und XML-Achseneigenschaften oder als Parameter für die `GetXmlNamespace` Operator.</span><span class="sxs-lookup"><span data-stu-id="7654e-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="7654e-115">(Informationen zur Verwendung der `Imports` Anweisung zum Importieren eines Alias, die verwendet werden können, in dem Typnamen in Ihrem Code sind finden Sie unter [Imports-Anweisung (.NET Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespaces mithilfe der `Imports` -Anweisung ist identisch mit der in XML verwendeten Syntax.</span><span class="sxs-lookup"><span data-stu-id="7654e-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="7654e-116">Daher können Sie eine Namespacedeklaration aus einer XML-Datei kopieren und verwenden Sie es in eine `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7654e-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="7654e-117">XML-Namespacepräfixe sind nützlich, wenn Sie wiederholt XML-Elemente erstellen, die aus demselben Namespace möchten.</span><span class="sxs-lookup"><span data-stu-id="7654e-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="7654e-118">Das XML-Namespacepräfix deklariert, mit der `Imports` Anweisung ist global, in dem Sinne, dass sie für den gesamten Code in der Datei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="7654e-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="7654e-119">Sie können es verwenden, wenn Sie XML-Element-Literalen und beim Zugriff auf XML-Achseneigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="7654e-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="7654e-120">Weitere Informationen finden Sie unter [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span><span class="sxs-lookup"><span data-stu-id="7654e-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md).</span></span>  
  
 <span data-ttu-id="7654e-121">Wenn Sie einen globalen XML-Namespace ohne einen Namespacepräfix definieren (z. B. `Imports <xmlns="http://SomeNameSpace>"`), dieser Namespace als den XML-Standardnamespace angesehen.</span><span class="sxs-lookup"><span data-stu-id="7654e-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="7654e-122">Für alle XML-Elementliterale oder XML-Attribut-Achseneigenschaften, mit die nicht explizit einen Namespace angegeben werden, wird der XML-Standardnamespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="7654e-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="7654e-123">Der Standardnamespace wird auch verwendet, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="7654e-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="7654e-124">Der XML-Standardnamespace gilt nicht, XML-Attributen in XML-Literalen oder XML-Attribut-Achseneigenschaften, mit die nicht mit einen Namespace verfügen.</span><span class="sxs-lookup"><span data-stu-id="7654e-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="7654e-125">XML-Namespaces, die in einem XML-literal definiert sind bezeichnet *lokale XML-Namespaces*, von definierten, XML-Namespaces haben Vorrang vor den `Imports` -Anweisung als global.</span><span class="sxs-lookup"><span data-stu-id="7654e-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="7654e-126">XML-Namespaces, die durch definiert sind die `Imports` Anweisung haben Vorrang vor XML-Namespaces, die für ein Visual Basic-Projekt importiert.</span><span class="sxs-lookup"><span data-stu-id="7654e-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="7654e-127">Wenn ein XML-Literal einen XML-Namespace definiert, gilt dieser lokale Namespace nicht für eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="7654e-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="7654e-128">Globale XML-Namespaces folgen denselben Regeln für Bereichs- und Definitionsregeln wie .NET Framework-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="7654e-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="7654e-129">Sie können daher einschließen einer `Imports` Anweisung, um einen globalen XML-Namespace definieren an können Sie einen .NET Framework-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="7654e-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="7654e-130">Dies schließt sowohl Codedateien und importierten Namespaces auf Projektebene.</span><span class="sxs-lookup"><span data-stu-id="7654e-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="7654e-131">Informationen über auf Projektebene importierte Namespaces finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="7654e-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="7654e-132">Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7654e-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="7654e-133">Diese müssen führen Sie die Option-Deklarationen, wie z. B. die `Option Strict` -Anweisung, und sie müssen Programmierung Elementdeklarationen, wie z. B. voranstellen `Module` oder `Class` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7654e-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7654e-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7654e-134">Example</span></span>  
 <span data-ttu-id="7654e-135">Das folgende Beispiel importiert eine XML-Standardnamespace und ein XML-Namespace mit dem Präfix identifiziert `ns`.</span><span class="sxs-lookup"><span data-stu-id="7654e-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="7654e-136">Anschließend erstellt Sie XML-Literale, die beide Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="7654e-136">It then creates XML literals that use both namespaces.</span></span>  
  
 <span data-ttu-id="7654e-137">[!code-vb[VbXMLSamples&#45;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7654e-137">[!code-vb[VbXMLSamples#45](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="7654e-138">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7654e-138">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="7654e-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7654e-139">Example</span></span>  
 <span data-ttu-id="7654e-140">Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`.</span><span class="sxs-lookup"><span data-stu-id="7654e-140">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="7654e-141">Anschließend erstellt Sie ein XML-literal, das das Namespacepräfix verwendet und die abschließende Form des Elements anzeigt.</span><span class="sxs-lookup"><span data-stu-id="7654e-141">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 <span data-ttu-id="7654e-142">[!code-vb[VbXMLSamples&#22;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7654e-142">[!code-vb[VbXMLSamples#22](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_2.vb)]</span></span>  
  
 <span data-ttu-id="7654e-143">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7654e-143">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="7654e-144">Beachten Sie, dass der Compiler das XML-Namespacepräfix aus dem globalen Präfix für die Definition einer standortlokalen Präfix konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7654e-144">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7654e-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7654e-145">Example</span></span>  
 <span data-ttu-id="7654e-146">Im folgende Beispiel wird das XML-Namespacepräfix importiert `ns`.</span><span class="sxs-lookup"><span data-stu-id="7654e-146">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="7654e-147">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="7654e-147">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="7654e-148">[!code-vb[VbXMLSamples Nr.&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="7654e-148">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/imports-statement-xml-namespace_3.vb)]</span></span>  
  
 <span data-ttu-id="7654e-149">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7654e-149">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="7654e-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7654e-150">See Also</span></span>  
 <span data-ttu-id="7654e-151">[XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="7654e-151">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="7654e-152"> [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="7654e-152"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="7654e-153"> [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="7654e-153"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md) </span></span>  
<span data-ttu-id="7654e-154"> [GetXmlNamespace-Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span><span class="sxs-lookup"><span data-stu-id="7654e-154"> [GetXmlNamespace Operator](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)</span></span>
