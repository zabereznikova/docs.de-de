---
title: Leerzeichen in XML-Literalen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d8587abb98fe33ab2c5a0cef6cea76049a00909e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-in-xml-literals-visual-basic"></a><span data-ttu-id="83602-102">Leerzeichen in XML-Literalen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83602-102">White Space in XML Literals (Visual Basic)</span></span>
<span data-ttu-id="83602-103">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler bindet nur die signifikanter Leerraumzeichen aus einem XML-Literal, wenn er erstellt eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt.</span><span class="sxs-lookup"><span data-stu-id="83602-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler incorporates only the significant white space characters from an XML literal when it creates a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object.</span></span> <span data-ttu-id="83602-104">Bedeutungslose Leerzeichen sind nicht integriert.</span><span class="sxs-lookup"><span data-stu-id="83602-104">The insignificant white space characters are not incorporated.</span></span>  
  
## <a name="significant-and-insignificant-white-space"></a><span data-ttu-id="83602-105">Signifikante und nicht signifikante Leerraum</span><span class="sxs-lookup"><span data-stu-id="83602-105">Significant and Insignificant White Space</span></span>  
 <span data-ttu-id="83602-106">Leerzeichen in XML-Literalen sind nur in drei Bereichen signifikant:</span><span class="sxs-lookup"><span data-stu-id="83602-106">White space characters in XML literals are significant in only three areas:</span></span>  
  
-   <span data-ttu-id="83602-107">Wenn sie in einem Attributwert befinden.</span><span class="sxs-lookup"><span data-stu-id="83602-107">When they are in an attribute value.</span></span>  
  
-   <span data-ttu-id="83602-108">Wenn sie sind Bestandteil der Textinhalt des Elements und der Text auch andere Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="83602-108">When they are part of an element's text content and the text also contains other characters.</span></span>  
  
-   <span data-ttu-id="83602-109">Wenn sie in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.</span><span class="sxs-lookup"><span data-stu-id="83602-109">When they are in an embedded expression for an element's text content.</span></span>  
  
 <span data-ttu-id="83602-110">Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt dann nicht in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für das Literal.</span><span class="sxs-lookup"><span data-stu-id="83602-110">Otherwise, the compiler treats white space characters as insignificant and does not include then in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] object for the literal.</span></span>  
  
 <span data-ttu-id="83602-111">Verwenden Sie einen eingebetteten Ausdruck, der ein Zeichenfolgenliteral mit den Leerzeichen enthält, für die Einbeziehung der nicht signifikanten Leerraum in einem XML-literal.</span><span class="sxs-lookup"><span data-stu-id="83602-111">To include insignificant white space in an XML literal, use an embedded expression that contains a string literal with the white space.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="83602-112">Wenn die `xml:space` Attribut in einem XML-Elementliteral, erscheint die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] schließt der Compiler das Attribut in der <xref:System.Xml.Linq.XElement> Objekt hinzufügen können, aber dieses Attribut ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.</span><span class="sxs-lookup"><span data-stu-id="83602-112">If the `xml:space` attribute appears in an XML element literal, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler includes the attribute in the <xref:System.Xml.Linq.XElement> object, but adding this attribute does not change how the compiler treats white space.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="83602-113">Beispiele</span><span class="sxs-lookup"><span data-stu-id="83602-113">Examples</span></span>  
 <span data-ttu-id="83602-114">Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere.</span><span class="sxs-lookup"><span data-stu-id="83602-114">The following example contains two XML elements, outer and inner.</span></span> <span data-ttu-id="83602-115">Beide Elemente werden Leerzeichen in ihre Text-Inhalt enthalten.</span><span class="sxs-lookup"><span data-stu-id="83602-115">Both elements contain white space in their text content.</span></span> <span data-ttu-id="83602-116">Der Leerraum in der äußeren Elements ist nicht signifikante, da sie nur aus Leerzeichen und ein XML-Element enthält.</span><span class="sxs-lookup"><span data-stu-id="83602-116">The white space in the outer element is insignificant because it contains only white space and an XML element.</span></span> <span data-ttu-id="83602-117">Der Leerraum in der inneren Elements ist wichtig, weil er Leerzeichen und Text enthält.</span><span class="sxs-lookup"><span data-stu-id="83602-117">The white space in the inner element is significant because it contains white space and text.</span></span>  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 <span data-ttu-id="83602-118">Wenn ausführen, zeigt dieser Code den folgenden Text an.</span><span class="sxs-lookup"><span data-stu-id="83602-118">When run, this code displays the following text.</span></span>  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83602-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83602-119">See Also</span></span>  
 [<span data-ttu-id="83602-120">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="83602-120">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
