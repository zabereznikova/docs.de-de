---
title: XML Child Axis Property
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
ms.openlocfilehash: 728c17cd2ed8661e0a5f1f2b8e929059713a1edf
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545119"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="c7d47-102">Untergeordnete XML-Achseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7d47-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="c7d47-103">Bietet Zugriff auf die untergeordneten Elemente eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts, einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder einer Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c7d47-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d47-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7d47-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="c7d47-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="c7d47-105">Parts</span></span>  
  
|<span data-ttu-id="c7d47-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c7d47-106">Term</span></span>|<span data-ttu-id="c7d47-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c7d47-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="c7d47-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7d47-108">Required.</span></span> <span data-ttu-id="c7d47-109">Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c7d47-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="c7d47-110">.<</span><span class="sxs-lookup"><span data-stu-id="c7d47-110">.<</span></span>|<span data-ttu-id="c7d47-111">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7d47-111">Required.</span></span> <span data-ttu-id="c7d47-112">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c7d47-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="c7d47-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7d47-113">Required.</span></span> <span data-ttu-id="c7d47-114">Der Name der untergeordneten Knoten, auf die mit dem Formular `[prefix:]name`zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7d47-114">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="c7d47-115">-   `Prefix`: optional.</span><span class="sxs-lookup"><span data-stu-id="c7d47-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="c7d47-116">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="c7d47-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="c7d47-117">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c7d47-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="c7d47-118">-   `Name`-erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c7d47-118">-   `Name` - Required.</span></span> <span data-ttu-id="c7d47-119">Lokaler Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="c7d47-119">Local child node name.</span></span> <span data-ttu-id="c7d47-120">Siehe [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="c7d47-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="c7d47-121">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c7d47-121">Required.</span></span> <span data-ttu-id="c7d47-122">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c7d47-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="c7d47-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c7d47-123">Return Value</span></span>  
 <span data-ttu-id="c7d47-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c7d47-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7d47-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7d47-125">Remarks</span></span>  
 <span data-ttu-id="c7d47-126">Sie können eine untergeordnete XML-Achseneigenschaft verwenden, um auf untergeordnete Knoten eines <xref:System.Xml.Linq.XElement>-Objekts oder eines <xref:System.Xml.Linq.XDocument>-Objekts bzw. einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder <xref:System.Xml.Linq.XDocument>-Objekten über den Namen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7d47-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="c7d47-127">Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c7d47-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="c7d47-128">Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="c7d47-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="c7d47-129">Der Visual Basic-Compiler konvertiert Eigenschaften der untergeordneten Achse in Aufrufe der <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c7d47-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="c7d47-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c7d47-130">XML Namespaces</span></span>  
 <span data-ttu-id="c7d47-131">Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="c7d47-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="c7d47-132">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="c7d47-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="c7d47-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c7d47-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7d47-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7d47-134">Example</span></span>  
 <span data-ttu-id="c7d47-135">Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7d47-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="c7d47-136">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c7d47-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="c7d47-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7d47-137">Example</span></span>  
 <span data-ttu-id="c7d47-138">Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c7d47-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="c7d47-139">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c7d47-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="c7d47-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7d47-140">Example</span></span>  
 <span data-ttu-id="c7d47-141">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="c7d47-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="c7d47-142">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="c7d47-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="c7d47-143">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c7d47-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="c7d47-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7d47-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="c7d47-145">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="c7d47-145">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="c7d47-146">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="c7d47-146">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="c7d47-147">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7d47-147">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="c7d47-148">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="c7d47-148">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
