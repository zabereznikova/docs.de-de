---
title: XML-Verarbeitungsanweisungsliteral
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: 3602a81feae9287a77d060bb46f10eefee4fc05d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347045"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="e08aa-102">XML-Verarbeitungsanweisungsliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e08aa-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="e08aa-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span><span class="sxs-lookup"><span data-stu-id="e08aa-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e08aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e08aa-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="e08aa-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e08aa-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="e08aa-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e08aa-106">Required.</span></span> <span data-ttu-id="e08aa-107">Denotes the start of the XML processing instruction literal.</span><span class="sxs-lookup"><span data-stu-id="e08aa-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="e08aa-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e08aa-108">Required.</span></span> <span data-ttu-id="e08aa-109">Name indicating which application the processing instruction targets.</span><span class="sxs-lookup"><span data-stu-id="e08aa-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="e08aa-110">Cannot begin with "xml" or "XML".</span><span class="sxs-lookup"><span data-stu-id="e08aa-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="e08aa-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e08aa-111">Optional.</span></span> <span data-ttu-id="e08aa-112">String indicating how the application targeted by `piName` should process the XML document.</span><span class="sxs-lookup"><span data-stu-id="e08aa-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="e08aa-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e08aa-113">Required.</span></span> <span data-ttu-id="e08aa-114">Denotes the end of the processing instruction.</span><span class="sxs-lookup"><span data-stu-id="e08aa-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e08aa-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e08aa-115">Return Value</span></span>  
 <span data-ttu-id="e08aa-116">Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e08aa-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e08aa-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e08aa-117">Remarks</span></span>  
 <span data-ttu-id="e08aa-118">XML processing instruction literals indicate how applications should process an XML document.</span><span class="sxs-lookup"><span data-stu-id="e08aa-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="e08aa-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span><span class="sxs-lookup"><span data-stu-id="e08aa-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="e08aa-120">The application interprets the meaning of `piName` and `piData`.</span><span class="sxs-lookup"><span data-stu-id="e08aa-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="e08aa-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span><span class="sxs-lookup"><span data-stu-id="e08aa-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="e08aa-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e08aa-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e08aa-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span><span class="sxs-lookup"><span data-stu-id="e08aa-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="e08aa-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span><span class="sxs-lookup"><span data-stu-id="e08aa-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e08aa-125">An XML literal can span multiple lines without needing line continuation characters.</span><span class="sxs-lookup"><span data-stu-id="e08aa-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="e08aa-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span><span class="sxs-lookup"><span data-stu-id="e08aa-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="e08aa-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="e08aa-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08aa-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e08aa-128">Example</span></span>  
 <span data-ttu-id="e08aa-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span><span class="sxs-lookup"><span data-stu-id="e08aa-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="e08aa-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e08aa-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="e08aa-131">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="e08aa-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="e08aa-132">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="e08aa-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="e08aa-133">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e08aa-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
