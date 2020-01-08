---
title: 'Gewusst wie: Zugriff auf XML-Nachfolgerelemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347158"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="63086-102">Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63086-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="63086-103">In diesem Beispiel wird gezeigt, wie Sie mithilfe einer Nachfolger Achsen Eigenschaft auf alle XML-Elemente zugreifen können, die über einen angegebenen Namen verfügen und in einem XML-Element enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="63086-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="63086-104">Insbesondere wird die `Value`-Eigenschaft verwendet, um den Wert des ersten Elements in der Auflistung zu erhalten, das die `name` Nachfolger Axis-Eigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="63086-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="63086-105">Die `name` Nachfolger Achsen Eigenschaft ruft alle Elemente mit dem Namen `name` ab, die im `contacts` Objekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="63086-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="63086-106">In diesem Beispiel wird auch die `phone` nachfolgende Achsen Eigenschaft verwendet, um auf alle Nachfolger `phone` zuzugreifen, die im `contacts`-Objekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="63086-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63086-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63086-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="63086-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="63086-108">Compile the code</span></span>  
 <span data-ttu-id="63086-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="63086-109">This example requires:</span></span>  
  
- <span data-ttu-id="63086-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="63086-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63086-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63086-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="63086-112">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="63086-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="63086-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="63086-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="63086-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63086-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="63086-115">XML</span><span class="sxs-lookup"><span data-stu-id="63086-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
