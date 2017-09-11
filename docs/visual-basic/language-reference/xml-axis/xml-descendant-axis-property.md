---
title: XML-Achseneigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyDescendantsAxis
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Baisc]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
caps.latest.revision: 14
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
ms.openlocfilehash: e84a8bb989ebbed57595ebf93cef620027a04328
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-descendant-axis-property-visual-basic"></a><span data-ttu-id="1bda4-102">XML-Nachfolgerachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bda4-102">XML Descendant Axis Property (Visual Basic)</span></span>
<span data-ttu-id="1bda4-103">Bietet Zugriff auf die Nachfolger: ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1bda4-103">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bda4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bda4-104">Syntax</span></span>  
  
```  
  
object...<descendant>  
```  
  
## <a name="parts"></a><span data-ttu-id="1bda4-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1bda4-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="1bda4-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1bda4-106">Required.</span></span> <span data-ttu-id="1bda4-107">Ein <xref:System.Xml.Linq.XElement>-Objekt, ein <xref:System.Xml.Linq.XDocument>-Objekt, das eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte oder eine Auflistung von <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1bda4-107">An <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span>  
  
 <span data-ttu-id="1bda4-108">...<</span><span class="sxs-lookup"><span data-stu-id="1bda4-108">...<</span></span>  
 <span data-ttu-id="1bda4-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1bda4-109">Required.</span></span> <span data-ttu-id="1bda4-110">Kennzeichnet den Anfang einer Eigenschaft descendant-Achse.</span><span class="sxs-lookup"><span data-stu-id="1bda4-110">Denotes the start of a descendant axis property.</span></span>  
  
 `descendant`  
 <span data-ttu-id="1bda4-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1bda4-111">Required.</span></span> <span data-ttu-id="1bda4-112">Name der untergeordneten Knoten des Formulars Zugriff auf [`prefix``:`]`name`.</span><span class="sxs-lookup"><span data-stu-id="1bda4-112">Name of the descendant nodes to access, of the form [`prefix``:`]`name`.</span></span>  
  
|<span data-ttu-id="1bda4-113">Segment</span><span class="sxs-lookup"><span data-stu-id="1bda4-113">Part</span></span>|<span data-ttu-id="1bda4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bda4-114">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="1bda4-115">Optional.</span><span class="sxs-lookup"><span data-stu-id="1bda4-115">Optional.</span></span> <span data-ttu-id="1bda4-116">XML-Namespacepräfix für den untergeordneten Knoten.</span><span class="sxs-lookup"><span data-stu-id="1bda4-116">XML namespace prefix for the descendant node.</span></span> <span data-ttu-id="1bda4-117">Muss ein globaler XML-Namespace, die mithilfe von definiert ist eine `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1bda4-117">Must be a global XML namespace that is defined by using an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="1bda4-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1bda4-118">Required.</span></span> <span data-ttu-id="1bda4-119">Lokale Name des untergeordneten Knotens.</span><span class="sxs-lookup"><span data-stu-id="1bda4-119">Local name of the descendant node.</span></span> <span data-ttu-id="1bda4-120">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1bda4-120">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="1bda4-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1bda4-121">Required.</span></span> <span data-ttu-id="1bda4-122">Kennzeichnet das Ende einer untergeordneten Achseneigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1bda4-122">Denotes the end of a descendant axis property.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1bda4-123">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1bda4-123">Return Value</span></span>  
 <span data-ttu-id="1bda4-124">Eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1bda4-124">A collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bda4-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1bda4-125">Remarks</span></span>  
 <span data-ttu-id="1bda4-126">Können Sie eine XML-Achseneigenschaft untergeordnete Knoten nach Namen von Zugriff auf eine <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>-Objekt, oder aus einer Auflistung von <xref:System.Xml.Linq.XElement>oder <xref:System.Xml.Linq.XDocument>Objekte.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1bda4-126">You can use an XML descendant axis property to access descendant nodes by name from an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> object, or from a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="1bda4-127">Mit dem XML- `Value` Eigenschaft, um den Wert des ersten untergeordneten Knoten in der zurückgegebenen Auflistung zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1bda4-127">Use the XML `Value` property to access the value of the first descendant node in the returned collection.</span></span> <span data-ttu-id="1bda4-128">Weitere Informationen finden Sie unter [XML-Value-Eigenschaft](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span><span class="sxs-lookup"><span data-stu-id="1bda4-128">For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
 <span data-ttu-id="1bda4-129">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler konvertiert die untergeordneten Achseneigenschaften in Aufrufe an die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methode.</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="1bda4-129">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler converts descendant axis properties into calls to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="1bda4-130">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="1bda4-130">XML Namespaces</span></span>  
 <span data-ttu-id="1bda4-131">Der Name in einer untergeordneten Achseneigenschaft können nur XML-Namespaces, die global deklariert, mit der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1bda4-131">The name in a descendant axis property can use only XML namespaces declared globally with the `Imports` statement.</span></span> <span data-ttu-id="1bda4-132">Es können keine XML-Namespaces, die lokal innerhalb von XML-Element-literalen deklariert.</span><span class="sxs-lookup"><span data-stu-id="1bda4-132">It cannot use XML namespaces declared locally within XML element literals.</span></span> <span data-ttu-id="1bda4-133">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="1bda4-133">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bda4-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1bda4-134">Example</span></span>  
 <span data-ttu-id="1bda4-135">Das folgende Beispiel zeigt, wie Sie Zugriff auf den Wert des ersten untergeordneten Knoten mit dem Namen `name` und die Werte aller untergeordneten Knoten mit dem Namen `phone` aus der `contacts` Objekt.</span><span class="sxs-lookup"><span data-stu-id="1bda4-135">The following example shows how to access the value of the first descendant node named `name` and the values of all descendant nodes named `phone` from the `contacts` object.</span></span>  
  
 <span data-ttu-id="1bda4-136">[!code-vb[VbXMLSamples&#25;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1bda4-136">[!code-vb[VbXMLSamples#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="1bda4-137">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1bda4-137">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
 `Home Phone = 206-555-0144`  
  
## <a name="example"></a><span data-ttu-id="1bda4-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1bda4-138">Example</span></span>  
 <span data-ttu-id="1bda4-139">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="1bda4-139">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="1bda4-140">Anschließend wird mithilfe der Namespacepräfix ein XML-literal erstellt, und greifen Sie auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name`.</span><span class="sxs-lookup"><span data-stu-id="1bda4-140">It then uses the prefix of the namespace to create an XML literal and access the value of the first child node with the qualified name `ns:name`.</span></span>  
  
 <span data-ttu-id="1bda4-141">[!code-vb[VbXMLSamples&#26;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1bda4-141">[!code-vb[VbXMLSamples#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-descendant-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="1bda4-142">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1bda4-142">This code displays the following text:</span></span>  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="1bda4-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bda4-143">See Also</span></span>  
 <span data-ttu-id="1bda4-144"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="1bda4-144"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="1bda4-145"> [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="1bda4-145"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="1bda4-146"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="1bda4-146"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="1bda4-147"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="1bda4-147"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="1bda4-148"> [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="1bda4-148"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
