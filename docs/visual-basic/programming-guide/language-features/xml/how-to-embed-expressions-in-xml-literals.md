---
title: "Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic) | Microsoft-Dokumentation"
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
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
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
ms.openlocfilehash: e4f086b06575cb8300bd65d450cda6b9893bb692
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a><span data-ttu-id="516e4-102">Gewusst wie: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="516e4-102">How to: Embed Expressions in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="516e4-103">Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie ein XML-Dokument, Fragment oder Element, das zur Laufzeit erstellte Inhalte enthält.</span><span class="sxs-lookup"><span data-stu-id="516e4-103">You can combine XML literals with embedded expressions to create an XML document, fragment, or element that contains content created at run time.</span></span> <span data-ttu-id="516e4-104">Die folgenden Beispiele veranschaulichen, wie Sie eingebettete Ausdrücke zum Auffüllen von Elementinhalt, Attribute und Elementnamen zur Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="516e4-104">The following examples demonstrate how to use embedded expressions to populate element content, attributes, and element names at run time.</span></span>  
  
 <span data-ttu-id="516e4-105">Die Syntax für einen eingebetteten Ausdruck lautet `<%=` `exp` `%>`, also die gleiche Syntax, [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="516e4-105">The syntax for an embedded expression is `<%=` `exp` `%>`, which is the same syntax that [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] uses.</span></span> <span data-ttu-id="516e4-106">Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span><span class="sxs-lookup"><span data-stu-id="516e4-106">For more information, see [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).</span></span>  
  
 <span data-ttu-id="516e4-107">Sie können auch die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekte.</span><span class="sxs-lookup"><span data-stu-id="516e4-107">You can also use the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] APIs to create [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] objects.</span></span> <span data-ttu-id="516e4-108">Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="516e4-108">For more information, see <xref:System.Xml.Linq.XElement>.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="516e4-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="516e4-109">Procedures</span></span>  
  
#### <a name="to-insert-text-as-element-content"></a><span data-ttu-id="516e4-110">Zum Einfügen von Text als Inhalt des Elements</span><span class="sxs-lookup"><span data-stu-id="516e4-110">To insert text as element content</span></span>  
  
-   <span data-ttu-id="516e4-111">Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.</span><span class="sxs-lookup"><span data-stu-id="516e4-111">The following example shows how to insert the text that is contained in the `contactName` variable between the opening and closing name elements.</span></span>  
  
     <span data-ttu-id="516e4-112">[!code-vb[VbXMLSamples Nr.&39;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="516e4-112">[!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_1.vb)]</span></span>  
  
     <span data-ttu-id="516e4-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="516e4-113">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a><span data-ttu-id="516e4-114">Zum Einfügen von Text als Attributwert</span><span class="sxs-lookup"><span data-stu-id="516e4-114">To insert text as an attribute value</span></span>  
  
-   <span data-ttu-id="516e4-115">Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `phoneType` Variable als Wert für die `type` Attribut.</span><span class="sxs-lookup"><span data-stu-id="516e4-115">The following example shows how to insert the text that is contained in the `phoneType` variable as the value of the `type` attribute.</span></span>  
  
     <span data-ttu-id="516e4-116">[!code-vb[VbXMLSamples&#40;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="516e4-116">[!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_2.vb)]</span></span>  
  
     <span data-ttu-id="516e4-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="516e4-117">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a><span data-ttu-id="516e4-118">Zum Einfügen von Text für einen Elementnamen</span><span class="sxs-lookup"><span data-stu-id="516e4-118">To insert text for an element name</span></span>  
  
-   <span data-ttu-id="516e4-119">Das folgende Beispiel zeigt, wie Sie den Text einfügen, die in enthalten ist die `elementName` -Variable als den Namen eines Elements.</span><span class="sxs-lookup"><span data-stu-id="516e4-119">The following example shows how to insert the text that is contained in the `elementName` variable as the name of an element.</span></span>  
  
     <span data-ttu-id="516e4-120">Elemente mit diesem Verfahren erstellen, müssen, schließen Sie sie mit der \</ > Tag.</span><span class="sxs-lookup"><span data-stu-id="516e4-120">When creating elements by using this technique, you must close them with the \</> tag.</span></span>  
  
     <span data-ttu-id="516e4-121">[!code-vb[VbXMLSamples&#41;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="516e4-121">[!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-embed-expressions-in-xml-literals_3.vb)]</span></span>  
  
     <span data-ttu-id="516e4-122">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="516e4-122">This example produces the following output:</span></span>  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="516e4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="516e4-123">See Also</span></span>  
 <span data-ttu-id="516e4-124">[Gewusst wie: Erstellen von XML-Literalen](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span><span class="sxs-lookup"><span data-stu-id="516e4-124">[How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md) </span></span>  
<span data-ttu-id="516e4-125"> [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span><span class="sxs-lookup"><span data-stu-id="516e4-125"> [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md) </span></span>  
<span data-ttu-id="516e4-126"> [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="516e4-126"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="516e4-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span><span class="sxs-lookup"><span data-stu-id="516e4-127"> [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)</span></span>
