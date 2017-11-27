---
title: 'Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a07e9645-b45b-403b-b698-f652f904c7d2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 934559b5c27d243930c191dd3d601fbf8c5beb65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-visual-basic"></a><span data-ttu-id="5ad7c-102">Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ad7c-102">How to: Retrieve a Collection of Attributes (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5ad7c-103">Dieses Thema enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="5ad7c-103">This topic introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="5ad7c-104">Diese Methode ruft die Attribute eines Elements ab.</span><span class="sxs-lookup"><span data-stu-id="5ad7c-104">This method retrieves the attributes of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ad7c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5ad7c-105">Example</span></span>  
 <span data-ttu-id="5ad7c-106">Im folgenden Beispiel wird gezeigt, wie die Auflistung von Attributen eines Elements durchlaufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ad7c-106">The following example shows how to iterate through the collection of attributes of an element.</span></span>  
  
```vb  
Dim val = _  
    <Value ID="1243" Type="int" ConvertableTo="double">100</Value>  
Dim listOfAttributes As IEnumerable(Of XAttribute) = _  
    From att In val.Attributes() _  
    Select att  
For Each att As XAttribute In listOfAttributes  
    Console.WriteLine(att)  
Next  
```  
  
 <span data-ttu-id="5ad7c-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="5ad7c-107">This code produces the following output:</span></span>  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a><span data-ttu-id="5ad7c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ad7c-108">See Also</span></span>  
 [<span data-ttu-id="5ad7c-109">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ad7c-109">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
