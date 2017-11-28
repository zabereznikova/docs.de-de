---
title: XML-Attributachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a286c70f57128d0406b3a300610fea5e1c44b32d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="d4f61-102">XML-Attributachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4f61-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="d4f61-103">Bietet Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d4f61-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4f61-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4f61-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="d4f61-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d4f61-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="d4f61-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4f61-106">Required.</span></span> <span data-ttu-id="d4f61-107">Ein <xref:System.Xml.Linq.XElement> Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d4f61-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="d4f61-108">.@</span><span class="sxs-lookup"><span data-stu-id="d4f61-108">.@</span></span>  
 <span data-ttu-id="d4f61-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4f61-109">Required.</span></span> <span data-ttu-id="d4f61-110">Kennzeichnet den Anfang der Attribute Axis-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d4f61-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="d4f61-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d4f61-111">Optional.</span></span> <span data-ttu-id="d4f61-112">Kennzeichnet den Anfang des Namens des Attributs Wenn `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f61-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 `attribute`  
 <span data-ttu-id="d4f61-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4f61-113">Required.</span></span> <span data-ttu-id="d4f61-114">Der Name des Attributs des Formulars den Zugriff auf [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="d4f61-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="d4f61-115">Segment</span><span class="sxs-lookup"><span data-stu-id="d4f61-115">Part</span></span>|<span data-ttu-id="d4f61-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d4f61-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="d4f61-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d4f61-117">Optional.</span></span> <span data-ttu-id="d4f61-118">XML-Namespacepräfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="d4f61-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="d4f61-119">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d4f61-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="d4f61-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4f61-120">Required.</span></span> <span data-ttu-id="d4f61-121">Lokale Attributname.</span><span class="sxs-lookup"><span data-stu-id="d4f61-121">Local attribute name.</span></span> <span data-ttu-id="d4f61-122">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d4f61-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="d4f61-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="d4f61-123">Optional.</span></span> <span data-ttu-id="d4f61-124">Kennzeichnet das Ende des Namens des Attributs Wenn `attribute` ist kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f61-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4f61-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4f61-125">Return Value</span></span>  
 <span data-ttu-id="d4f61-126">Eine Zeichenfolge, die den Wert der enthält `attribute`.</span><span class="sxs-lookup"><span data-stu-id="d4f61-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="d4f61-127">Wenn der Attributname nicht vorhanden ist, `Nothing` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d4f61-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4f61-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4f61-128">Remarks</span></span>  
 <span data-ttu-id="d4f61-129">Können Sie den Wert eines Attributs anhand des Namens aus den Zugriff auf ein XML-Attributachseneigenschaft ein <xref:System.Xml.Linq.XElement> Objekt oder vom ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="d4f61-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="d4f61-130">Sie können einen Attributwert anhand des Namens abrufen oder hinzufügen ein neues Attributs auf ein Element unter Angabe eines neuen Namens vorangestellt der @ Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d4f61-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="d4f61-131">Bei Verweisen auf ein XML-Attribut mit dem @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben der <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d4f61-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="d4f61-132">Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d4f61-132">The naming rules for XML attributes differ from the naming rules for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] identifiers.</span></span> <span data-ttu-id="d4f61-133">Zugriff auf ein XML-Attribut mit dem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).</span><span class="sxs-lookup"><span data-stu-id="d4f61-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="d4f61-134">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="d4f61-134">XML Namespaces</span></span>  
 <span data-ttu-id="d4f61-135">Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert werden, mithilfe der `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d4f61-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="d4f61-136">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="d4f61-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="d4f61-137">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d4f61-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4f61-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4f61-138">Example</span></span>  
 <span data-ttu-id="d4f61-139">Im folgende Beispiel wird gezeigt, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen sind `phone`.</span><span class="sxs-lookup"><span data-stu-id="d4f61-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_1.vb)]  
  
 <span data-ttu-id="d4f61-140">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d4f61-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="d4f61-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4f61-141">Example</span></span>  
 <span data-ttu-id="d4f61-142">Im folgende Beispiel wird gezeigt, wie Attribute für ein XML-Element beide deklarativ als Teil des XML- und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von erstellt ein <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="d4f61-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="d4f61-143">Die `type` -Attribut wird deklarativ erstellt und die `owner` -Attribut wird dynamisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="d4f61-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_2.vb)]  
  
 <span data-ttu-id="d4f61-144">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d4f61-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="d4f61-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4f61-145">Example</span></span>  
 <span data-ttu-id="d4f61-146">Im folgenden Beispiel wird die Spitze Klammer-Syntax zum Abrufen des Werts der XML-Attribut mit dem Namen `number-type`, der kein gültiger Bezeichner in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d4f61-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [!code-vb[VbXMLSamples#13](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_3.vb)]  
  
 <span data-ttu-id="d4f61-147">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d4f61-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="d4f61-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4f61-148">Example</span></span>  
 <span data-ttu-id="d4f61-149">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="d4f61-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="d4f61-150">Es verwendet dann das Namespacepräfix ein XML-literal erstellt und Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="d4f61-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-attribute-axis-property_4.vb)]  
  
 <span data-ttu-id="d4f61-151">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="d4f61-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="d4f61-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4f61-152">See Also</span></span>  
 <xref:System.Xml.Linq.XElement>  
 [<span data-ttu-id="d4f61-153">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="d4f61-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [<span data-ttu-id="d4f61-154">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="d4f61-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="d4f61-155">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4f61-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [<span data-ttu-id="d4f61-156">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="d4f61-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
