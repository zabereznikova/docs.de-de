---
title: Leerzeichen in XML-Literalen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 60ee90c69aeda38f95107a6043801a4994972079
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245158"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="a2576-102">Leerzeichen in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2576-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="a2576-103">Visual Basic-Compiler bindet nur die signifikanten Leerzeichen aus einem XML-Literal, wenn er erstellt eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt.</span><span class="sxs-lookup"><span data-stu-id="a2576-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="a2576-104">Bedeutungslose Leerzeichen sind nicht integriert.</span><span class="sxs-lookup"><span data-stu-id="a2576-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="a2576-105">Erhebliche und nicht signifikanter Leerraum</span><span class="sxs-lookup"><span data-stu-id="a2576-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="a2576-106">Leerzeichen in XML-Literale sind wichtig, nur in drei Bereichen:</span><span class="sxs-lookup"><span data-stu-id="a2576-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="a2576-107">Wenn sie sich in einem Attributwert sind.</span><span class="sxs-lookup"><span data-stu-id="a2576-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="a2576-108">Wenn sie sind Bestandteil des Textinhalts eines Elements und der Text auch andere Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="a2576-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="a2576-109">Wenn sie sich in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.</span><span class="sxs-lookup"><span data-stu-id="a2576-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="a2576-110">Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt Sie nicht der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für das Literal.</span><span class="sxs-lookup"><span data-stu-id="a2576-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="a2576-111">Um nicht signifikante Leerraum in einem XML-literal einschließen möchten, verwenden Sie einen eingebetteten Ausdruck an, der ein Zeichenfolgenliteral mit den Leerraum enthält.</span><span class="sxs-lookup"><span data-stu-id="a2576-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2576-112">Wenn die `xml:space` Attribut wird in einem XML-Elementliteral angezeigt, in Visual Basic-Compiler umfasst das Attribut in der <xref:System.Xml.Linq.XElement> -Objekt, aber das Hinzufügen dieses Attributs ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="a2576-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a2576-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a2576-113">Examples</span></span>  
 <span data-ttu-id="a2576-114">Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere.</span><span class="sxs-lookup"><span data-stu-id="a2576-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="a2576-115">Beide Elemente enthalten Leerzeichen in ihren Textinhalt.</span><span class="sxs-lookup"><span data-stu-id="a2576-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="a2576-116">Der Leerraum in das äußere Element ist unbedeutend, da sie nur aus Leerzeichen und ein XML-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="a2576-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="a2576-117">Der Leerraum in das innere Element ist von Bedeutung, da er Leerzeichen und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="a2576-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="a2576-118">Wenn ausführen, zeigt dieser Code den folgenden Text ein.</span><span class="sxs-lookup"><span data-stu-id="a2576-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2576-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2576-119">See Also</span></span>  
 [<span data-ttu-id="a2576-120">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a2576-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
