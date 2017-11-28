---
title: 'Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d3a708b787ad38f08d4673d4003db839f6cf6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="2299f-102">Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2299f-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="2299f-103">Dieses Beispiel zeigt, wie eines untergeordneten Achseneigenschaft auf alle untergeordnete XML-Elemente, die den angegebenen Namen in ein XML-Element aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2299f-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="2299f-104">Insbesondere verwendet die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft rufen Sie den Wert des ersten Elements in der Auflistung, die die `name` untergeordnete Achse Eigenschaft gibt.</span><span class="sxs-lookup"><span data-stu-id="2299f-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="2299f-105">Die `name` Child Axis-Eigenschaft ruft alle untergeordneten Elemente mit dem Namen `phone` in die `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="2299f-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="2299f-106">Dieses Beispiel verwendet außerdem die `phone` Child Axis-Eigenschaft auf alle untergeordneten Elemente mit dem Namen `phone` enthalten sind die `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="2299f-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2299f-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2299f-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2299f-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2299f-108">Compiling the Code</span></span>  
 <span data-ttu-id="2299f-109">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2299f-109">This example requires:</span></span>  
  
-   <span data-ttu-id="2299f-110">Einen Verweis auf den <xref:System.Xml.Linq>-Namespace</span><span class="sxs-lookup"><span data-stu-id="2299f-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2299f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2299f-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2299f-112">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="2299f-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="2299f-113">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2299f-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="2299f-114">Zugreifen auf XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2299f-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="2299f-115">XML</span><span class="sxs-lookup"><span data-stu-id="2299f-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
