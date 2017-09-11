---
title: XML-Attributachseneigenschaft (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyAttributeAxis
dev_langs:
- VB
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: 23
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
ms.openlocfilehash: a3c327f4448287bcf6c45b9b6e26a1ef9ba13c16
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="ce00a-102">XML-Attributachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce00a-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="ce00a-103">Ermöglicht den Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement>Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ce00a-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce00a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce00a-104">Syntax</span></span>  
  
```  
  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="ce00a-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ce00a-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="ce00a-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce00a-106">Required.</span></span> <span data-ttu-id="ce00a-107">Ein <xref:System.Xml.Linq.XElement>Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ce00a-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ce00a-108">.@</span><span class="sxs-lookup"><span data-stu-id="ce00a-108">.@</span></span>  
 <span data-ttu-id="ce00a-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce00a-109">Required.</span></span> <span data-ttu-id="ce00a-110">Kennzeichnet den Anfang der Attribute Axis-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ce00a-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="ce00a-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="ce00a-111">Optional.</span></span> <span data-ttu-id="ce00a-112">Kennzeichnet den Beginn des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce00a-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="ce00a-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce00a-113">Required.</span></span> <span data-ttu-id="ce00a-114">Der Name des Attributs des Formulars Zugriff auf [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="ce00a-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="ce00a-115">Segment</span><span class="sxs-lookup"><span data-stu-id="ce00a-115">Part</span></span>|<span data-ttu-id="ce00a-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce00a-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="ce00a-117">Optional.</span><span class="sxs-lookup"><span data-stu-id="ce00a-117">Optional.</span></span> <span data-ttu-id="ce00a-118">XML-Namespacepräfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce00a-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="ce00a-119">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ce00a-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="ce00a-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ce00a-120">Required.</span></span> <span data-ttu-id="ce00a-121">Lokaler Attributname.</span><span class="sxs-lookup"><span data-stu-id="ce00a-121">Local attribute name.</span></span> <span data-ttu-id="ce00a-122">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ce00a-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="ce00a-123">Optional.</span><span class="sxs-lookup"><span data-stu-id="ce00a-123">Optional.</span></span> <span data-ttu-id="ce00a-124">Kennzeichnet das Ende des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce00a-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce00a-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce00a-125">Return Value</span></span>  
 <span data-ttu-id="ce00a-126">Eine Zeichenfolge, die dem Wert des `attribute`.</span><span class="sxs-lookup"><span data-stu-id="ce00a-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="ce00a-127">Wenn der Attributname nicht vorhanden ist, `Nothing` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce00a-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce00a-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce00a-128">Remarks</span></span>  
 <span data-ttu-id="ce00a-129">Können Sie Zugriff auf den Wert eines Attributs anhand des Namens von einer XML-Attributachseneigenschaft ein <xref:System.Xml.Linq.XElement>Objekt oder aus dem ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ce00a-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ce00a-130">Sie können einen Attributwert nach Namen abrufen oder hinzufügen ein neues Attributs zu einem Element durch einen neuen Namen mit vorangestellten der @ Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ce00a-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="ce00a-131">Bei Verweisen auf ein XML-Attribut mit dem @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A>Eigenschaft.</xref:System.Xml.Linq.XAttribute.Value%2A></span><span class="sxs-lookup"><span data-stu-id="ce00a-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="ce00a-132">Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ce00a-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identifiers.</span></span> <span data-ttu-id="ce00a-133">Zugriff auf ein XML-Attribut mit dem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).</span><span class="sxs-lookup"><span data-stu-id="ce00a-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="ce00a-134">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="ce00a-134">XML Namespaces</span></span>  
 <span data-ttu-id="ce00a-135">Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert, indem die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ce00a-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="ce00a-136">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="ce00a-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="ce00a-137">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="ce00a-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce00a-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce00a-138">Example</span></span>  
 <span data-ttu-id="ce00a-139">Im folgenden Beispiel wird veranschaulicht, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen `phone`.</span><span class="sxs-lookup"><span data-stu-id="ce00a-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 <span data-ttu-id="ce00a-140">[!code-vb[VbXMLSamples&#12;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ce00a-140">[!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]</span></span>  
  
 <span data-ttu-id="ce00a-141">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce00a-141">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="ce00a-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce00a-142">Example</span></span>  
 <span data-ttu-id="ce00a-143">Im folgenden Beispiel wird veranschaulicht, wie Attribute für ein XML-Element sowohl deklarativ als Teil des XML und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von erstellt ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ce00a-143">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ce00a-144">Die `type` -Attribut wird deklarativ erstellt und die `owne`R-Attribut wird dynamisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="ce00a-144">The `type` attribute is created declaratively and the `owne`r attribute is created dynamically.</span></span>  
  
 <span data-ttu-id="ce00a-145">[!code-vb[VbXMLSamples&#44;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ce00a-145">[!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]</span></span>  
  
 <span data-ttu-id="ce00a-146">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce00a-146">This code displays the following text:</span></span>  
  
```  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="ce00a-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce00a-147">Example</span></span>  
 <span data-ttu-id="ce00a-148">Im folgenden Beispiel wird die Syntax mit spitzen Klammern zum Abrufen des Wert des XML-Attributs mit dem Namen `number-type`, der kein gültiger Bezeichner in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce00a-148">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="ce00a-149">[!code-vb[VbXMLSamples&#13;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ce00a-149">[!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]</span></span>  
  
 <span data-ttu-id="ce00a-150">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce00a-150">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="ce00a-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce00a-151">Example</span></span>  
 <span data-ttu-id="ce00a-152">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="ce00a-152">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ce00a-153">Anschließend wird mithilfe der Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="ce00a-153">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 <span data-ttu-id="ce00a-154">[!code-vb[VbXMLSamples&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ce00a-154">[!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]</span></span>  
  
 <span data-ttu-id="ce00a-155">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ce00a-155">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="ce00a-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce00a-156">See Also</span></span>  
 <span data-ttu-id="ce00a-157"><xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ce00a-157"><xref:System.Xml.Linq.XElement></span></span>   
<span data-ttu-id="ce00a-158"> [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span><span class="sxs-lookup"><span data-stu-id="ce00a-158"> [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md) </span></span>  
<span data-ttu-id="ce00a-159"> [XML-Literale](../../../visual-basic/language-reference/xml-literals/index.md) </span><span class="sxs-lookup"><span data-stu-id="ce00a-159"> [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md) </span></span>  
<span data-ttu-id="ce00a-160"> [Erstellen von XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ce00a-160"> [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="ce00a-161"> [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="ce00a-161"> [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)</span></span>
