---
title: XML-Dokumentliteral (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlLiteralDocument
dev_langs:
- VB
helpviewer_keywords:
- XML document literal [Visual Basic]
- XML literals [Visual Basic], document
- XML documents [Visual Basic], creating
- document literal [Visual Basic]
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
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
ms.openlocfilehash: 5e173c8bc89f61925c3e6127fb3cac61379aeffa
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-document-literal-visual-basic"></a><span data-ttu-id="e4df5-102">XML-Dokumentliteral (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e4df5-102">XML Document Literal (Visual Basic)</span></span>
<span data-ttu-id="e4df5-103">Ein Zeichenfolgenliteral, eine <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4df5-103">A literal representing an <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4df5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4df5-104">Syntax</span></span>  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e4df5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e4df5-105">Parts</span></span>  
  
|<span data-ttu-id="e4df5-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e4df5-106">Term</span></span>|<span data-ttu-id="e4df5-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e4df5-107">Definition</span></span>|  
|---|---|  
|`encoding`|<span data-ttu-id="e4df5-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="e4df5-108">Optional.</span></span> <span data-ttu-id="e4df5-109">Literaltext, der deklariert, welche Codierung das Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4df5-109">Literal text declaring which encoding the document uses.</span></span>|  
|`standalone`|<span data-ttu-id="e4df5-110">Optional.</span><span class="sxs-lookup"><span data-stu-id="e4df5-110">Optional.</span></span> <span data-ttu-id="e4df5-111">Normaler Text.</span><span class="sxs-lookup"><span data-stu-id="e4df5-111">Literal text.</span></span> <span data-ttu-id="e4df5-112">Muss "Ja" oder "no".</span><span class="sxs-lookup"><span data-stu-id="e4df5-112">Must be "yes" or "no".</span></span>|  
|`piCommentList`|<span data-ttu-id="e4df5-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="e4df5-113">Optional.</span></span> <span data-ttu-id="e4df5-114">Liste der XML-verarbeitungsanweisungen und XML-Kommentare.</span><span class="sxs-lookup"><span data-stu-id="e4df5-114">List of XML processing instructions and XML comments.</span></span> <span data-ttu-id="e4df5-115">Hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="e4df5-115">Takes the following format:</span></span><br /><br /> <span data-ttu-id="e4df5-116">`piComment [` `piComment` `... ]`</span><span class="sxs-lookup"><span data-stu-id="e4df5-116">`piComment [` `piComment` `... ]`</span></span><br /><br /> <span data-ttu-id="e4df5-117">Jede `piComment`kann einer der folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="e4df5-117">Each `piComment`can be one of the following:</span></span><br /><br /><span data-ttu-id="e4df5-118"> -   [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4df5-118"> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).</span></span><br /><span data-ttu-id="e4df5-119">-   [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4df5-119">-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).</span></span>|  
|`rootElement`|<span data-ttu-id="e4df5-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e4df5-120">Required.</span></span> <span data-ttu-id="e4df5-121">Das Stammelement des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="e4df5-121">Root element of the document.</span></span> <span data-ttu-id="e4df5-122">Das Format ist eines der folgenden:</span><span class="sxs-lookup"><span data-stu-id="e4df5-122">The format is one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="e4df5-123">[XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="e4df5-123">[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span></li><li><span data-ttu-id="e4df5-124">Eingebetteter Ausdruck der Form `<%=` `elementExp` `%>`.</span><span class="sxs-lookup"><span data-stu-id="e4df5-124">Embedded expression of the form `<%=` `elementExp` `%>`.</span></span> <span data-ttu-id="e4df5-125">Die `elementExp` gibt einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="e4df5-125">The `elementExp` returns one of the following:</span></span><br /><br /> <ul><li><span data-ttu-id="e4df5-126">Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4df5-126">An <xref:System.Xml.Linq.XElement> object.</span></span></li><li><span data-ttu-id="e4df5-127">Eine Auflistung mit einem <xref:System.Xml.Linq.XElement>-Objekt und eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>und <xref:System.Xml.Linq.XComment>Objekte.</xref:System.Xml.Linq.XComment> </xref:System.Xml.Linq.XProcessingInstruction> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4df5-127">A collection that contains one <xref:System.Xml.Linq.XElement> object and any number of <xref:System.Xml.Linq.XProcessingInstruction> and <xref:System.Xml.Linq.XComment> objects.</span></span></li></ul></li></ul><br /> <span data-ttu-id="e4df5-128">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e4df5-128">For more information, see [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="e4df5-129">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4df5-129">Return Value</span></span>  
 <span data-ttu-id="e4df5-130">Ein <xref:System.Xml.Linq.XDocument>Objekt.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4df5-130">An <xref:System.Xml.Linq.XDocument> object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4df5-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4df5-131">Remarks</span></span>  
 <span data-ttu-id="e4df5-132">Ein XML-Dokumentliteral wird durch die XML-Deklaration am Anfang des Literals identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e4df5-132">An XML document literal is identified by the XML declaration at the start of the literal.</span></span> <span data-ttu-id="e4df5-133">Obwohl jedes XML-Dokumentliteral genau ein XML-Stammelement verfügen muss, können sie eine beliebige Anzahl von XML-verarbeitungsanweisungen und XML-Kommentare.</span><span class="sxs-lookup"><span data-stu-id="e4df5-133">Although each XML document literal must have exactly one root XML element, it can have any number of XML processing instructions and XML comments.</span></span>  
  
 <span data-ttu-id="e4df5-134">Ein XML-Dokumentliteral kann nicht in ein XML-Element angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e4df5-134">An XML document literal cannot appear in an XML element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4df5-135">Ein XML-literal kann mehrere Zeilen umfassen, ohne Zeilenfortsetzungszeichen.</span><span class="sxs-lookup"><span data-stu-id="e4df5-135">An XML literal can span multiple lines without using line continuation characters.</span></span> <span data-ttu-id="e4df5-136">Dadurch können Sie Inhalt aus einem XML-Dokument kopieren und fügen ihn direkt in ein [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Programm.</span><span class="sxs-lookup"><span data-stu-id="e4df5-136">This enables you to copy content from an XML document and paste it directly into a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program.</span></span>  
  
 <span data-ttu-id="e4df5-137">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert das XML-Dokumentliteral in Aufrufe an die <xref:System.Xml.Linq.XDocument.%23ctor%2A>und <xref:System.Xml.Linq.XDeclaration.%23ctor%2A>Konstruktoren.</xref:System.Xml.Linq.XDeclaration.%23ctor%2A> </xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="e4df5-137">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts the XML document literal into calls to the <xref:System.Xml.Linq.XDocument.%23ctor%2A> and <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> constructors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4df5-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4df5-138">Example</span></span>  
 <span data-ttu-id="e4df5-139">Das folgende Beispiel erstellt eine XML-Dokument mit einer XML-Deklaration, eine Anweisung zur Verarbeitung, einen Kommentar und ein Element, ein anderes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="e4df5-139">The following example creates an XML document that has an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
 <span data-ttu-id="e4df5-140">[!code-vb[VbXMLSamples&#30;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e4df5-140">[!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-document-literal_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4df5-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4df5-141">See Also</span></span>  
 <span data-ttu-id="e4df5-142"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="e4df5-142"><xref:System.Xml.Linq.XElement></span></span>   
 <span data-ttu-id="e4df5-143"><xref:System.Xml.Linq.XProcessingInstruction></xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="e4df5-143"><xref:System.Xml.Linq.XProcessingInstruction></span></span>   
 <span data-ttu-id="e4df5-144"><xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="e4df5-144"><xref:System.Xml.Linq.XComment></span></span>   
 <span data-ttu-id="e4df5-145"><xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="e4df5-145"><xref:System.Xml.Linq.XDocument></span></span>   
<span data-ttu-id="e4df5-146"> [XML-Verarbeitungsanweisungsliteral](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4df5-146"> [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md) </span></span>  
<span data-ttu-id="e4df5-147"> [XML-Kommentarliteral](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4df5-147"> [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md) </span></span>  
<span data-ttu-id="e4df5-148"> [XML-Elementliteral](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="e4df5-148"> [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="e4df5-149"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="e4df5-149"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="e4df5-150"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e4df5-150"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="e4df5-151"> [Eingebettete Ausdrücke in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span><span class="sxs-lookup"><span data-stu-id="e4df5-151"> [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)</span></span>
