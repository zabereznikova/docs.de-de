---
title: XML-Dokumentliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralDocument
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
ms.openlocfilehash: bd2ecfb93cfcdb7cf9c115f9a44ac47dd74c4b53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="4e8d5-102">XML-Dokumentliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e8d5-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="4e8d5-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XDocument> Objekt.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e8d5-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4e8d5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4e8d5-105">Parts</span></span>  
  
|<span data-ttu-id="4e8d5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4e8d5-106">Term</span></span>|<span data-ttu-id="4e8d5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4e8d5-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="4e8d5-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-108">Optional.</span></span> <span data-ttu-id="4e8d5-109">Literaltext deklarieren, welche Codierung des Dokuments verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="4e8d5-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-110">Optional.</span></span> <span data-ttu-id="4e8d5-111">Literaltext.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-111">Literal text.</span></span> <span data-ttu-id="4e8d5-112">Muss "yes" oder "no".</span><span class="sxs-lookup"><span data-stu-id="4e8d5-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="4e8d5-113">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-113">Optional.</span></span> <span data-ttu-id="4e8d5-114">Liste der XML-verarbeitungsanweisungen und XML-Kommentare.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="4e8d5-115">Weist das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="4e8d5-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="4e8d5-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="4e8d5-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="4e8d5-117">Jede `piComment` kann eines der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="4e8d5-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="4e8d5-118">-   [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d5-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="4e8d5-119">-   [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="4e8d5-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-120">Required.</span></span> <span data-ttu-id="4e8d5-121">Das Stammelement des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-121">Root element of the document.</span></span> <span data-ttu-id="4e8d5-122">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4e8d5-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4e8d5-123">[XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="4e8d5-124">Eingebetteter Ausdruck der Form `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="4e8d5-125">Die `elementExp` gibt einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="4e8d5-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="4e8d5-126">Ein <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="4e8d5-127">Eine Auflistung, die einen enthält <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction> und <xref:System.Xml.Linq.XComment> Objekte.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="4e8d5-128">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="4e8d5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="4e8d5-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e8d5-129">Return Value</span></span>  
 <span data-ttu-id="4e8d5-130">Ein <xref:System.Xml.Linq.XDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e8d5-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e8d5-131">Remarks</span></span>  
 <span data-ttu-id="4e8d5-132">Ein XML-Dokumentliteral wird durch die XML-Deklaration zu Beginn des Literals identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="4e8d5-133">Obwohl jede XML-Dokumentliteral genau eine XML-Stammelement benötigen, können sie eine beliebige Anzahl von XML-verarbeitungsanweisungen und XML-Kommentare haben.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="4e8d5-134">Ein XML-Dokumentliteral kann nicht in ein XML-Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e8d5-135">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="4e8d5-136">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein Visual Basic-Programm.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="4e8d5-137">Visual Basic-Compiler konvertiert die XML-Dokumentliteral in Aufrufe an die <xref:System.Xml.Linq.XDocument.%23ctor%2A> und <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e8d5-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e8d5-138">Example</span></span>  
 <span data-ttu-id="4e8d5-139">Das folgende Beispiel erstellt eine XML-Dokument, dessen eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, das ein anderes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="4e8d5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="4e8d5-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e8d5-140">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 <xref:System.Xml.Linq.XComment>  
 <xref:System.Xml.Linq.XDocument>  
 [<span data-ttu-id="4e8d5-141">XML-Verarbeitungsanweisungsliteral</span><span class="sxs-lookup"><span data-stu-id="4e8d5-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)  
 [<span data-ttu-id="4e8d5-142">XML-Kommentarliteral</span><span class="sxs-lookup"><span data-stu-id="4e8d5-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)  
 [<span data-ttu-id="4e8d5-143">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="4e8d5-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="4e8d5-144">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="4e8d5-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="4e8d5-145">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4e8d5-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="4e8d5-146">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="4e8d5-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
