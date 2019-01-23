---
title: XML-Verarbeitungsanweisungsliteral (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
ms.openlocfilehash: cb9ad1d687203dff497e4cd451933a8bbbdf4bf6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491232"
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="17ea2-102">XML-Verarbeitungsanweisungsliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17ea2-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="17ea2-103">Ein Zeichenfolgenliteral, ein <xref:System.Xml.Linq.XProcessingInstruction> Objekt.</span><span class="sxs-lookup"><span data-stu-id="17ea2-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ea2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17ea2-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="17ea2-105">Teile</span><span class="sxs-lookup"><span data-stu-id="17ea2-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="17ea2-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17ea2-106">Required.</span></span> <span data-ttu-id="17ea2-107">Gibt den Anfang der XML-Verarbeitungsanweisungsliteral an.</span><span class="sxs-lookup"><span data-stu-id="17ea2-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="17ea2-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17ea2-108">Required.</span></span> <span data-ttu-id="17ea2-109">Namen Sie, der angibt, welche Anwendung die Verarbeitungsanweisungszielen an.</span><span class="sxs-lookup"><span data-stu-id="17ea2-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="17ea2-110">Nicht beginnen mit "Xml" oder "XML".</span><span class="sxs-lookup"><span data-stu-id="17ea2-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="17ea2-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="17ea2-111">Optional.</span></span> <span data-ttu-id="17ea2-112">Zeichenfolge, der angibt, wie die Anwendung von soll `piName` das XML-Dokument verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="17ea2-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="17ea2-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17ea2-113">Required.</span></span> <span data-ttu-id="17ea2-114">Kennzeichnet das Ende der verarbeitungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="17ea2-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17ea2-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17ea2-115">Return Value</span></span>  
 <span data-ttu-id="17ea2-116">Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="17ea2-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17ea2-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17ea2-117">Remarks</span></span>  
 <span data-ttu-id="17ea2-118">XML-Verarbeitung Anweisung Literale geben an, wie Anwendungen ein XML-Dokument verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="17ea2-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="17ea2-119">Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung die XML-verarbeitungsanweisungen zu bestimmen, wie zum Verarbeiten des Dokuments überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17ea2-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="17ea2-120">Die Anwendung interpretiert die Bedeutung von `piName` und `piData`.</span><span class="sxs-lookup"><span data-stu-id="17ea2-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="17ea2-121">Das XML-Dokumentliteral verwendet die Syntax, die vergleichbar mit der XML-verarbeitungsanweisung ist.</span><span class="sxs-lookup"><span data-stu-id="17ea2-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="17ea2-122">Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="17ea2-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ea2-123">Die `piName` Element darf nicht mit den Zeichenfolgen "Xml" oder "XML", beginnen, da diese Bezeichner für XML 1.0-Spezifikation reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="17ea2-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="17ea2-124">Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder ihn in einem XML-Dokumentliteral.</span><span class="sxs-lookup"><span data-stu-id="17ea2-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17ea2-125">Ein XML-Literal kann mehrere Zeilen umfassen, ohne der Fortsetzung-Zeile-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="17ea2-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="17ea2-126">Dadurch können Sie zum Kopieren von Inhalt aus einem XML-Dokument, und fügen ihn direkt in Visual Basic-Programms.</span><span class="sxs-lookup"><span data-stu-id="17ea2-126">This enables you to copy content from an XML document and paste it directly into a Visual Basic program.</span></span>  
  
 <span data-ttu-id="17ea2-127">Visual Basic-Compiler konvertiert die XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="17ea2-127">The Visual Basic compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17ea2-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17ea2-128">Example</span></span>  
 <span data-ttu-id="17ea2-129">Das folgende Beispiel erstellt eine verarbeitungsanweisung, ein Stylesheet für ein XML-Dokument zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="17ea2-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="17ea2-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17ea2-130">See also</span></span>
- <xref:System.Xml.Linq.XProcessingInstruction>
- [<span data-ttu-id="17ea2-131">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="17ea2-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [<span data-ttu-id="17ea2-132">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="17ea2-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="17ea2-133">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17ea2-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
