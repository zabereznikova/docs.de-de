---
title: 'Vorgehensweise: Erstellen von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: 836ec4390e7675effe57c75c79768272d66925a3
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836862"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="de9c7-102">Vorgehensweise: Erstellen von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de9c7-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="de9c7-103">Sie können eine XML-Dokument, Fragment oder Element direkt im Code erstellen, mit einem XML-literal.</span><span class="sxs-lookup"><span data-stu-id="de9c7-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="de9c7-104">In die Beispielen in diesem Thema wird veranschaulicht, wie ein XML-Element zu erstellen, die über drei untergeordnete Elemente verfügt wie ein XML-Dokument erstellt.</span><span class="sxs-lookup"><span data-stu-id="de9c7-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="de9c7-105">Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="de9c7-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="de9c7-106">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="de9c7-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="de9c7-107">Erstellen Sie ein XML-element</span><span class="sxs-lookup"><span data-stu-id="de9c7-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="de9c7-108">Erstellen Sie die XML-Inline, indem Sie mit der XML-Literalen Syntax, die die tatsächlichen XML-Syntax identisch ist.</span><span class="sxs-lookup"><span data-stu-id="de9c7-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="de9c7-109">Führen Sie den Code ein.</span><span class="sxs-lookup"><span data-stu-id="de9c7-109">Run the code.</span></span> <span data-ttu-id="de9c7-110">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="de9c7-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="de9c7-111">Zum Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="de9c7-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="de9c7-112">Die XML-Dokument Inline zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="de9c7-112">Create the XML document inline.</span></span> <span data-ttu-id="de9c7-113">Der folgende Code erstellt eine XML-Dokument mit Literalen Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, ein anderes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="de9c7-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="de9c7-114">Führen Sie den Code ein.</span><span class="sxs-lookup"><span data-stu-id="de9c7-114">Run the code.</span></span> <span data-ttu-id="de9c7-115">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="de9c7-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="de9c7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de9c7-116">See also</span></span>

- [<span data-ttu-id="de9c7-117">XML</span><span class="sxs-lookup"><span data-stu-id="de9c7-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="de9c7-118">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="de9c7-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="de9c7-119">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="de9c7-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="de9c7-120">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="de9c7-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
