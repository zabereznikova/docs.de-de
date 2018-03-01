---
title: XML-Verarbeitungsanweisungsliteral (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9ce0f2d0dff80072beefdb4f84643ea28e2cf165
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="17abc-102">XML-Verarbeitungsanweisungsliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="17abc-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="17abc-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XProcessingInstruction> Objekt.</span><span class="sxs-lookup"><span data-stu-id="17abc-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17abc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17abc-104">Syntax</span></span>  
  
```xml  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="17abc-105">Teile</span><span class="sxs-lookup"><span data-stu-id="17abc-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="17abc-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17abc-106">Required.</span></span> <span data-ttu-id="17abc-107">Kennzeichnet den Anfang des XML-Verarbeitungsanweisungsliteral.</span><span class="sxs-lookup"><span data-stu-id="17abc-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="17abc-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17abc-108">Required.</span></span> <span data-ttu-id="17abc-109">Namen Sie, der angibt, welche Anwendung die Verarbeitung Anweisung Ziele an.</span><span class="sxs-lookup"><span data-stu-id="17abc-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="17abc-110">Nicht beginnen mit "Xml" oder "XML".</span><span class="sxs-lookup"><span data-stu-id="17abc-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="17abc-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="17abc-111">Optional.</span></span> <span data-ttu-id="17abc-112">Zeichenfolge, der angibt, wie die Anwendung Ziel `piName` sollte das XML-Dokument verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="17abc-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="17abc-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17abc-113">Required.</span></span> <span data-ttu-id="17abc-114">Kennzeichnet das Ende der verarbeitungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="17abc-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17abc-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17abc-115">Return Value</span></span>  
 <span data-ttu-id="17abc-116">Ein <xref:System.Xml.Linq.XProcessingInstruction>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="17abc-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17abc-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17abc-117">Remarks</span></span>  
 <span data-ttu-id="17abc-118">XML-Verarbeitung Anweisung Literale geben an, wie ein XML-Dokument Anwendungen verarbeitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="17abc-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="17abc-119">Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung bestimmen, wie das Dokument verarbeitet die XML-verarbeitungsanweisungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17abc-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="17abc-120">Die Anwendung interpretiert die Bedeutung der `piName` und `piData`.</span><span class="sxs-lookup"><span data-stu-id="17abc-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="17abc-121">Der XML-Dokumentliteral verwendet die Syntax, ähnlich dem Konzept der XML-verarbeitungsanweisung ist.</span><span class="sxs-lookup"><span data-stu-id="17abc-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="17abc-122">Weitere Informationen finden Sie unter [XML-Dokument-Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="17abc-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17abc-123">Die `piName` Element darf nicht mit den Zeichenfolgen "Xml" oder "XML", beginnen, da die XML 1.0-Spezifikation diese Bezeichner reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="17abc-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="17abc-124">Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder in einem XML-Dokumentliteral eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="17abc-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17abc-125">Ein XML-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="17abc-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="17abc-126">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in eine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="17abc-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 <span data-ttu-id="17abc-127">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="17abc-127">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17abc-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17abc-128">Example</span></span>  
 <span data-ttu-id="17abc-129">Das folgende Beispiel erstellt eine verarbeitungsanweisung, ein Stylesheet für ein XML-Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="17abc-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 [!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="17abc-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17abc-130">See Also</span></span>  
 <xref:System.Xml.Linq.XProcessingInstruction>  
 [<span data-ttu-id="17abc-131">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="17abc-131">XML Document Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)  
 [<span data-ttu-id="17abc-132">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="17abc-132">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="17abc-133">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17abc-133">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
