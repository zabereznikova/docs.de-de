---
title: XML-Value-Eigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 1c7aa1cc32bc1c5ef637f7a606db7e695f1dfaee
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821950"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="1e721-102">XML-Value-Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e721-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="1e721-103">Ermöglicht den Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="1e721-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e721-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e721-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="1e721-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1e721-105">Parts</span></span>  
  
|<span data-ttu-id="1e721-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1e721-106">Term</span></span>|<span data-ttu-id="1e721-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1e721-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="1e721-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e721-108">Required.</span></span> <span data-ttu-id="1e721-109">Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="1e721-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="1e721-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e721-110">Return Value</span></span>  
 <span data-ttu-id="1e721-111">Ein `String` , den Wert des ersten Elements der Auflistung enthält oder `Nothing` , wenn die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="1e721-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e721-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1e721-112">Remarks</span></span>  
 <span data-ttu-id="1e721-113">Die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft erleichtert das Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="1e721-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1e721-114">Diese Eigenschaft überprüft zuerst, ob die Auflistung über mindestens ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1e721-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="1e721-115">Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="1e721-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="1e721-116">Andernfalls gibt diese Eigenschaft den Wert der die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft des ersten Elements in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="1e721-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e721-117">Beim Zugriff auf den Wert eines XML-Attributs mithilfe der "\@'-ID, den Wert des Attributs wird als zurückgegeben eine `String` und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e721-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="1e721-118">Um andere Elemente in einer Auflistung zuzugreifen, können Sie die Indexereigenschaft für XML-Erweiterung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e721-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="1e721-119">Weitere Informationen finden Sie unter [Erweiterungsindexereigenschaft](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="1e721-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="1e721-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="1e721-120">Inheritance</span></span>  
 <span data-ttu-id="1e721-121">Die meisten Benutzer haben keinen implementieren <xref:System.Collections.Generic.IEnumerable%601>, und können daher diesen Abschnitt ignorieren.</span><span class="sxs-lookup"><span data-stu-id="1e721-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="1e721-122">Die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft ist eine Erweiterungseigenschaft für Typen, implementieren `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="1e721-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="1e721-123">Die Bindung dieser Eigenschaft für die Erweiterung wird wie die Bindung der Erweiterungsmethoden: Wenn ein Typ eine der Schnittstellen implementiert und definiert eine Eigenschaft mit dem Namen "Value", hat diese Eigenschaft Vorrang vor der Erweiterungseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1e721-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="1e721-124">Das heißt, diese <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft kann überschrieben werden, definieren Sie eine neue Eigenschaft in einer Klasse, die implementiert `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="1e721-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e721-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e721-125">Example</span></span>  
 <span data-ttu-id="1e721-126">Das folgende Beispiel zeigt, wie Sie mit der <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft auf den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="1e721-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1e721-127">Im Beispiel wird die untergeordneten Achseneigenschaft verwendet, um die Auflistung aller untergeordneten Knoten mit dem Namen abzurufen `phone` , die sich in der `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1e721-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="1e721-128">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e721-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="1e721-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e721-129">Example</span></span>  
 <span data-ttu-id="1e721-130">Das folgende Beispiel zeigt, wie Sie den Wert eines XML-Attributs aus einer Auflistung von abrufen <xref:System.Xml.Linq.XAttribute> Objekte.</span><span class="sxs-lookup"><span data-stu-id="1e721-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="1e721-131">Im Beispiel wird die Attributachseneigenschaft verwendet, um den Wert der an die `type` -Attribut für alle von der `phone` Elemente.</span><span class="sxs-lookup"><span data-stu-id="1e721-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="1e721-132">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e721-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="1e721-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e721-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="1e721-134">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e721-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="1e721-135">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="1e721-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="1e721-136">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e721-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1e721-137">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="1e721-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="1e721-138">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e721-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="1e721-139">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e721-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="1e721-140">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e721-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
