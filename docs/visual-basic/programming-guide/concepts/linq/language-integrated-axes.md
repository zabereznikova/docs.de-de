---
title: Sprachintegrierte Achsen in Visual Basic (LINQ to XML) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7ca88aed0772f4fb93ab561af4bd9a1129cbf3c5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="1c10e-102">Sprachintegrierte Achsen in Visual Basic (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1c10e-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="1c10e-103">Dieser Abschnitt beschreibt Funktionen, die direkt in integriert die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Sprache zu erleichtern, die XML-Daten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c10e-103">This section describes features built directly into the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="1c10e-104">Diese integrierten [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Achsen kommen in vielen der Beispiele in der LINQ to XML-Dokumentation zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="1c10e-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c10e-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1c10e-105">In This Section</span></span>  
  
|<span data-ttu-id="1c10e-106">Thema</span><span class="sxs-lookup"><span data-stu-id="1c10e-106">Topic</span></span>|<span data-ttu-id="1c10e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1c10e-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1c10e-108">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c10e-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="1c10e-109">Bietet Zugriff auf die untergeordneten Elemente eines der folgenden: ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1c10e-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="1c10e-110">Diese Achse entspricht der <xref:System.Xml.Linq.XContainer.Elements%2A>Achse.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="1c10e-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="1c10e-111">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c10e-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="1c10e-112">Bietet Zugriff auf die Nachfolger: ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1c10e-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1c10e-113">Diese Achse entspricht der <xref:System.Xml.Linq.XContainer.Descendants%2A>Achse.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="1c10e-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="1c10e-114">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c10e-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="1c10e-115">Ermöglicht den Zugriff auf ein Attribut des ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1c10e-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="1c10e-116">Diese Achse entspricht annähernd der <xref:System.Xml.Linq.XElement.Attribute%2A>Achse.</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="1c10e-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="1c10e-117">Diese Achse unterscheidet sich von der <xref:System.Xml.Linq.XElement.Attribute%2A>Achse in, dass der Wert des Attributs zurückgegeben wird keine <xref:System.Xml.Linq.XAttribute>Objekt.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="1c10e-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="1c10e-118">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c10e-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="1c10e-119">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1c10e-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c10e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c10e-120">See Also</span></span>  
 [<span data-ttu-id="1c10e-121">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c10e-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
