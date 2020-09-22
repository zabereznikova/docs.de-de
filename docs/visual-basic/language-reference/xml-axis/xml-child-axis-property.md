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
ms.openlocfilehash: c6af9584931206fecde3154a91a60cfd38278ec0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873071"
---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="56c6c-102">Untergeordnete XML-Achseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56c6c-102">XML Child Axis Property (Visual Basic)</span></span>

<span data-ttu-id="56c6c-103">Bietet Zugriff auf die untergeordneten Elemente eines <xref:System.Xml.Linq.XElement>-Objekts, eines <xref:System.Xml.Linq.XDocument>-Objekts, einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder einer Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="56c6c-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="56c6c-104">Syntax</span></span>  
  
```vb  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="56c6c-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="56c6c-105">Parts</span></span>  
  
|<span data-ttu-id="56c6c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="56c6c-106">Term</span></span>|<span data-ttu-id="56c6c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="56c6c-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="56c6c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56c6c-108">Required.</span></span> <span data-ttu-id="56c6c-109">Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="56c6c-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="56c6c-110">. <</span><span class="sxs-lookup"><span data-stu-id="56c6c-110">.<</span></span>|<span data-ttu-id="56c6c-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56c6c-111">Required.</span></span> <span data-ttu-id="56c6c-112">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="56c6c-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="56c6c-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56c6c-113">Required.</span></span> <span data-ttu-id="56c6c-114">Der Name der untergeordneten Knoten, auf die im Formular zugegriffen werden soll `[prefix:]name` .</span><span class="sxs-lookup"><span data-stu-id="56c6c-114">Name of the child nodes to access, of the form `[prefix:]name`.</span></span><br /><br /> <span data-ttu-id="56c6c-115">-   `Prefix` Optionale.</span><span class="sxs-lookup"><span data-stu-id="56c6c-115">-   `Prefix` - Optional.</span></span> <span data-ttu-id="56c6c-116"> XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="56c6c-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="56c6c-117">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="56c6c-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="56c6c-118">-   `Name` Benötigten.</span><span class="sxs-lookup"><span data-stu-id="56c6c-118">-   `Name` - Required.</span></span> <span data-ttu-id="56c6c-119">Lokaler Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="56c6c-119">Local child node name.</span></span> <span data-ttu-id="56c6c-120">Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="56c6c-120">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="56c6c-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56c6c-121">Required.</span></span> <span data-ttu-id="56c6c-122">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="56c6c-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="56c6c-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="56c6c-123">Return Value</span></span>  

 <span data-ttu-id="56c6c-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="56c6c-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56c6c-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="56c6c-125">Remarks</span></span>  

 <span data-ttu-id="56c6c-126">Sie können eine untergeordnete XML-Achseneigenschaft verwenden, um auf untergeordnete Knoten eines <xref:System.Xml.Linq.XElement>-Objekts oder eines <xref:System.Xml.Linq.XDocument>-Objekts bzw. einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten oder <xref:System.Xml.Linq.XDocument>-Objekten über den Namen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="56c6c-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="56c6c-127">Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="56c6c-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="56c6c-128">Weitere Informationen finden Sie unter [XML-Wert Eigenschaft](xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="56c6c-128">For more information, see [XML Value Property](xml-value-property.md).</span></span>  
  
 <span data-ttu-id="56c6c-129">Der Visual Basic-Compiler konvertiert Eigenschaften der untergeordneten Achse in Aufrufe der- <xref:System.Xml.Linq.XContainer.Elements%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="56c6c-129">The Visual Basic compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="56c6c-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="56c6c-130">XML Namespaces</span></span>  

 <span data-ttu-id="56c6c-131">Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="56c6c-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="56c6c-132">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="56c6c-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="56c6c-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="56c6c-133">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56c6c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56c6c-134">Example</span></span>  

 <span data-ttu-id="56c6c-135">Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="56c6c-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 [!code-vb[VbXMLSamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#17)]  
  
 <span data-ttu-id="56c6c-136">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="56c6c-136">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="56c6c-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56c6c-137">Example</span></span>  

 <span data-ttu-id="56c6c-138">Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="56c6c-138">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 [!code-vb[VbXMLSamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#18)]  
  
 <span data-ttu-id="56c6c-139">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="56c6c-139">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="56c6c-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56c6c-140">Example</span></span>  

 <span data-ttu-id="56c6c-141">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="56c6c-141">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="56c6c-142">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="56c6c-142">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="56c6c-143">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="56c6c-143">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="56c6c-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56c6c-144">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="56c6c-145">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="56c6c-145">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="56c6c-146">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="56c6c-146">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="56c6c-147">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56c6c-147">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="56c6c-148">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="56c6c-148">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
