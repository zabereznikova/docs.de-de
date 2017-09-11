---
title: XML-Achseneigenschaften (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- XML axis properties [Visual Basic]
- Visual Basic code, XML
- XML axis [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 7e400e20-5d1e-4d22-a65c-9df79d5c1621
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4dd15670eed316552f2f02e4536122a6a110542d
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="xml-axis-properties-visual-basic"></a><span data-ttu-id="6c002-102">XML-Achseneigenschaften (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6c002-102">XML Axis Properties (Visual Basic)</span></span>
<span data-ttu-id="6c002-103">In den Themen in diesem Abschnitt dokumentiert die Syntax des XML-Achseneigenschaften in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c002-103">The topics in this section document the syntax of XML axis properties in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="6c002-104">Die XML-Achseneigenschaften erleichtern die XML-Daten direkt im Code zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6c002-104">The XML axis properties make it easy to access XML directly in your code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c002-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6c002-105">In This Section</span></span>  
  
|<span data-ttu-id="6c002-106">Thema</span><span class="sxs-lookup"><span data-stu-id="6c002-106">Topic</span></span>|<span data-ttu-id="6c002-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6c002-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6c002-108">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c002-108">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="6c002-109">Beschreibt die Attribute den Zugriff auf ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6c002-109">Describes how to access the attributes of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="6c002-110">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c002-110">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="6c002-111">Beschreibt das Zugreifen auf die untergeordneten Elemente ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6c002-111">Describes how to access the children of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="6c002-112">XML-Nachfolger-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c002-112">XML Descendant Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="6c002-113">Beschreibt das Zugreifen auf den nachfolgenden Werten einer <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6c002-113">Describes how to access the descendants of an <xref:System.Xml.Linq.XElement> object.</span></span>|  
|[<span data-ttu-id="6c002-114">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c002-114">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="6c002-115">Beschreibt, wie Zugriff auf einzelne Elemente in einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6c002-115">Describes how to access individual elements in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
|[<span data-ttu-id="6c002-116">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6c002-116">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)|<span data-ttu-id="6c002-117">Beschreibt das Zugreifen auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6c002-117">Describes how to access the value of the first element of a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c002-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c002-118">See Also</span></span>  
 [<span data-ttu-id="6c002-119">XML</span><span class="sxs-lookup"><span data-stu-id="6c002-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
