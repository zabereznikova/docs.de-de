---
title: XML-Value-Eigenschaft (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c52ac09e209d6e3f0cfd877a071cbbe3ab96f18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="16e52-102">XML-Value-Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16e52-102">XML Value Property (Visual Basic)</span></span>
<span data-ttu-id="16e52-103">Bietet Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16e52-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16e52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16e52-104">Syntax</span></span>  
  
```  
object.Value  
```  
  
## <a name="parts"></a><span data-ttu-id="16e52-105">Teile</span><span class="sxs-lookup"><span data-stu-id="16e52-105">Parts</span></span>  
  
|<span data-ttu-id="16e52-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="16e52-106">Term</span></span>|<span data-ttu-id="16e52-107">Definition</span><span class="sxs-lookup"><span data-stu-id="16e52-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="16e52-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="16e52-108">Required.</span></span> <span data-ttu-id="16e52-109">Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="16e52-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="16e52-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="16e52-110">Return Value</span></span>  
 <span data-ttu-id="16e52-111">Ein `String` , den Wert des ersten Elements der Auflistung enthält oder `Nothing` , wenn die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="16e52-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16e52-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16e52-112">Remarks</span></span>  
 <span data-ttu-id="16e52-113">Die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft erleichtert das Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16e52-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="16e52-114">Diese Eigenschaft überprüft zuerst, ob die Auflistung über mindestens ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="16e52-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="16e52-115">Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="16e52-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="16e52-116">Andernfalls gibt diese Eigenschaft den Wert der die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft des ersten Elements in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="16e52-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16e52-117">Beim Zugriff auf den Wert eines XML-Attributs mithilfe der "@" Bezeichner, den Wert des Attributs wird zurückgegeben, als eine `String` und Sie müssen nicht explizit angeben der <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="16e52-117">When you access the value of an XML attribute using the '@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="16e52-118">Um andere Elemente in einer Auflistung zuzugreifen, können Sie die XML-Erweiterungsindexereigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="16e52-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="16e52-119">Weitere Informationen finden Sie unter [Erweiterungsindexereigenschaft](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="16e52-119">For more information, see [Extension Indexer Property](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md).</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="16e52-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="16e52-120">Inheritance</span></span>  
 <span data-ttu-id="16e52-121">Die meisten Benutzer müssen nicht implementieren <xref:System.Collections.Generic.IEnumerable%601>, und Sie können diesen Abschnitt daher ignorieren.</span><span class="sxs-lookup"><span data-stu-id="16e52-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>  
  
 <span data-ttu-id="16e52-122">Die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft ist eine Erweiterungseigenschaft für Typen, die implementieren `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="16e52-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="16e52-123">Die Bindung dieser Eigenschaft für die Erweiterung wird wie die Bindung von Erweiterungsmethoden: Wenn ein Typ eine der Schnittstellen implementiert und definiert eine Eigenschaft mit dem Namen "Wert", hat diese Eigenschaft Vorrang vor der Erweiterungseigenschaft.</span><span class="sxs-lookup"><span data-stu-id="16e52-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="16e52-124">Das heißt, diese <xref:System.Xml.Linq.XElement.Value%2A> -Eigenschaft kann überschrieben werden, definieren Sie eine neue Eigenschaft in einer Klasse, die implementiert `IEnumerable(Of XElement)`.</span><span class="sxs-lookup"><span data-stu-id="16e52-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16e52-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16e52-125">Example</span></span>  
 <span data-ttu-id="16e52-126">Das folgende Beispiel zeigt, wie Sie die <xref:System.Xml.Linq.XElement.Value%2A> Eigenschaft für den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16e52-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="16e52-127">Im Beispiel wird die untergeordnete Achseneigenschaft beim Abrufen der Auflistung aller untergeordneten Knoten mit dem Namen `phone` , die sich in der `contact` Objekt.</span><span class="sxs-lookup"><span data-stu-id="16e52-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 <span data-ttu-id="16e52-128">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="16e52-128">This code displays the following text:</span></span>  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="16e52-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16e52-129">Example</span></span>  
 <span data-ttu-id="16e52-130">Im folgende Beispiel wird gezeigt, wie der Wert für ein XML-Attribut aus einer Auflistung von abgerufen <xref:System.Xml.Linq.XAttribute> Objekte.</span><span class="sxs-lookup"><span data-stu-id="16e52-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="16e52-131">Im Beispiel wird die Attribute Axis-Eigenschaft den Wert der anzuzeigenden der `type` Attribut für alle von der die `phone` Elemente.</span><span class="sxs-lookup"><span data-stu-id="16e52-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the the `phone` elements.</span></span>  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 <span data-ttu-id="16e52-132">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="16e52-132">This code displays the following text:</span></span>  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a><span data-ttu-id="16e52-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16e52-133">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [<span data-ttu-id="16e52-134">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="16e52-134">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="16e52-135">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="16e52-135">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="16e52-136">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="16e52-136">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="16e52-137">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="16e52-137">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="16e52-138">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="16e52-138">Extension Indexer Property</span></span>](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [<span data-ttu-id="16e52-139">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="16e52-139">XML Child Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [<span data-ttu-id="16e52-140">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="16e52-140">XML Attribute Axis Property</span></span>](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
