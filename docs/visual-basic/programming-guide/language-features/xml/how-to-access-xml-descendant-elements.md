---
title: 'Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b3b6c8ac96bd18a379804b83f3ab3e48a5b0c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="43a43-102">Gewusst wie: Zugreifen auf XML-Nachfolgerelemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43a43-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="43a43-103">Dieses Beispiel zeigt, wie Sie eine descendant-Achse-Eigenschaft verwenden, um Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und in ein XML-Element enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="43a43-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="43a43-104">Insbesondere verwendet die `Value` Eigenschaft, um den Wert des ersten Elements in der Auflistung abrufen, die die `name` -Achseneigenschaft zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="43a43-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="43a43-105">Die `name` Nachfolgerachseneigenschaft Ruft alle Elemente, die mit dem Namen `name` enthalten sind die `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="43a43-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="43a43-106">Dieses Beispiel verwendet außerdem die `phone` Nachfolgerachseneigenschaft auf allen untergeordneten Elementen mit dem Namen `phone` enthalten sind die `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="43a43-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43a43-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43a43-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43a43-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="43a43-108">Compiling the Code</span></span>  
 <span data-ttu-id="43a43-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="43a43-109">This example requires:</span></span>  
  
-   <span data-ttu-id="43a43-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="43a43-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43a43-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43a43-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="43a43-112">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="43a43-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="43a43-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="43a43-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="43a43-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="43a43-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="43a43-115">XML</span><span class="sxs-lookup"><span data-stu-id="43a43-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
