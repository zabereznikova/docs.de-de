---
title: XML-Verarbeitungsanweisungsliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralProcessingInstruction
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], processing instruction
- XML processing instruction literal [Visual Basic]
- processing instruction literal [Visual Basic]
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
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
ms.openlocfilehash: 2ae976530ed3028677a1fef39db92265591df530
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-processing-instruction-literal-visual-basic"></a><span data-ttu-id="05c95-102">XML-Verarbeitungsanweisungsliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05c95-102">XML Processing Instruction Literal (Visual Basic)</span></span>
<span data-ttu-id="05c95-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XProcessingInstruction>Objekt.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="05c95-103">A literal representing an <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05c95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05c95-104">Syntax</span></span>  
  
```  
<?piName [ = piData ] ?>  
```  
  
## <a name="parts"></a><span data-ttu-id="05c95-105">Teile</span><span class="sxs-lookup"><span data-stu-id="05c95-105">Parts</span></span>  
 `<?`  
 <span data-ttu-id="05c95-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05c95-106">Required.</span></span> <span data-ttu-id="05c95-107">Kennzeichnet den Anfang des XML-Verarbeitungsanweisungsliteral.</span><span class="sxs-lookup"><span data-stu-id="05c95-107">Denotes the start of the XML processing instruction literal.</span></span>  
  
 `piName`  
 <span data-ttu-id="05c95-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05c95-108">Required.</span></span> <span data-ttu-id="05c95-109">Name, der angibt, welche Anwendung die Verarbeitungsanweisungszielen an.</span><span class="sxs-lookup"><span data-stu-id="05c95-109">Name indicating which application the processing instruction targets.</span></span> <span data-ttu-id="05c95-110">Nicht beginnen mit "Xml" oder "XML".</span><span class="sxs-lookup"><span data-stu-id="05c95-110">Cannot begin with "xml" or "XML".</span></span>  
  
 `piData`  
 <span data-ttu-id="05c95-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="05c95-111">Optional.</span></span> <span data-ttu-id="05c95-112">Zeichenfolge, die angibt, wie die Anwendung Ziel `piName` das XML-Dokument verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="05c95-112">String indicating how the application targeted by `piName` should process the XML document.</span></span>  
  
 `?>`  
 <span data-ttu-id="05c95-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05c95-113">Required.</span></span> <span data-ttu-id="05c95-114">Kennzeichnet das Ende der verarbeitungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="05c95-114">Denotes the end of the processing instruction.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05c95-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05c95-115">Return Value</span></span>  
 <span data-ttu-id="05c95-116">Ein <xref:System.Xml.Linq.XProcessingInstruction>Objekt.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="05c95-116">An <xref:System.Xml.Linq.XProcessingInstruction> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05c95-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05c95-117">Remarks</span></span>  
 <span data-ttu-id="05c95-118">XML-Verarbeitung Anweisung Literale geben an, wie die Anwendung ein XML-Dokument verarbeiten soll.</span><span class="sxs-lookup"><span data-stu-id="05c95-118">XML processing instruction literals indicate how applications should process an XML document.</span></span> <span data-ttu-id="05c95-119">Wenn eine Anwendung ein XML-Dokument geladen wird, kann die Anwendung die XML-verarbeitungsanweisungen zu entscheiden, wie das Dokument verarbeitet überprüfen.</span><span class="sxs-lookup"><span data-stu-id="05c95-119">When an application loads an XML document, the application can check the XML processing instructions to determine how to process the document.</span></span> <span data-ttu-id="05c95-120">Die Anwendung interpretiert die Bedeutung von `piName` und `piData`.</span><span class="sxs-lookup"><span data-stu-id="05c95-120">The application interprets the meaning of `piName` and `piData`.</span></span>  
  
 <span data-ttu-id="05c95-121">Das XML-Dokumentliteral verwendet Syntax ähnelt der von der XML-verarbeitungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="05c95-121">The XML document literal uses syntax that is similar to that of the XML processing instruction.</span></span> <span data-ttu-id="05c95-122">Weitere Informationen finden Sie unter [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span><span class="sxs-lookup"><span data-stu-id="05c95-122">For more information, see [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05c95-123">Das `piName` -Element darf nicht mit den Zeichenfolgen "Xml" oder "XML" beginnen, da diese Bezeichner für XML 1.0-Spezifikation reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="05c95-123">The `piName` element cannot begin with the strings "xml" or "XML", because the XML 1.0 specification reserves those identifiers.</span></span>  
  
 <span data-ttu-id="05c95-124">Sie können eine XML-Verarbeitungsanweisungsliteral einer Variablen zuweisen oder ihn in ein XML-Dokumentliteral.</span><span class="sxs-lookup"><span data-stu-id="05c95-124">You can assign an XML processing instruction literal to a variable or include it in an XML document literal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05c95-125">Ein XML-Literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="05c95-125">An XML literal can span multiple lines without needing line continuation characters.</span></span> <span data-ttu-id="05c95-126">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="05c95-126">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="05c95-127">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Verarbeitungsanweisungsliteral in einen Aufruf der <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A>Konstruktor.</xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="05c95-127">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML processing instruction literal to a call to the <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> constructor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05c95-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05c95-128">Example</span></span>  
 <span data-ttu-id="05c95-129">Das folgende Beispiel erstellt eine verarbeitungsanweisung, eine Stylesheet für ein XML-Dokument identifiziert.</span><span class="sxs-lookup"><span data-stu-id="05c95-129">The following example creates a processing instruction identifying a style-sheet for an XML document.</span></span>  
  
 <span data-ttu-id="05c95-130">[!code-vb[VbXMLSamples&#28;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="05c95-130">[!code-vb[VbXMLSamples#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-processing-instruction-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05c95-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05c95-131">See Also</span></span>  
 <span data-ttu-id="05c95-132"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="05c95-132"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
<span data-ttu-id="05c95-133"> [XML-Dokumentliteral](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span><span class="sxs-lookup"><span data-stu-id="05c95-133"> [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md) </span></span>  
<span data-ttu-id="05c95-134"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="05c95-134"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="05c95-135"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="05c95-135"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)</span></span>
