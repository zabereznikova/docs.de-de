---
title: Leerzeichen in XML-Literalen (Visual Basic) | Microsoft-Dokumentation
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
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
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
ms.openlocfilehash: 4fc3d30a9c71cbd732597c5e3f32bd01eb489a80
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="91d3b-102">Leerzeichen in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91d3b-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="91d3b-103">Die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Compiler bindet nur die signifikanten Leerzeichen eines XML-Literals, wenn er erstellt ein [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Objekt.</span><span class="sxs-lookup"><span data-stu-id="91d3b-103">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object.</span></span> <span data-ttu-id="91d3b-104">Bedeutungslose Leerzeichen werden nicht übernommen.</span><span class="sxs-lookup"><span data-stu-id="91d3b-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="91d3b-105">Signifikante und nicht signifikante Leerraum</span><span class="sxs-lookup"><span data-stu-id="91d3b-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="91d3b-106">Leerzeichen in XML-Literalen sind nur in drei Bereichen signifikant:</span><span class="sxs-lookup"><span data-stu-id="91d3b-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="91d3b-107">Wenn sie in einem Attributwert befinden.</span><span class="sxs-lookup"><span data-stu-id="91d3b-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="91d3b-108">Wenn sie sind Bestandteil der Textinhalt des Elements, und der Text auch andere Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="91d3b-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="91d3b-109">Wenn sie in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.</span><span class="sxs-lookup"><span data-stu-id="91d3b-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="91d3b-110">Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt Sie nicht der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] -Objekt für das Literal.</span><span class="sxs-lookup"><span data-stu-id="91d3b-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="91d3b-111">Um nicht signifikanter Leerraum in einem XML-literal einschließen möchten, verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit den Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="91d3b-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91d3b-112">Wenn die `xml:space` Attribut in einem XML-Elementliteral, erscheint die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] schließt der Compiler das Attribut in der <xref:System.Xml.Linq.XElement>Objekt hinzufügen können, aber dieses Attribut ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="91d3b-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="91d3b-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="91d3b-113">Examples</span></span>  
 <span data-ttu-id="91d3b-114">Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere.</span><span class="sxs-lookup"><span data-stu-id="91d3b-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="91d3b-115">Beide Elemente enthalten Leerzeichen im Textinhalt.</span><span class="sxs-lookup"><span data-stu-id="91d3b-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="91d3b-116">Die Leerzeichen im äußeren Element ist unbedeutend, da er nur Leerzeichen und ein XML-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="91d3b-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="91d3b-117">Der Leerraum in der inneren Elements ist wichtig, da er Leerzeichen und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="91d3b-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 <span data-ttu-id="91d3b-118">[!code-vb[VbXMLSamples&#29;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="91d3b-118">[!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]</span></span>  
  
 <span data-ttu-id="91d3b-119">Beim Ausführen zeigt dieser Code den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="91d3b-119">When run, this code displays the following text.</span></span>  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91d3b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91d3b-120">See Also</span></span>  
 [<span data-ttu-id="91d3b-121">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91d3b-121">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
