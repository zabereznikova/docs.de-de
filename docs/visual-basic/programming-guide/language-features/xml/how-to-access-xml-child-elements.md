---
title: 'Gewusst wie: Zugriff auf untergeordnete XML-Elemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 32bdb1ba476a954bdad1f23c3ecc6129c90ccaac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347175"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="e743a-102">Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e743a-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="e743a-103">Dieses Beispiel zeigt, wie Sie mithilfe einer untergeordneten Achsen Eigenschaft auf alle untergeordneten XML-Elemente zugreifen können, die einen angegebenen Namen in einem XML-Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e743a-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="e743a-104">Insbesondere wird die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwendet, um den Wert des ersten Elements in der Auflistung zu erhalten, das die Eigenschaft `name` untergeordneter Achse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e743a-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="e743a-105">Die Eigenschaft `name` untergeordneter Achse ruft alle untergeordneten Elemente mit dem Namen `phone` im `contact` Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="e743a-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="e743a-106">In diesem Beispiel wird auch die Eigenschaft `phone` untergeordneter Achse verwendet, um auf alle untergeordneten Elemente mit dem Namen `phone` zuzugreifen, die im `contact`-Objekt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e743a-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e743a-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e743a-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="e743a-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="e743a-108">Compile the code</span></span>  
 <span data-ttu-id="e743a-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e743a-109">This example requires:</span></span>  
  
- <span data-ttu-id="e743a-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="e743a-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e743a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e743a-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e743a-112">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="e743a-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="e743a-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e743a-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="e743a-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e743a-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="e743a-115">XML</span><span class="sxs-lookup"><span data-stu-id="e743a-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
