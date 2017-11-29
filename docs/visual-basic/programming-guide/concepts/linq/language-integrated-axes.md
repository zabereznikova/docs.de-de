---
title: Sprachintegrierte Achsen in Visual Basic (LINQ to XML)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d648ba7c8710f73c4aeb8dad3983f219c5fe1815
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="ad4b4-102">Sprachintegrierte Achsen in Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="ad4b4-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="ad4b4-103">In diesem Abschnitt wird beschrieben, Funktionen, die direkt in die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Sprache zu erleichtern, die XML-Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-103">This section describes features built directly into the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="ad4b4-104">Diese integrierten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Achsen kommen in vielen der Beispiele in der LINQ to XML-Dokumentation zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad4b4-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ad4b4-105">In This Section</span></span>  
  
|<span data-ttu-id="ad4b4-106">Thema</span><span class="sxs-lookup"><span data-stu-id="ad4b4-106">Topic</span></span>|<span data-ttu-id="ad4b4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ad4b4-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="ad4b4-108">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="ad4b4-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="ad4b4-109">Bietet Zugriff auf die untergeordneten Elemente eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts, einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder einer Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="ad4b4-110">Diese Achse entspricht der <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="ad4b4-111">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="ad4b4-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="ad4b4-112">Bietet Zugriff auf die Nachfolger eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts oder einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ad4b4-113">Diese Achse entspricht der <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="ad4b4-114">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="ad4b4-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="ad4b4-115">Bietet Zugriff auf ein Attribut eines <xref:System.Xml.Linq.XElement>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ad4b4-116">Diese Achse entspricht annähernd der <xref:System.Xml.Linq.XElement.Attribute%2A>-Achse.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="ad4b4-117">Im Unterschied zur <xref:System.Xml.Linq.XElement.Attribute%2A>-Achse gibt sie den Wert des Attributs und kein <xref:System.Xml.Linq.XAttribute>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="ad4b4-118">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="ad4b4-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="ad4b4-119">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ad4b4-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ad4b4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad4b4-120">See Also</span></span>  
 [<span data-ttu-id="ad4b4-121">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ad4b4-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
