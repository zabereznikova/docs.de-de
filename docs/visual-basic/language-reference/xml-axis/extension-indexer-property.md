---
title: Erweiterungsindexereigenschaft
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: c91061d49e22e648b7bf75a812071b352793abcb
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401341"
---
# <a name="extension-indexer-property-visual-basic"></a><span data-ttu-id="1afc7-102">Erweiterungsindexereigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1afc7-102">Extension Indexer Property (Visual Basic)</span></span>
<span data-ttu-id="1afc7-103">Bietet Zugriff auf einzelne Elemente in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1afc7-103">Provides access to individual elements in a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1afc7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1afc7-104">Syntax</span></span>  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a><span data-ttu-id="1afc7-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1afc7-105">Parts</span></span>  
  
|<span data-ttu-id="1afc7-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1afc7-106">Term</span></span>|<span data-ttu-id="1afc7-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1afc7-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="1afc7-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1afc7-108">Required.</span></span> <span data-ttu-id="1afc7-109">Eine abfragbare Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1afc7-109">A queryable collection.</span></span> <span data-ttu-id="1afc7-110">Das heißt, eine Auflistung, die <xref:System.Collections.Generic.IEnumerable%601> oder implementiert <xref:System.Linq.IQueryable%601> .</span><span class="sxs-lookup"><span data-stu-id="1afc7-110">That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>|  
|<span data-ttu-id="1afc7-111">(</span><span class="sxs-lookup"><span data-stu-id="1afc7-111">(</span></span>|<span data-ttu-id="1afc7-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1afc7-112">Required.</span></span> <span data-ttu-id="1afc7-113">Gibt den Anfang der Indexer-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1afc7-113">Denotes the start of the indexer property.</span></span>|  
|`index`|<span data-ttu-id="1afc7-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1afc7-114">Required.</span></span> <span data-ttu-id="1afc7-115">Ein ganzzahliger Ausdruck, der die null basierte Position eines Elements der Auflistung angibt.</span><span class="sxs-lookup"><span data-stu-id="1afc7-115">An integer expression that specifies the zero-based position of an element of the collection.</span></span>|  
|<span data-ttu-id="1afc7-116">)</span><span class="sxs-lookup"><span data-stu-id="1afc7-116">)</span></span>|<span data-ttu-id="1afc7-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1afc7-117">Required.</span></span> <span data-ttu-id="1afc7-118">Bezeichnet das Ende der Indexer-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1afc7-118">Denotes the end of the indexer property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="1afc7-119">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1afc7-119">Return Value</span></span>  
 <span data-ttu-id="1afc7-120">Das Objekt aus der angegebenen Position in der Auflistung oder, `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="1afc7-120">The object from the specified location in the collection, or `Nothing` if the index is out of range.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1afc7-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1afc7-121">Remarks</span></span>  
 <span data-ttu-id="1afc7-122">Mit der Eigenschaft Erweiterungsindexer können Sie auf einzelne Elemente in einer Auflistung zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1afc7-122">You can use the extension indexer property to access individual elements in a collection.</span></span> <span data-ttu-id="1afc7-123">Diese Indexer-Eigenschaft wird in der Regel in der Ausgabe von XML-Achsen Eigenschaften verwendet.</span><span class="sxs-lookup"><span data-stu-id="1afc7-123">This indexer property is typically used on the output of XML axis properties.</span></span> <span data-ttu-id="1afc7-124">Die Eigenschaften der untergeordneten XML-und XML-Nachfolger Achse geben Auflistungen von <xref:System.Xml.Linq.XElement> Objekten oder einen Attribut Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="1afc7-124">The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.</span></span>  
  
 <span data-ttu-id="1afc7-125">Der Visual Basic-Compiler konvertiert Erweiterungs Indexer-Eigenschaften in Aufrufe der- `ElementAtOrDefault` Methode.</span><span class="sxs-lookup"><span data-stu-id="1afc7-125">The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method.</span></span> <span data-ttu-id="1afc7-126">Anders als bei einem Arrayindexer `ElementAtOrDefault` gibt die Methode zurück, `Nothing` Wenn der Index außerhalb des gültigen Bereichs liegt.</span><span class="sxs-lookup"><span data-stu-id="1afc7-126">Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range.</span></span> <span data-ttu-id="1afc7-127">Dieses Verhalten ist nützlich, wenn Sie die Anzahl der Elemente in einer Auflistung nicht einfach ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="1afc7-127">This behavior is useful when you cannot easily determine the number of elements in a collection.</span></span>  
  
 <span data-ttu-id="1afc7-128">Diese Indexer-Eigenschaft ist wie eine Erweiterungs Eigenschaft für Auflistungen, die <xref:System.Collections.Generic.IEnumerable%601> oder implementieren <xref:System.Linq.IQueryable%601> : Sie wird nur verwendet, wenn die Auflistung keinen Indexer oder keine Standard Eigenschaft aufweist.</span><span class="sxs-lookup"><span data-stu-id="1afc7-128">This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.</span></span>  
  
 <span data-ttu-id="1afc7-129">Um auf den Wert des ersten Elements in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten oder- <xref:System.Xml.Linq.XAttribute> Objekten zuzugreifen, können Sie die XML- `Value` Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="1afc7-129">To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property.</span></span> <span data-ttu-id="1afc7-130">Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="1afc7-130">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1afc7-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1afc7-131">Example</span></span>  
 <span data-ttu-id="1afc7-132">Im folgenden Beispiel wird gezeigt, wie der Erweiterungsindexer zum Zugreifen auf den zweiten untergeordneten Knoten in einer Auflistung von-Objekten verwendet wird <xref:System.Xml.Linq.XElement> .</span><span class="sxs-lookup"><span data-stu-id="1afc7-132">The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1afc7-133">Der Zugriff auf die Auflistung erfolgt mithilfe der untergeordneten Achsen Eigenschaft, die alle untergeordneten Elemente mit dem Namen im-Objekt abruft `phone` `contact` .</span><span class="sxs-lookup"><span data-stu-id="1afc7-133">The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 <span data-ttu-id="1afc7-134">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1afc7-134">This code displays the following text:</span></span>  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a><span data-ttu-id="1afc7-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1afc7-135">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="1afc7-136">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1afc7-136">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="1afc7-137">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="1afc7-137">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="1afc7-138">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1afc7-138">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1afc7-139">XML-Value-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1afc7-139">XML Value Property</span></span>](xml-value-property.md)
