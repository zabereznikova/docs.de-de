---
title: Leerzeichen in XML-Literalen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: f72dcc25b158d793850069e5cc32c3a3c02fad17
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939213"
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="247bc-102">Leerzeichen in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="247bc-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="247bc-103">Der Visual Basic-Compiler bindet nur die signifikanten leer Raum Zeichen aus einem XML-Literalzeichen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ein, wenn ein-Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="247bc-103">The Visual Basic compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="247bc-104">Die unbedeutenden Leerzeichen sind nicht eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="247bc-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="247bc-105">Signifikanter und unbedeutender Leerraum</span><span class="sxs-lookup"><span data-stu-id="247bc-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="247bc-106">Leerzeichen in XML-Literalen sind nur in drei Bereichen wichtig:</span><span class="sxs-lookup"><span data-stu-id="247bc-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
- <span data-ttu-id="247bc-107">Wenn Sie einen Attribut Wert haben.</span><span class="sxs-lookup"><span data-stu-id="247bc-107">When they are in an attribute value.</span></span>  
  
- <span data-ttu-id="247bc-108">Wenn Sie Teil des Text Inhalts eines Elements sind und der Text auch andere Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="247bc-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
- <span data-ttu-id="247bc-109">Wenn Sie in einem eingebetteten Ausdruck für den Text Inhalt eines Elements enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="247bc-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="247bc-110">Andernfalls behandelt der Compiler leer Raum Zeichen als unbedeutend und schließt dann nicht in das [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] -Objekt für das Literale ein.</span><span class="sxs-lookup"><span data-stu-id="247bc-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="247bc-111">Verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit dem Leerraum enthält, um unbedeutende Leerzeichen in ein XML-Literalformat einzubeziehen</span><span class="sxs-lookup"><span data-stu-id="247bc-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="247bc-112">Wenn das `xml:space` Attribut in einem XML-Elementliterals angezeigt wird, schließt der Visual Basic Compiler das <xref:System.Xml.Linq.XElement> -Attribut in das-Objekt ein, aber durch das Hinzufügen dieses Attributs wird nicht geändert, wie der Compiler Leerraum behandelt.</span><span class="sxs-lookup"><span data-stu-id="247bc-112">If the `xml:space` attribute appears in an XML element literal, the Visual Basic compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="247bc-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="247bc-113">Examples</span></span>  
 <span data-ttu-id="247bc-114">Das folgende Beispiel enthält zwei XML-Elemente (Outer und Inner).</span><span class="sxs-lookup"><span data-stu-id="247bc-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="247bc-115">Beide Elemente enthalten Leerraum in Ihren Text Inhalt.</span><span class="sxs-lookup"><span data-stu-id="247bc-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="247bc-116">Der Leerraum im äußeren Element ist unerheblich, da er nur Leerraum und ein XML-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="247bc-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="247bc-117">Der Leerraum im Inneren Element ist wichtig, da er Leerzeichen und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="247bc-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 <span data-ttu-id="247bc-118">Wenn Sie ausführen, wird in diesem Code der folgende Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="247bc-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="247bc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="247bc-119">See also</span></span>

- [<span data-ttu-id="247bc-120">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="247bc-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
