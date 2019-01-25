---
title: XML-Nachfolgerachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: 3b8d13e606f28896cae88162d572470e49af3739
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730281"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="8dbb3-102">XML-Nachfolgerachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dbb3-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="8dbb3-103">Ermöglicht den Zugriff auf die untergeordneten Elemente des Folgendes: eine <xref:System.Xml.Linq.XElement> -Objekt, ein <xref:System.Xml.Linq.XDocument> -Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dbb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8dbb3-104">Syntax</span></span>  
  
```  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="8dbb3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8dbb3-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="8dbb3-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-106">Required.</span></span> <span data-ttu-id="8dbb3-107">Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="8dbb3-108">...<</span><span class="sxs-lookup"><span data-stu-id="8dbb3-108">...<</span></span>  
 <span data-ttu-id="8dbb3-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-109">Required.</span></span> <span data-ttu-id="8dbb3-110">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="8dbb3-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-111">Required.</span></span> <span data-ttu-id="8dbb3-112">Name der untergeordneten Knoten des Formulars den Zugriff auf [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="8dbb3-113">Segment</span><span class="sxs-lookup"><span data-stu-id="8dbb3-113">Part</span></span>|<span data-ttu-id="8dbb3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8dbb3-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="8dbb3-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-115">Optional.</span></span> <span data-ttu-id="8dbb3-116">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="8dbb3-117">Muss ein globaler XML-Namespace, die mithilfe von definiert ist ein `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="8dbb3-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-118">Required.</span></span> <span data-ttu-id="8dbb3-119">Lokale Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-119">Local name of the descendant node.</span></span> <span data-ttu-id="8dbb3-120">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="8dbb3-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="8dbb3-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-121">Required.</span></span> <span data-ttu-id="8dbb3-122">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dbb3-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8dbb3-123">Return Value</span></span>  
 <span data-ttu-id="8dbb3-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dbb3-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8dbb3-125">Remarks</span></span>  
 <span data-ttu-id="8dbb3-126">Können Sie eine XML-Achseneigenschaft mittelbar untergeordneten Knoten nach Namen aus den Zugriff auf eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> -Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="8dbb3-127">Verwenden Sie das XML `Value` Eigenschaft, um den Wert des ersten untergeordneten Knoten in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="8dbb3-128">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="8dbb3-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="8dbb3-129">Visual Basic-Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Descendants%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-129">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="8dbb3-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="8dbb3-130">XML Namespaces</span></span>  
 <span data-ttu-id="8dbb3-131">Der Name in einer untergeordneten Achseneigenschaft können nur XML-Namespaces, die global deklariert, mit der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="8dbb3-132">Es können keine XML-Namespaces, die lokal innerhalb der XML-Elementliteralen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="8dbb3-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="8dbb3-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8dbb3-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dbb3-134">Example</span></span>  
 <span data-ttu-id="8dbb3-135">Das folgende Beispiel zeigt, wie Sie Zugriff auf den Wert des ersten untergeordneten Knoten mit dem Namen `name` und die Werte aller untergeordneten Knoten, die mit dem Namen `phone` aus der `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]  
  
 <span data-ttu-id="8dbb3-136">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8dbb3-136">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="8dbb3-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8dbb3-137">Example</span></span>  
 <span data-ttu-id="8dbb3-138">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-138">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="8dbb3-139">Klicken Sie dann das Namespacepräfix des Namespace eine XML-literal erstellt und der Zugriff auf den Wert des ersten untergeordneten Knotens mit dem qualifizierten Namen verwendet `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="8dbb3-139">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]  
  
 <span data-ttu-id="8dbb3-140">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8dbb3-140">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="8dbb3-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dbb3-141">See also</span></span>
- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="8dbb3-142">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8dbb3-142">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="8dbb3-143">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="8dbb3-143">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="8dbb3-144">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dbb3-144">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="8dbb3-145">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="8dbb3-145">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
