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
ms.openlocfilehash: 9bd1781e01bc4cbf1ce5da8c454ab2f5a679aead
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400175"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="c4e8f-102">XML-Verarbeitungsanweisungsliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4e8f-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="c4e8f-103">Ein Literalwert, der ein <xref:System.Xml.Linq.XProcessingInstruction> Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e8f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4e8f-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="c4e8f-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="c4e8f-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="c4e8f-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-106">Required.</span></span> <span data-ttu-id="c4e8f-107">Bezeichnet den Anfang des XML-Verarbeitungsanweisungs-Literals.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="c4e8f-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-108">Required.</span></span> <span data-ttu-id="c4e8f-109">Name, der angibt, welche Anwendung die Verarbeitungsanweisung als Ziel hat.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="c4e8f-110">Darf nicht mit "XML" oder "XML" beginnen.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="c4e8f-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-111">Optional.</span></span> <span data-ttu-id="c4e8f-112">Zeichenfolge, die angibt, wie die von Zielanwendung `piName` das XML-Dokument verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="c4e8f-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-113">Required.</span></span> <span data-ttu-id="c4e8f-114">Bezeichnet das Ende der Verarbeitungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4e8f-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c4e8f-115">Return Value</span></span>  
 <span data-ttu-id="c4e8f-116">Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e8f-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c4e8f-117">Remarks</span></span>  
 <span data-ttu-id="c4e8f-118">XML-Verarbeitungs Anweisungs Literale geben an, wie Anwendungen ein XML-Dokument verarbeiten sollen.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="c4e8f-119">Wenn eine Anwendung ein XML-Dokument lädt, kann die Anwendung die XML-Verarbeitungsanweisungen überprüfen, um zu bestimmen, wie das Dokument verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="c4e8f-120">Die Anwendung interpretiert die Bedeutung von `piName` und `piData` .</span><span class="sxs-lookup"><span data-stu-id="c4e8f-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="c4e8f-121">Das XML-dokumentliterale verwendet eine Syntax, die der XML-Verarbeitungsanweisung ähnelt.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="c4e8f-122">Weitere Informationen finden Sie unter [XML Document Literale](xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c4e8f-122">For more information, see [XML Document Literal](xml-document-literal.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4e8f-123">Das `piName` Element darf nicht mit den Zeichen folgen "XML" oder "XML" beginnen, da die XML 1,0-Spezifikation diese IDs reserviert.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="c4e8f-124">Sie können eine XML-Verarbeitungsanweisungs-Literale einer Variablen zuweisen oder Sie in ein XML-Dokumentliteral einschließen.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4e8f-125">Ein XML-Literale kann mehrere Zeilen umfassen, ohne dass Zeilen Fortsetzungs Zeichen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="c4e8f-126">Auf diese Weise können Sie Inhalte aus einem XML-Dokument kopieren und direkt in ein Visual Basic Programm einfügen.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="c4e8f-127">Der Visual Basic Compiler konvertiert das XML-Verarbeitungsanweisungsliteral in einen <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> aufrufkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4e8f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c4e8f-128">Example</span></span>  
 <span data-ttu-id="c4e8f-129">Im folgenden Beispiel wird eine Verarbeitungsanweisung erstellt, die ein Stylesheet für ein XML-Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4e8f-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#28)]  
  
## <a name="see-also"></a><span data-ttu-id="c4e8f-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4e8f-130">See also</span></span>

- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="c4e8f-131">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="c4e8f-131">XML Document Literal</span></span>](xml-document-literal.md)
- [<span data-ttu-id="c4e8f-132">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="c4e8f-132">XML Literals</span></span>](index.md)
- [<span data-ttu-id="c4e8f-133">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c4e8f-133">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
