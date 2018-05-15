---
title: 'Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="ae917-102">Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae917-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="ae917-103">Dieses Beispiel zeigt, wie Sie eine descendant-Achse-Eigenschaft verwenden, um Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und in ein XML-Element enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="ae917-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="ae917-104">Insbesondere verwendet die `Value` Eigenschaft, um den Wert des ersten Elements in der Auflistung abrufen, die die `name` -Achseneigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ae917-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="ae917-105">Die `name` Nachfolgerachseneigenschaft Ruft alle Elemente, die mit dem Namen `name` enthalten sind die `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ae917-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="ae917-106">Dieses Beispiel verwendet außerdem die `phone` Nachfolgerachseneigenschaft auf allen untergeordneten Elementen mit dem Namen `phone` enthalten sind die `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="ae917-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae917-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae917-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae917-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ae917-108">Compiling the Code</span></span>  
 <span data-ttu-id="ae917-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ae917-109">This example requires:</span></span>  
  
-   <span data-ttu-id="ae917-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="ae917-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae917-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae917-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ae917-112">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="ae917-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="ae917-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ae917-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="ae917-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ae917-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="ae917-115">XML</span><span class="sxs-lookup"><span data-stu-id="ae917-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
