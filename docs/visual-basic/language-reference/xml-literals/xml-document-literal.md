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
ms.openlocfilehash: 8a489be46295c213b7a8b355eb3c9786d49dd8f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958498"
---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="881cb-102">XML-Dokumentliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="881cb-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="881cb-103">Ein Literalwert <xref:System.Xml.Linq.XDocument> , der ein Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="881cb-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881cb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="881cb-104">Syntax</span></span>  
  
```xml  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="881cb-105">Teile</span><span class="sxs-lookup"><span data-stu-id="881cb-105">Parts</span></span>  
  
|<span data-ttu-id="881cb-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="881cb-106">Term</span></span>|<span data-ttu-id="881cb-107">Definition</span><span class="sxs-lookup"><span data-stu-id="881cb-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="881cb-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="881cb-108">Optional.</span></span> <span data-ttu-id="881cb-109">Literaler Text, der deklariert, welche Codierung das Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="881cb-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="881cb-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="881cb-110">Optional.</span></span> <span data-ttu-id="881cb-111">LiteralText.</span><span class="sxs-lookup"><span data-stu-id="881cb-111">Literal text.</span></span> <span data-ttu-id="881cb-112">Muss "yes" oder "No" lauten.</span><span class="sxs-lookup"><span data-stu-id="881cb-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="881cb-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="881cb-113">Optional.</span></span> <span data-ttu-id="881cb-114">Die Liste der XML-Verarbeitungsanweisungen und XML-Kommentare.</span><span class="sxs-lookup"><span data-stu-id="881cb-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="881cb-115">Hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="881cb-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="881cb-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="881cb-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="881cb-117">Dabei `piComment` kann es sich um einen der folgenden handeln:</span><span class="sxs-lookup"><span data-stu-id="881cb-117">Each `piComment` can be one of the following:</span></span><br /><br /> <span data-ttu-id="881cb-118">-   [XML-Verarbeitungs Anweisungs Literale](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="881cb-118">-   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="881cb-119">-   [XML-Kommentarliteral.](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)</span><span class="sxs-lookup"><span data-stu-id="881cb-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="881cb-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="881cb-120">Required.</span></span> <span data-ttu-id="881cb-121">Das Stamm Element des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="881cb-121">Root element of the document.</span></span> <span data-ttu-id="881cb-122">Das Format ist einer der folgenden:</span><span class="sxs-lookup"><span data-stu-id="881cb-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="881cb-123">[XML-Elementliterale](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="881cb-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="881cb-124">Eingebetteter Ausdruck des Formulars `<%=`. `elementExp` `%>`</span><span class="sxs-lookup"><span data-stu-id="881cb-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="881cb-125">Der `elementExp` gibt eine der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="881cb-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="881cb-126">Ein <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="881cb-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="881cb-127">Eine Auflistung, die ein <xref:System.Xml.Linq.XElement> -Objekt und eine beliebige <xref:System.Xml.Linq.XProcessingInstruction> Anzahl <xref:System.Xml.Linq.XComment> von-Objekten und-Objekten enthält.</span><span class="sxs-lookup"><span data-stu-id="881cb-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="881cb-128">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="881cb-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="881cb-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="881cb-129">Return Value</span></span>  
 <span data-ttu-id="881cb-130">Ein <xref:System.Xml.Linq.XDocument>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="881cb-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="881cb-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="881cb-131">Remarks</span></span>  
 <span data-ttu-id="881cb-132">Ein XML-Dokumentliteral wird durch die XML-Deklaration am Anfang des Literals identifiziert.</span><span class="sxs-lookup"><span data-stu-id="881cb-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="881cb-133">Obwohl jedes XML-Dokumentliteral genau ein XML-Stamm Element aufweisen muss, kann es eine beliebige Anzahl von XML-Verarbeitungsanweisungen und XML-Kommentaren enthalten.</span><span class="sxs-lookup"><span data-stu-id="881cb-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="881cb-134">Ein XML-Dokumentliteral darf nicht in einem XML-Element vorkommen.</span><span class="sxs-lookup"><span data-stu-id="881cb-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="881cb-135">Ein XML-Literale kann mehrere Zeilen umfassen, ohne Zeilen Fortsetzungs Zeichen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="881cb-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="881cb-136">Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.</span><span class="sxs-lookup"><span data-stu-id="881cb-136">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="881cb-137">Der Visual Basic Compiler konvertiert das XML-Dokumentliteral in Aufrufe <xref:System.Xml.Linq.XDocument.%23ctor%2A> der <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> -und-Konstruktoren.</span><span class="sxs-lookup"><span data-stu-id="881cb-137">The Visual Basic compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="881cb-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="881cb-138">Example</span></span>  
 <span data-ttu-id="881cb-139">Im folgenden Beispiel wird ein XML-Dokument erstellt, das eine XML-Deklaration, eine Verarbeitungsanweisung, einen Kommentar und ein-Element enthält, das ein anderes-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="881cb-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="881cb-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="881cb-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Xml.Linq.XProcessingInstruction>
- <xref:System.Xml.Linq.XComment>
- <xref:System.Xml.Linq.XDocument>
- [<span data-ttu-id="881cb-141">XML-Verarbeitungsanweisungsliteral</span><span class="sxs-lookup"><span data-stu-id="881cb-141">XML Processing Instruction Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)
- [<span data-ttu-id="881cb-142">XML-Kommentarliteral</span><span class="sxs-lookup"><span data-stu-id="881cb-142">XML Comment Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)
- [<span data-ttu-id="881cb-143">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="881cb-143">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="881cb-144">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="881cb-144">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="881cb-145">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="881cb-145">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="881cb-146">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="881cb-146">Embedded Expressions in XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
