---
title: 'Vorgehensweise: Zugreifen auf XML-Nachfolgerelemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: dcbaf1f9022d86f40a90ef6a1e0033f627caeef2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058208"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="79816-102">Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="79816-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>

<span data-ttu-id="79816-103">In diesem Beispiel wird gezeigt, wie Sie mithilfe einer Nachfolger Achsen Eigenschaft auf alle XML-Elemente zugreifen können, die über einen angegebenen Namen verfügen und in einem XML-Element enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="79816-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="79816-104">Insbesondere wird die-Eigenschaft verwendet `Value` , um den Wert des ersten Elements in der Auflistung zu erhalten, das von der Eigenschaft der nachfolgenden `name` Achse zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="79816-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="79816-105">Die Eigenschaft der nachfolgenden `name` Achse ruft alle Elemente mit dem Namen ab `name` , die im-Objekt enthalten sind `contacts` .</span><span class="sxs-lookup"><span data-stu-id="79816-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="79816-106">In diesem Beispiel wird auch die Eigenschaft für die nachfolgende `phone` Achse verwendet, um auf alle im-Objekt enthaltenen Nachfolger Elemente mit dem Namen zuzugreifen `phone` `contacts` .</span><span class="sxs-lookup"><span data-stu-id="79816-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79816-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79816-107">Example</span></span>  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="79816-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="79816-108">Compile the code</span></span>  

 <span data-ttu-id="79816-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="79816-109">This example requires:</span></span>  
  
- <span data-ttu-id="79816-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="79816-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79816-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79816-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="79816-112">XML Descendant Axis Property</span><span class="sxs-lookup"><span data-stu-id="79816-112">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="79816-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="79816-113">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="79816-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="79816-114">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="79816-115">XML</span><span class="sxs-lookup"><span data-stu-id="79816-115">XML</span></span>](index.md)
