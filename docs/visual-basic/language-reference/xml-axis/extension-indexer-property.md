---
title: Erweiterungsindexereigenschaft (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="16125-102">Erweiterungsindexereigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16125-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="16125-103">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="16125-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16125-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16125-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="16125-105">Teile</span><span class="sxs-lookup"><span data-stu-id="16125-105">Parts</span></span>  
  
|<span data-ttu-id="16125-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="16125-106">Term</span></span>|<span data-ttu-id="16125-107">Definition</span><span class="sxs-lookup"><span data-stu-id="16125-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="16125-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16125-108">Required.</span></span> <span data-ttu-id="16125-109">Eine abfragbare Sammlung.</span><span class="sxs-lookup"><span data-stu-id="16125-109">A queryable collection.</span></span> <span data-ttu-id="16125-110">D. h. eine Auflistung mit Implementierung <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="16125-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="16125-111">(</span><span class="sxs-lookup"><span data-stu-id="16125-111">(</span></span>|<span data-ttu-id="16125-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16125-112">Required.</span></span> <span data-ttu-id="16125-113">Kennzeichnet den Anfang der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="16125-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="16125-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16125-114">Required.</span></span> <span data-ttu-id="16125-115">Ein ganzzahliger Ausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="16125-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="16125-116">)</span><span class="sxs-lookup"><span data-stu-id="16125-116">)</span></span>|<span data-ttu-id="16125-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16125-117">Required.</span></span> <span data-ttu-id="16125-118">Kennzeichnet das Ende der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="16125-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="16125-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16125-119">Return Value</span></span>  
 <span data-ttu-id="16125-120">Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="16125-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16125-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16125-121">Remarks</span></span>  
 <span data-ttu-id="16125-122">Sie können die Erweiterungsindexereigenschaft Zugriff auf einzelne Elemente in einer Auflistung verwenden.</span><span class="sxs-lookup"><span data-stu-id="16125-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="16125-123">Diese Indexereigenschaft wird in der Regel auf die Ausgabe der XML-Achseneigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="16125-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="16125-124">Die untergeordnete XML- und die untergeordnete XML-Achseneigenschaften zurückgeben Auflistungen von <xref:System.Xml.Linq.XElement> Objekte oder ein Attributwert.</span><span class="sxs-lookup"><span data-stu-id="16125-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="16125-125">Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler konvertiert Indexer Erweiterungseigenschaften in Aufrufe an die `ElementAtOrDefault` Methode.</span><span class="sxs-lookup"><span data-stu-id="16125-125">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="16125-126">Im Gegensatz zu einer konstantenarrayindizierung der `ElementAtOrDefault` -Methode zurückkehrt `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="16125-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="16125-127">Dieses Verhalten ist nützlich, wenn Sie einfach die Anzahl der Elemente in einer Auflistung nicht bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="16125-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="16125-128">Diese Indexereigenschaft ist wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>: wird verwendet, nur, wenn die Auflistung nicht über einen Indexer oder eine Standardeigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="16125-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="16125-129">Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> Objekte aufweist, können Sie den XML-Code `Value` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="16125-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="16125-130">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="16125-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="16125-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16125-131">Example</span></span>  
 <span data-ttu-id="16125-132">Das folgende Beispiel zeigt, wie Sie die Erweiterung Indexer zu verwenden, auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16125-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="16125-133">Die Auflistung erfolgt mithilfe der untergeordneten Achseneigenschaft, der alle untergeordneten Elemente mit dem Namen abgerufen `phone` in die `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="16125-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="16125-134">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="16125-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="16125-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16125-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="16125-136">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="16125-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="16125-137">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="16125-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="16125-138">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16125-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="16125-139">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="16125-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
