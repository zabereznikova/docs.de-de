---
title: 'Gewusst wie: Erstellen von XML-Literalen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
caps.latest.revision: 17
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
ms.openlocfilehash: 3a7b5dc692317067290b48222ba056d765a449f3
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="680bb-102">Gewusst wie: Erstellen von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="680bb-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="680bb-103">Sie können ein XML-Dokument, Fragment oder das Element direkt im Code erstellen, mit einem XML-literal.</span><span class="sxs-lookup"><span data-stu-id="680bb-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="680bb-104">In den Beispielen in diesem Thema veranschaulichen ein XML-Element zu erstellen, die drei untergeordnete Elemente verfügt, und wie Sie ein XML-Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="680bb-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="680bb-105">Sie können auch die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="680bb-105">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="680bb-106">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="680bb-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="680bb-107">Erstellen Sie ein XML-element</span><span class="sxs-lookup"><span data-stu-id="680bb-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="680bb-108">Erstellen Sie XML Inline, indem die XML-Literalen Syntax verwenden, die die tatsächlichen XML-Syntax entspricht.</span><span class="sxs-lookup"><span data-stu-id="680bb-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     <span data-ttu-id="680bb-109">[!code-vb[VbXMLSamples&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="680bb-109">[!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="680bb-110">Führen Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="680bb-110">Run the code.</span></span> <span data-ttu-id="680bb-111">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="680bb-111">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="680bb-112">Zum Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="680bb-112">To create an XML document</span></span>  
  
-   <span data-ttu-id="680bb-113">Erstellen Sie die XML-Dokument Inline.</span><span class="sxs-lookup"><span data-stu-id="680bb-113">Create the XML document inline.</span></span> <span data-ttu-id="680bb-114">Der folgende Code erstellt ein XML-Dokument mit Literalen Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, ein anderes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="680bb-114">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     <span data-ttu-id="680bb-115">[!code-vb[VbXMLSamples&#30;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="680bb-115">[!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="680bb-116">Führen Sie den Code.</span><span class="sxs-lookup"><span data-stu-id="680bb-116">Run the code.</span></span> <span data-ttu-id="680bb-117">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="680bb-117">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="680bb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="680bb-118">See Also</span></span>  
 <span data-ttu-id="680bb-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="680bb-119">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="680bb-120"> [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="680bb-120"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="680bb-121"> [XML-Elementliteral](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span><span class="sxs-lookup"><span data-stu-id="680bb-121"> [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) </span></span>  
<span data-ttu-id="680bb-122"> [XML-Dokumentliteral](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span><span class="sxs-lookup"><span data-stu-id="680bb-122"> [XML Document Literal](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)</span></span>
