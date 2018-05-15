---
title: 'Gewusst wie: Erstellen von XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: e5f8429b3ff02678bf8bf3e9e32bef6eb1a56831
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="bdb83-102">Gewusst wie: Erstellen von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdb83-102">How to: Create XML Literals (Visual Basic)</span></span>
<span data-ttu-id="bdb83-103">Sie können eine XML-Dokument, Fragment oder Element direkt im Code erstellen, mit einem XML-literal.</span><span class="sxs-lookup"><span data-stu-id="bdb83-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="bdb83-104">In den Beispielen in diesem Thema wird veranschaulicht, wie ein XML-Element zu erstellen, die über drei untergeordnete Elemente verfügt, wie ein XML-Dokument erstellt.</span><span class="sxs-lookup"><span data-stu-id="bdb83-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="bdb83-105">Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="bdb83-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="bdb83-106">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="bdb83-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="bdb83-107">So erstellen ein XML-element</span><span class="sxs-lookup"><span data-stu-id="bdb83-107">To create an XML element</span></span>  
  
-   <span data-ttu-id="bdb83-108">Erstellen Sie die XML-Inline mit der XML-literal Syntax, die die tatsächlichen XML-Syntax entspricht.</span><span class="sxs-lookup"><span data-stu-id="bdb83-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_1.vb)]  
  
     <span data-ttu-id="bdb83-109">Führen Sie den Code ein.</span><span class="sxs-lookup"><span data-stu-id="bdb83-109">Run the code.</span></span> <span data-ttu-id="bdb83-110">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="bdb83-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="bdb83-111">Beim Erstellen des XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="bdb83-111">To create an XML document</span></span>  
  
-   <span data-ttu-id="bdb83-112">Erstellen der XML-Dokument zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bdb83-112">Create the XML document inline.</span></span> <span data-ttu-id="bdb83-113">Der folgende Code erstellt ein XML-Dokument, dessen literal Syntax, eine XML-Deklaration, eine verarbeitungsanweisung, einen Kommentar und ein Element, das ein anderes Element enthält.</span><span class="sxs-lookup"><span data-stu-id="bdb83-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-xml-literals_2.vb)]  
  
     <span data-ttu-id="bdb83-114">Führen Sie den Code ein.</span><span class="sxs-lookup"><span data-stu-id="bdb83-114">Run the code.</span></span> <span data-ttu-id="bdb83-115">Die Ausgabe dieses Codes lautet:</span><span class="sxs-lookup"><span data-stu-id="bdb83-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="bdb83-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdb83-116">See Also</span></span>  
 [<span data-ttu-id="bdb83-117">XML</span><span class="sxs-lookup"><span data-stu-id="bdb83-117">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="bdb83-118">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdb83-118">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="bdb83-119">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="bdb83-119">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [<span data-ttu-id="bdb83-120">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="bdb83-120">XML Document Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
