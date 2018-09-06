---
title: Erweiterungsindexereigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: ab9eacc3fb3796139d8ed8382146a4a6c2b28a97
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43803960"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="2fa55-102">Erweiterungsindexereigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fa55-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="2fa55-103">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2fa55-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa55-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fa55-104">Syntax</span></span>  
  
```  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="2fa55-105">Teile</span><span class="sxs-lookup"><span data-stu-id="2fa55-105">Parts</span></span>  
  
|<span data-ttu-id="2fa55-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="2fa55-106">Term</span></span>|<span data-ttu-id="2fa55-107">Definition</span><span class="sxs-lookup"><span data-stu-id="2fa55-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="2fa55-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa55-108">Required.</span></span> <span data-ttu-id="2fa55-109">Eine abfragbare Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2fa55-109">A queryable collection.</span></span> <span data-ttu-id="2fa55-110">D. h. einer Auflistung mit Implementierung <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="2fa55-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="2fa55-111">(</span><span class="sxs-lookup"><span data-stu-id="2fa55-111">(</span></span>|<span data-ttu-id="2fa55-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa55-112">Required.</span></span> <span data-ttu-id="2fa55-113">Kennzeichnet den Anfang der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2fa55-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="2fa55-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa55-114">Required.</span></span> <span data-ttu-id="2fa55-115">Ein ganzzahliger Ausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="2fa55-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="2fa55-116">)</span><span class="sxs-lookup"><span data-stu-id="2fa55-116">)</span></span>|<span data-ttu-id="2fa55-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa55-117">Required.</span></span> <span data-ttu-id="2fa55-118">Kennzeichnet das Ende der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2fa55-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="2fa55-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2fa55-119">Return Value</span></span>  
 <span data-ttu-id="2fa55-120">Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="2fa55-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa55-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2fa55-121">Remarks</span></span>  
 <span data-ttu-id="2fa55-122">Sie können die Erweiterungseigenschaft für Indexer verwenden, Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="2fa55-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="2fa55-123">Diese Indexereigenschaft wird in der Regel für die Ausgabe der XML-Achseneigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fa55-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="2fa55-124">Die XML-untergeordneten und untergeordnete XML-Achseneigenschaften Auflistungen von zurückgeben <xref:System.Xml.Linq.XElement> Objekte oder einen Attributwert.</span><span class="sxs-lookup"><span data-stu-id="2fa55-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="2fa55-125">Visual Basic-Compiler konvertiert die Erweiterungseigenschaften für Indexer in Aufrufe an die `ElementAtOrDefault` Methode.</span><span class="sxs-lookup"><span data-stu-id="2fa55-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="2fa55-126">Im Gegensatz zu einem Arrayindexer der `ElementAtOrDefault` Methodenrückgabe `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="2fa55-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="2fa55-127">Dies ist hilfreich, wenn Sie einfach die Anzahl der Elemente in einer Auflistung nicht bestimmen können.</span><span class="sxs-lookup"><span data-stu-id="2fa55-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="2fa55-128">Diese Indexereigenschaft wird wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>: Es wird nur verwendet, wenn die Auflistung nicht über einen Indexer oder eine Default-Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="2fa55-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="2fa55-129">Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XAttribute> Objekte aufweist, können Sie den XML-Code `Value` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2fa55-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="2fa55-130">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="2fa55-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fa55-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fa55-131">Example</span></span>  
 <span data-ttu-id="2fa55-132">Das folgende Beispiel zeigt, wie Sie mit der Erweiterungsindexer auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="2fa55-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="2fa55-133">Die Auflistung erfolgt mithilfe einer untergeordneten Achseneigenschaft, in dem alle untergeordneten Elemente, die mit dem Namen abgerufen werden, `phone` in die `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="2fa55-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 <span data-ttu-id="2fa55-134">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="2fa55-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="2fa55-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fa55-135">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="2fa55-136">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="2fa55-136">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="2fa55-137">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="2fa55-137">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="2fa55-138">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fa55-138">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="2fa55-139">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2fa55-139">XML Value Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
