---
title: 'Vorgehensweise: Erstellen von XML-Literalen'
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], creating
ms.assetid: 573a6db5-b14d-4e42-b356-8cc7e2d77745
ms.openlocfilehash: c7ad8d684dde31550b6e1b74c098d152b227f6c1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058221"
---
# <a name="how-to-create-xml-literals-visual-basic"></a><span data-ttu-id="a56f7-102">Gewusst wie: Erstellen von XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a56f7-102">How to: Create XML Literals (Visual Basic)</span></span>

<span data-ttu-id="a56f7-103">Sie können ein XML-Dokument,-Fragment oder-Element direkt im Code mithilfe eines XML-Literals erstellen.</span><span class="sxs-lookup"><span data-stu-id="a56f7-103">You can create an XML document, fragment, or element directly in code by using an XML literal.</span></span> <span data-ttu-id="a56f7-104">In den Beispielen in diesem Thema wird gezeigt, wie ein XML-Element erstellt wird, das über drei untergeordnete Elemente verfügt, und wie ein XML-Dokument erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a56f7-104">The examples in this topic demonstrate how to create an XML element that has three child elements, and how to create an XML document.</span></span>  
  
 <span data-ttu-id="a56f7-105">Sie können auch die- [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs verwenden, um-Objekte zu erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a56f7-105">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="a56f7-106">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="a56f7-106">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
### <a name="to-create-an-xml-element"></a><span data-ttu-id="a56f7-107">So erstellen Sie ein XML-Element</span><span class="sxs-lookup"><span data-stu-id="a56f7-107">To create an XML element</span></span>  
  
- <span data-ttu-id="a56f7-108">Erstellen Sie die XML-Datei Inline mithilfe der XML-Literalsyntax, die der eigentlichen XML-Syntax entspricht.</span><span class="sxs-lookup"><span data-stu-id="a56f7-108">Create the XML inline by using the XML literal syntax, which is the same as the actual XML syntax.</span></span>  
  
     [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
     <span data-ttu-id="a56f7-109">Führen Sie den Code aus.</span><span class="sxs-lookup"><span data-stu-id="a56f7-109">Run the code.</span></span> <span data-ttu-id="a56f7-110">Die Ausgabe dieses Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a56f7-110">The output of this code is:</span></span>  
  
     `<contact>`  
  
     `<name>Patrick Hines</name>`  
  
     `<phone type="home">206-555-0144</phone>`  
  
     `<phone type="work">425-555-0145</phone>`  
  
     `</contact>`  
  
### <a name="to-create-an-xml-document"></a><span data-ttu-id="a56f7-111">So erstellen Sie ein XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="a56f7-111">To create an XML document</span></span>  
  
- <span data-ttu-id="a56f7-112">Erstellen Sie das XML-Dokument Inline.</span><span class="sxs-lookup"><span data-stu-id="a56f7-112">Create the XML document inline.</span></span> <span data-ttu-id="a56f7-113">Der folgende Code erstellt ein XML-Dokument, das eine Literalsyntax, eine XML-Deklaration, eine Verarbeitungsanweisung, einen Kommentar und ein Element mit einem anderen Element enthält.</span><span class="sxs-lookup"><span data-stu-id="a56f7-113">The following code creates an XML document that has literal syntax, an XML declaration, a processing instruction, a comment, and an element that contains another element.</span></span>  
  
     [!code-vb[VbXMLSamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#30)]  
  
     <span data-ttu-id="a56f7-114">Führen Sie den Code aus.</span><span class="sxs-lookup"><span data-stu-id="a56f7-114">Run the code.</span></span> <span data-ttu-id="a56f7-115">Die Ausgabe dieses Codes lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="a56f7-115">The output of this code is:</span></span>  
  
     `<?xml-stylesheet type="text/xsl" href="show_book.xsl"?>`  
  
     `<!-- Tests that the application works. -->`  
  
     `<books>`  
  
     `<book/>`  
  
     `</books>`  
  
## <a name="see-also"></a><span data-ttu-id="a56f7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a56f7-116">See also</span></span>

- [<span data-ttu-id="a56f7-117">XML</span><span class="sxs-lookup"><span data-stu-id="a56f7-117">XML</span></span>](index.md)
- [<span data-ttu-id="a56f7-118">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a56f7-118">Creating XML in Visual Basic</span></span>](creating-xml.md)
- [<span data-ttu-id="a56f7-119">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="a56f7-119">XML Element Literal</span></span>](../../../language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="a56f7-120">XML-Dokumentliteral</span><span class="sxs-lookup"><span data-stu-id="a56f7-120">XML Document Literal</span></span>](../../../language-reference/xml-literals/xml-document-literal.md)
