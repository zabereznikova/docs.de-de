---
title: Erweiterungsindexereigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
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
ms.openlocfilehash: 71c16d3f1b93647154bdead4a85d1117b5f6c463
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="03a0e-102">Erweiterungsindexereigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03a0e-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="03a0e-103">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="03a0e-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03a0e-104">Syntax</span></span>  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="03a0e-105">Teile</span><span class="sxs-lookup"><span data-stu-id="03a0e-105">Parts</span></span>  
  
|<span data-ttu-id="03a0e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="03a0e-106">Term</span></span>|<span data-ttu-id="03a0e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="03a0e-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="03a0e-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03a0e-108">Required.</span></span> <span data-ttu-id="03a0e-109">Eine abfragbare Auflistung.</span><span class="sxs-lookup"><span data-stu-id="03a0e-109">A queryable collection.</span></span> <span data-ttu-id="03a0e-110">D. h. eine Auflistung, die implementiert <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="03a0e-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="03a0e-111">(</span><span class="sxs-lookup"><span data-stu-id="03a0e-111">(</span></span>|<span data-ttu-id="03a0e-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03a0e-112">Required.</span></span> <span data-ttu-id="03a0e-113">Kennzeichnet den Anfang der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03a0e-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="03a0e-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03a0e-114">Required.</span></span> <span data-ttu-id="03a0e-115">Ein Ganzzahlausdruck, der die nullbasierte Position eines Elements der Auflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="03a0e-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="03a0e-116">)</span><span class="sxs-lookup"><span data-stu-id="03a0e-116">)</span></span>|<span data-ttu-id="03a0e-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03a0e-117">Required.</span></span> <span data-ttu-id="03a0e-118">Kennzeichnet das Ende der Indexereigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03a0e-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="03a0e-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="03a0e-119">Return Value</span></span>  
 <span data-ttu-id="03a0e-120">Das Objekt aus der angegebenen Position in der Auflistung oder `Nothing` , wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="03a0e-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03a0e-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03a0e-121">Remarks</span></span>  
 <span data-ttu-id="03a0e-122">Sie können die Erweiterungsindexereigenschaft Zugriff auf einzelne Elemente in einer Auflistung verwenden.</span><span class="sxs-lookup"><span data-stu-id="03a0e-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="03a0e-123">Diese Indexereigenschaft wird normalerweise für die Ausgabe der XML-Achseneigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="03a0e-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="03a0e-124">Die XML Child und untergeordnete XML-Achseneigenschaften Auflistungen von zurückgeben <xref:System.Xml.Linq.XElement>Objekte oder ein Attributwert.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="03a0e-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="03a0e-125">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert Indexer-Erweiterungseigenschaften in Aufrufe an die`ElementAtOrDefault` Methode.</span><span class="sxs-lookup"><span data-stu-id="03a0e-125">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts extension indexer properties to calls to the`ElementAtOrDefault` method.</span></span> <span data-ttu-id="03a0e-126">Im Gegensatz zu einem Array-Indexer die`ElementAtOrDefault` -Methode gibt `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="03a0e-126">Unlike an array indexer, the`ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="03a0e-127">Dieses Verhalten ist nützlich, wenn Sie die Anzahl der Elemente in einer Auflistung nicht leicht ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="03a0e-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="03a0e-128">Diese Indexereigenschaft ist wie eine Erweiterungseigenschaft für Auflistungen, implementieren <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Linq.IQueryable%601>: wird nur verwendet, wenn die Auflistung nicht über einen Indexer oder eine Standardeigenschaft verfügt.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="03a0e-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="03a0e-129">Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XAttribute>Objekte, können Sie den XML-Code `Value` Eigenschaft.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="03a0e-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="03a0e-130">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="03a0e-130">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a0e-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03a0e-131">Example</span></span>  
 <span data-ttu-id="03a0e-132">Im folgenden Beispiel wird veranschaulicht, wie der Erweiterungsindexer auf den zweiten untergeordneten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="03a0e-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="03a0e-133">Die Auflistung erfolgt über die Child Axis-Eigenschaft, die alle untergeordneten Elemente mit dem Namen abruft `phone` in den `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="03a0e-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 <span data-ttu-id="03a0e-134">[!code-vb[VbXMLSamples&#24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="03a0e-134">[!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]</span></span>  
  
 <span data-ttu-id="03a0e-135">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="03a0e-135">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="03a0e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03a0e-136">See Also</span></span>  
 <span data-ttu-id="03a0e-137"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="03a0e-137"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="03a0e-138"> [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="03a0e-138"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="03a0e-139"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="03a0e-139"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="03a0e-140"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="03a0e-140"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="03a0e-141"> [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span><span class="sxs-lookup"><span data-stu-id="03a0e-141"> [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)</span></span>
