---
title: Untergeordnete XML-Achseneigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyChildAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 89a59d00-985e-4f5c-b59f-29b47bad11cb
caps.latest.revision: 18
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
ms.openlocfilehash: 2ccdacdadf219b9c928558f07e0890be6471d40a
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-child-axis-property-visual-basic"></a><span data-ttu-id="3ca7c-102">Untergeordnete XML-Achseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ca7c-102">XML Child Axis Property (Visual Basic)</span></span>
<span data-ttu-id="3ca7c-103">Bietet Zugriff auf die untergeordneten Elemente eines der folgenden: ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3ca7c-103">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ca7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ca7c-104">Syntax</span></span>  
  
```  
  
object.<child>  
```  
  
## <a name="parts"></a><span data-ttu-id="3ca7c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="3ca7c-105">Parts</span></span>  
  
|<span data-ttu-id="3ca7c-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="3ca7c-106">Term</span></span>|<span data-ttu-id="3ca7c-107">Definition</span><span class="sxs-lookup"><span data-stu-id="3ca7c-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="3ca7c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-108">Required.</span></span> <span data-ttu-id="3ca7c-109">Ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3ca7c-109">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|<span data-ttu-id="3ca7c-110">.<</span><span class="sxs-lookup"><span data-stu-id="3ca7c-110">.<</span></span>|<span data-ttu-id="3ca7c-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-111">Required.</span></span> <span data-ttu-id="3ca7c-112">Gibt den Anfang einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-112">Denotes the start of a child axis property.</span></span>|  
|`child`|<span data-ttu-id="3ca7c-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-113">Required.</span></span> <span data-ttu-id="3ca7c-114">Name der untergeordneten Knoten des Formulars Zugriff auf [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-114">Name of the child nodes to access, of the form [`prefix``:`]`name`.</span></span><br /><br /><span data-ttu-id="3ca7c-115"> -   `Prefix`-Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-115"> -   `Prefix` - Optional.</span></span> <span data-ttu-id="3ca7c-116">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-116">XML namespace prefix for the child node.</span></span> <span data-ttu-id="3ca7c-117">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-117">Must be a global XML namespace defined with an `Imports` statement.</span></span><br /><span data-ttu-id="3ca7c-118">-   `Name`-Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-118">-   `Name` - Required.</span></span> <span data-ttu-id="3ca7c-119">Lokaler Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-119">Local child node name.</span></span> <span data-ttu-id="3ca7c-120">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="3ca7c-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
|>|<span data-ttu-id="3ca7c-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-121">Required.</span></span> <span data-ttu-id="3ca7c-122">Gibt das Ende einer untergeordneten Achseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-122">Denotes the end of a child axis property.</span></span>|  
  
## <a name="return-value"></a><span data-ttu-id="3ca7c-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ca7c-123">Return Value</span></span>  
 <span data-ttu-id="3ca7c-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3ca7c-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ca7c-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ca7c-125">Remarks</span></span>  
 <span data-ttu-id="3ca7c-126">Können Sie eine untergeordnete XML-Achseneigenschaft Zugriff auf untergeordnete Knoten anhand des Namens von einer <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>-Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3ca7c-126">You can use an XML child axis property to access child nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="3ca7c-127">Verwenden Sie die XML-`Value`-Eigenschaft, um auf den Wert des ersten untergeordneten Knotens in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-127">Use the XML `Value` property to access the value of the first child node in the returned collection.</span></span> <span data-ttu-id="3ca7c-128">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="3ca7c-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="3ca7c-129">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="3ca7c-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts child axis properties to calls to the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="3ca7c-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="3ca7c-130">XML Namespaces</span></span>  
 <span data-ttu-id="3ca7c-131">Für den Namen in einer untergeordneten Achseneigenschaft können nur XML-Namespacepräfixe verwendet werden, die mit der `Imports`-Anweisung global deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-131">The name in a child axis property can use only XML namespace prefixes declared globally with the `Imports` statement.</span></span> <span data-ttu-id="3ca7c-132">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-132">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="3ca7c-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3ca7c-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ca7c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7c-134">Example</span></span>  
 <span data-ttu-id="3ca7c-135">Im folgenden Beispiel wird veranschaulicht, wie auf die untergeordneten Knoten mit dem Namen `phone` aus dem `contact`-Objekt zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-135">The following example shows how to access the child nodes named `phone` from the `contact` object.</span></span>  
  
 <span data-ttu-id="3ca7c-136">[!code-vb[VbXMLSamples&17;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ca7c-136">[!code-vb[VbXMLSamples#17](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="3ca7c-137">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3ca7c-137">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="3ca7c-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7c-138">Example</span></span>  
 <span data-ttu-id="3ca7c-139">Im folgenden Beispiel wird dargestellt, wie auf die untergeordneten Knoten mit dem Namen `phone` aus der Auflistung zugegriffen werden kann, die von der untergeordneten `contact`-Achseneigenschaft des `contacts`-Objekts zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-139">The following example shows how to access the child nodes named `phone` from the collection returned by the `contact` child axis property of the `contacts` object.</span></span>  
  
 <span data-ttu-id="3ca7c-140">[!code-vb[VbXMLSamples&18;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ca7c-140">[!code-vb[VbXMLSamples#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="3ca7c-141">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3ca7c-141">This code displays the following text:</span></span>  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="3ca7c-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ca7c-142">Example</span></span>  
 <span data-ttu-id="3ca7c-143">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-143">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="3ca7c-144">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="3ca7c-144">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="3ca7c-145">[!code-vb[VbXMLSamples Nr.&19;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ca7c-145">[!code-vb[VbXMLSamples#19](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-child-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="3ca7c-146">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3ca7c-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="3ca7c-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ca7c-147">See Also</span></span>  
 <span data-ttu-id="3ca7c-148"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="3ca7c-148"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="3ca7c-149"> [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="3ca7c-149"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="3ca7c-150"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="3ca7c-150"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="3ca7c-151"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="3ca7c-151"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="3ca7c-152"> [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="3ca7c-152"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
