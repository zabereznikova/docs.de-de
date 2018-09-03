---
title: Untergeordnete XML-Achseneigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyChildAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
ms.openlocfilehash: 0b504a9e368e5179d5f91faf7256445d7da47b1d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484893"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="37570-102">Untergeordnete XML-Achseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="37570-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="37570-103">Bietet Zugriff auf die untergeordneten Elemente eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts, einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder einer Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="37570-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37570-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="37570-104">Syntax</span></span>  
  
```  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="37570-105">Teile</span><span class="sxs-lookup"><span data-stu-id="37570-105">Parts</span></span>  
  
|<span data-ttu-id="37570-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="37570-106">Term</span></span>|<span data-ttu-id="37570-107">Definition</span><span class="sxs-lookup"><span data-stu-id="37570-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="37570-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37570-108">Required.</span></span> <span data-ttu-id="37570-109">Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="37570-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="37570-110">.<</span><span class="sxs-lookup"><span data-stu-id="37570-110">.<</span></span>|<span data-ttu-id="37570-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37570-111">Required.</span></span> <span data-ttu-id="37570-112">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="37570-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="37570-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37570-113">Required.</span></span> <span data-ttu-id="37570-114">Name der untergeordneten Knoten des Formulars den Zugriff auf [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="37570-114">Name of the child nodes to access, of the form [`prefix``:`]`name`.</span></span><br /><br /> <span data-ttu-id="37570-115">-   `Prefix` – Optional.</span><span class="sxs-lookup"><span data-stu-id="37570-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="37570-116">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="37570-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="37570-117">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="37570-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="37570-118">-   `Name` – Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37570-118">-   `Name` - Required.</span></span> <span data-ttu-id="37570-119">Lokaler Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="37570-119">Local child node name.</span></span> <span data-ttu-id="37570-120">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="37570-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="37570-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="37570-121">Required.</span></span> <span data-ttu-id="37570-122">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="37570-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="37570-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="37570-123">Return Value</span></span>  
 <span data-ttu-id="37570-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="37570-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37570-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37570-125">Remarks</span></span>  
 <span data-ttu-id="37570-126">Sie können eine untergeordnete XML-Achseneigenschaft verwenden, um auf untergeordnete Knoten eines <xref:System.Xml.Linq.XElement>-Objekts oder eines <xref:System.Xml.Linq.XDocument>-Objekts bzw. einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder <xref:System.Xml.Linq.XDocument>-Objekten über den Namen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37570-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="37570-127">Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="37570-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="37570-128">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="37570-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="37570-129">Visual Basic-Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Elements%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="37570-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="37570-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="37570-130">XML Namespaces</span></span>  
 <span data-ttu-id="37570-131">Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="37570-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="37570-132">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="37570-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="37570-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="37570-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37570-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37570-134">Example</span></span>  
 <span data-ttu-id="37570-135">Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="37570-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]  
  
 <span data-ttu-id="37570-136">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="37570-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="37570-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37570-137">Example</span></span>  
 <span data-ttu-id="37570-138">Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="37570-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]  
  
 <span data-ttu-id="37570-139">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="37570-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="37570-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="37570-140">Example</span></span>  
 <span data-ttu-id="37570-141">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="37570-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="37570-142">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="37570-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]  
  
 <span data-ttu-id="37570-143">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="37570-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="37570-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37570-144">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="37570-145">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="37570-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)  
 [<span data-ttu-id="37570-146">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="37570-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="37570-147">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37570-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="37570-148">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="37570-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
