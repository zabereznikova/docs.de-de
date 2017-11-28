---
title: "Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bef4662d69ca7ceddeb2641cbe265d93712c5d16
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="356cd-102">Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="356cd-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="356cd-103">Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie eine XML-Dokument, Fragment oder Element, das zur Laufzeit erstellte Inhalte enthält.</span><span class="sxs-lookup"><span data-stu-id="356cd-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="356cd-104">In den folgenden Beispielen wird gezeigt, wie eingebettete Ausdrücke, die zum Auffüllen von Elementinhalt, Attribute und Elementnamen zur Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="356cd-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="356cd-105">Die Syntax für einen eingebetteten Ausdruck `<%=` `exp` `%>`, die die gleiche Syntax ist, [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="356cd-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] uses.</span></span> <span data-ttu-id="356cd-106">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="356cd-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="356cd-107">Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="356cd-107">You can also use the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs to create [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] objects.</span></span> <span data-ttu-id="356cd-108">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="356cd-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="356cd-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="356cd-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="356cd-110">Zum Einfügen von Text als Elementinhalt</span><span class="sxs-lookup"><span data-stu-id="356cd-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="356cd-111">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.</span><span class="sxs-lookup"><span data-stu-id="356cd-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]  
  
     <span data-ttu-id="356cd-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="356cd-112">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="356cd-113">Zum Einfügen von Text als Attributwert</span><span class="sxs-lookup"><span data-stu-id="356cd-113">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="356cd-114">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist das `phoneType` Variable als Wert für die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="356cd-114">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]  
  
     <span data-ttu-id="356cd-115">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="356cd-115">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="356cd-116">Zum Einfügen von Text für den Namen eines Elements</span><span class="sxs-lookup"><span data-stu-id="356cd-116">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="356cd-117">Im folgende Beispiel wird gezeigt, wie den Text einfügen, die in enthalten ist die `elementName` -Variable als den Namen eines Elements.</span><span class="sxs-lookup"><span data-stu-id="356cd-117">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="356cd-118">Wenn Elemente mit diesem Verfahren erstellen, müssen Sie schließen, sie mit der \</ >-Tag.</span><span class="sxs-lookup"><span data-stu-id="356cd-118">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]  
  
     <span data-ttu-id="356cd-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="356cd-119">This example produces the following output:</span></span>  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="356cd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="356cd-120">See Also</span></span>  
 [<span data-ttu-id="356cd-121">Gewusst wie: Erstellen von XML-Literalen</span><span class="sxs-lookup"><span data-stu-id="356cd-121">How to: Create XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)  
 [<span data-ttu-id="356cd-122">Eingebettete Ausdrücke in XML</span><span class="sxs-lookup"><span data-stu-id="356cd-122">Embedded Expressions in XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)  
 [<span data-ttu-id="356cd-123">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="356cd-123">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="356cd-124">XML</span><span class="sxs-lookup"><span data-stu-id="356cd-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
