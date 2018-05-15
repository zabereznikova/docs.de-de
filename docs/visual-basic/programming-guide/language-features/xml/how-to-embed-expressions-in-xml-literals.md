---
title: 'Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: 41dc6ef8d2ec2ffd6cd1cf793911f2e09f1a1e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="45672-102">Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45672-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="45672-103">Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie eine XML-Dokument, Fragment oder Element, das zur Laufzeit erstellte Inhalte enthält.</span><span class="sxs-lookup"><span data-stu-id="45672-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="45672-104">In den folgenden Beispielen wird gezeigt, wie eingebettete Ausdrücke, die zum Auffüllen von Elementinhalt, Attribute und Elementnamen zur Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="45672-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="45672-105">Die Syntax für einen eingebetteten Ausdruck `<%=` `exp` `%>`, die die gleiche Syntax ist, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="45672-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="45672-106">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="45672-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="45672-107">Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="45672-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="45672-108">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="45672-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="45672-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="45672-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="45672-110">Zum Einfügen von Text als Elementinhalt</span><span class="sxs-lookup"><span data-stu-id="45672-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="45672-111">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.</span><span class="sxs-lookup"><span data-stu-id="45672-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="45672-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="45672-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="45672-113">Zum Einfügen von Text als Attributwert</span><span class="sxs-lookup"><span data-stu-id="45672-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="45672-114">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `phoneType` Variable als Wert für die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="45672-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="45672-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="45672-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="45672-116">Zum Einfügen von Text für den Namen eines Elements</span><span class="sxs-lookup"><span data-stu-id="45672-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="45672-117">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist die `elementName` -Variable als den Namen eines Elements.</span><span class="sxs-lookup"><span data-stu-id="45672-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="45672-118">Wenn Elemente mit diesem Verfahren erstellen, müssen Sie schließen, sie mit der \</ >-Tag.</span><span class="sxs-lookup"><span data-stu-id="45672-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="45672-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="45672-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="45672-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45672-120">See Also</span></span>  
 [<span data-ttu-id="45672-121">Gewusst wie: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="45672-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="45672-122">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="45672-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="45672-123">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45672-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="45672-124">XML</span><span class="sxs-lookup"><span data-stu-id="45672-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
