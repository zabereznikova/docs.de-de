---
title: XML-Nachfolgerachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: bc1dff6dc3b580079087f370212b7d3acd30e4fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938670"
---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="7ce8b-102">XML-Nachfolgerachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7ce8b-102">XML Descendant Axis Property (Visual Basic)</span></span>

<span data-ttu-id="7ce8b-103">Ermöglicht den Zugriff auf die untergeordneten Elemente des Folgendes: eine <xref:System.Xml.Linq.XElement> -Objekt, ein <xref:System.Xml.Linq.XDocument> -Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="7ce8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ce8b-104">Syntax</span></span>

```
object...<descendant>
```

## <a name="parts"></a><span data-ttu-id="7ce8b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7ce8b-105">Parts</span></span>

<span data-ttu-id="7ce8b-106">`object` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-106">`object` Required.</span></span> <span data-ttu-id="7ce8b-107">Ein <xref:System.Xml.Linq.XElement>Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, eine Auflistung von <xref:System.Xml.Linq.XElement>Objekten oder eine Auflistung von <xref:System.Xml.Linq.XDocument>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>

<span data-ttu-id="7ce8b-108">`...<` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-108">`...<` Required.</span></span> <span data-ttu-id="7ce8b-109">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-109">Denotes the start of a descendant axis property.</span></span>

<span data-ttu-id="7ce8b-110">`descendant` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-110">`descendant` Required.</span></span> <span data-ttu-id="7ce8b-111">Name der untergeordneten Knoten des Formulars den Zugriff auf [`prefix:]name`.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-111">Name of the descendant nodes to access, of the form [`prefix:]name`.</span></span>

|<span data-ttu-id="7ce8b-112">Segment</span><span class="sxs-lookup"><span data-stu-id="7ce8b-112">Part</span></span>|<span data-ttu-id="7ce8b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ce8b-113">Description</span></span>|
|----------|-----------------|
|`prefix`|<span data-ttu-id="7ce8b-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-114">Optional.</span></span> <span data-ttu-id="7ce8b-115">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-115">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="7ce8b-116">Muss ein globaler XML-Namespace, die mithilfe von definiert ist ein `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-116">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|
|`name`|<span data-ttu-id="7ce8b-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-117">Required.</span></span> <span data-ttu-id="7ce8b-118">Lokale Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-118">Local name of the descendant node.</span></span> <span data-ttu-id="7ce8b-119">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-119">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|

<span data-ttu-id="7ce8b-120">`>` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-120">`>` Required.</span></span> <span data-ttu-id="7ce8b-121">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-121">Denotes the end of a descendant axis property.</span></span>

## <a name="return-value"></a><span data-ttu-id="7ce8b-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ce8b-122">Return Value</span></span>

<span data-ttu-id="7ce8b-123">Eine Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-123">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ce8b-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ce8b-124">Remarks</span></span>

<span data-ttu-id="7ce8b-125">Können Sie eine XML-Achseneigenschaft mittelbar untergeordneten Knoten nach Namen aus den Zugriff auf eine <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> -Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument> Objekte.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-125">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="7ce8b-126">Verwenden Sie das XML `Value` Eigenschaft, um den Wert des ersten untergeordneten Knoten in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-126">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="7ce8b-127">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-127">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>

<span data-ttu-id="7ce8b-128">Visual Basic-Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Descendants%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-128">The Visual Basic compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>

## <a name="xml-namespaces"></a><span data-ttu-id="7ce8b-129">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="7ce8b-129">XML Namespaces</span></span>

<span data-ttu-id="7ce8b-130">Der Name in einer untergeordneten Achseneigenschaft können nur XML-Namespaces, die global deklariert, mit der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-130">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="7ce8b-131">Es können keine XML-Namespaces, die lokal innerhalb der XML-Elementliteralen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-131">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="7ce8b-132">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-132">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>

## <a name="example"></a><span data-ttu-id="7ce8b-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ce8b-133">Example</span></span>

<span data-ttu-id="7ce8b-134">Das folgende Beispiel zeigt, wie Sie Zugriff auf den Wert des ersten untergeordneten Knoten mit dem Namen `name` und die Werte aller untergeordneten Knoten, die mit dem Namen `phone` aus der `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-134">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

<span data-ttu-id="7ce8b-135">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7ce8b-135">This code displays the following text:</span></span>

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a><span data-ttu-id="7ce8b-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7ce8b-136">Example</span></span>

<span data-ttu-id="7ce8b-137">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-137">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="7ce8b-138">Klicken Sie dann das Namespacepräfix des Namespace eine XML-literal erstellt und der Zugriff auf den Wert des ersten untergeordneten Knotens mit dem qualifizierten Namen verwendet `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-138">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

<span data-ttu-id="7ce8b-139">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7ce8b-139">This code displays the following text:</span></span>

`Name: Patrick Hines`

## <a name="see-also"></a><span data-ttu-id="7ce8b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ce8b-140">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="7ce8b-141">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="7ce8b-141">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="7ce8b-142">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="7ce8b-142">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="7ce8b-143">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7ce8b-143">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="7ce8b-144">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="7ce8b-144">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
