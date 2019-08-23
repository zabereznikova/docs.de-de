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
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942979"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="aa2ab-102">XML-Value-Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa2ab-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="aa2ab-103">Bietet Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement> -Objekten.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa2ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa2ab-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="aa2ab-105">Teile</span><span class="sxs-lookup"><span data-stu-id="aa2ab-105">Parts</span></span>  
  
|<span data-ttu-id="aa2ab-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="aa2ab-106">Term</span></span>|<span data-ttu-id="aa2ab-107">Definition</span><span class="sxs-lookup"><span data-stu-id="aa2ab-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="aa2ab-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-108">Required.</span></span> <span data-ttu-id="aa2ab-109">Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="aa2ab-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa2ab-110">Return Value</span></span>  
 <span data-ttu-id="aa2ab-111">Ein `String` , der den Wert des ersten Elements der Auflistung enthält, oder `Nothing` , wenn die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa2ab-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa2ab-112">Remarks</span></span>  
 <span data-ttu-id="aa2ab-113">Die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft vereinfacht den Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> -Objekten.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="aa2ab-114">Diese Eigenschaft prüft zunächst, ob die Auflistung mindestens ein-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="aa2ab-115">Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing`zurück.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="aa2ab-116">Andernfalls gibt diese Eigenschaft den Wert der <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft des ersten Elements in der-Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa2ab-117">Wenn Sie mit dem Bezeichner "\@" auf den Wert eines XML `String` -Attributs zugreifen, wird der-Attribut Wert als zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A> -Eigenschaft nicht explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="aa2ab-118">Wenn Sie auf andere Elemente in einer Auflistung zugreifen möchten, können Sie die XML-Erweiterungsindexer-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="aa2ab-119">Weitere Informationen finden Sie unter [Extension Indexer-Eigenschaft](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="aa2ab-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="aa2ab-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="aa2ab-120">Inheritance</span></span>  
 <span data-ttu-id="aa2ab-121">Die meisten Benutzer müssen nicht implementieren <xref:System.Collections.Generic.IEnumerable%601>und können daher diesen Abschnitt ignorieren.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="aa2ab-122">Die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft ist eine Erweiterungs Eigenschaft für Typen, `IEnumerable(Of XElement)`die implementieren.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="aa2ab-123">Die Bindung dieser Erweiterungs Eigenschaft ähnelt der Bindung von Erweiterungs Methoden: Wenn ein Typ eine der Schnittstellen implementiert und eine Eigenschaft mit dem Namen "Value" definiert, hat diese Eigenschaft Vorrang vor der Erweiterungs Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="aa2ab-124">Anders ausgedrückt: diese <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft kann überschrieben werden, indem eine neue Eigenschaft in einer Klasse definiert wird, die implementiert. `IEnumerable(Of XElement)`</span><span class="sxs-lookup"><span data-stu-id="aa2ab-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa2ab-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa2ab-125">Example</span></span>  
 <span data-ttu-id="aa2ab-126">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft verwendet wird, um auf den ersten Knoten <xref:System.Xml.Linq.XElement> in einer Auflistung von-Objekten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="aa2ab-127">Im Beispiel wird die-Eigenschaft der untergeordneten-Achse verwendet, um die Auflistung `phone` aller untergeordneten Knoten `contact` mit dem Namen im-Objekt zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 <span data-ttu-id="aa2ab-128">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="aa2ab-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="aa2ab-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aa2ab-129">Example</span></span>  
 <span data-ttu-id="aa2ab-130">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines XML-Attributs aus einer <xref:System.Xml.Linq.XAttribute> Auflistung von-Objekten erhalten.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="aa2ab-131">Im Beispiel wird die Eigenschaft Attribut Achse verwendet, um den Wert des `type` -Attributs für alle `phone` Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="aa2ab-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 <span data-ttu-id="aa2ab-132">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="aa2ab-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="aa2ab-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa2ab-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="aa2ab-134">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa2ab-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="aa2ab-135">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="aa2ab-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="aa2ab-136">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="aa2ab-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="aa2ab-137">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="aa2ab-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="aa2ab-138">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="aa2ab-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [<span data-ttu-id="aa2ab-139">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="aa2ab-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="aa2ab-140">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="aa2ab-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
