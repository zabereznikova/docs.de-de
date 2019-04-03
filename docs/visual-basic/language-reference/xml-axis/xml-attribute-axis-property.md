---
title: XML-Attributachseneigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: a7a93608d14bcbec316228b59467b23e9247e043
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828803"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="ec7ea-102">XML-Attributachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec7ea-102">XML Attribute Axis Property (Visual Basic)</span></span>
<span data-ttu-id="ec7ea-103">Ermöglicht den Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec7ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec7ea-104">Syntax</span></span>  
  
```  
      object.@attribute  
-or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="ec7ea-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ec7ea-105">Parts</span></span>  
 `object`  
 <span data-ttu-id="ec7ea-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-106">Required.</span></span> <span data-ttu-id="ec7ea-107">Ein <xref:System.Xml.Linq.XElement> Objekt oder eine Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="ec7ea-108">.@</span><span class="sxs-lookup"><span data-stu-id="ec7ea-108">.@</span></span>  
 <span data-ttu-id="ec7ea-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-109">Required.</span></span> <span data-ttu-id="ec7ea-110">Gibt den Anfang einer Attributachseneigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="ec7ea-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-111">Optional.</span></span> <span data-ttu-id="ec7ea-112">Kennzeichnet den Anfang des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner im Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="ec7ea-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-113">Required.</span></span> <span data-ttu-id="ec7ea-114">Der Name des Attributs, das die Form den Zugriff auf [`prefix`:]`name`.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="ec7ea-115">Segment</span><span class="sxs-lookup"><span data-stu-id="ec7ea-115">Part</span></span>|<span data-ttu-id="ec7ea-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec7ea-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="ec7ea-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-117">Optional.</span></span> <span data-ttu-id="ec7ea-118">XML-Namespacepräfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="ec7ea-119">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="ec7ea-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-120">Required.</span></span> <span data-ttu-id="ec7ea-121">Lokale Attributname.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-121">Local attribute name.</span></span> <span data-ttu-id="ec7ea-122">Finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="ec7ea-122">See [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="ec7ea-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-123">Optional.</span></span> <span data-ttu-id="ec7ea-124">Kennzeichnet das Ende des Namens des Attributs bei `attribute` ist kein gültiger Bezeichner im Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec7ea-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ec7ea-125">Return Value</span></span>  
 <span data-ttu-id="ec7ea-126">Eine Zeichenfolge, die den Wert der enthält `attribute`.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="ec7ea-127">Wenn Sie der Attributnamen nicht vorhanden ist, `Nothing` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec7ea-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec7ea-128">Remarks</span></span>  
 <span data-ttu-id="ec7ea-129">Können Sie eine XML-Attributachseneigenschaft Zugriff auf den Wert eines Attributs aus anhand des Namens einer <xref:System.Xml.Linq.XElement> Objekt oder vom ersten Element in einer Auflistung von <xref:System.Xml.Linq.XElement> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ec7ea-130">Sie können einen Attributwert Name abrufen oder hinzufügen ein neues Attributs zu einem Element durch einen neuen Namen mit vorangestellten Angabe der @ Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="ec7ea-131">Bei Verweisen auf ein XML-Attribut mit der @ Bezeichner, den Wert des Attributs als Zeichenfolge zurückgegeben, und Sie müssen nicht explizit angeben, die <xref:System.Xml.Linq.XAttribute.Value%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="ec7ea-132">Die Benennungsregeln für XML-Attribute unterscheiden sich von den Benennungsregeln für Visual Basic-Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="ec7ea-133">Zugriff auf ein XML-Attribut mit einem Namen, der kein gültiger Visual Basic-Bezeichner ist, schließen Sie den Namen in spitzen Klammern (\< und >).</span><span class="sxs-lookup"><span data-stu-id="ec7ea-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="ec7ea-134">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="ec7ea-134">XML Namespaces</span></span>  
 <span data-ttu-id="ec7ea-135">Der Name in einem Attributachseneigenschaft können nur XML-Namespacepräfixe global deklariert werden, indem die `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="ec7ea-136">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="ec7ea-137">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="ec7ea-137">For more information, see [Imports Statement (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec7ea-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec7ea-138">Example</span></span>  
 <span data-ttu-id="ec7ea-139">Das folgende Beispiel zeigt, wie Sie die Werte der XML-Attribute mit dem Namen abrufen `type` aus einer Auflistung von XML-Elementen mit dem Namen `phone`.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="ec7ea-140">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec7ea-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="ec7ea-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec7ea-141">Example</span></span>  
 <span data-ttu-id="ec7ea-142">Das folgende Beispiel zeigt die zum Erstellen von Attributen für ein XML-Element sowohl deklarativ als Teil der XML-Code, und dynamisch durch Hinzufügen eines Attributs zu einer Instanz von einem <xref:System.Xml.Linq.XElement> Objekt.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="ec7ea-143">Die `type` -Attribut wird deklarativ erstellt und die `owner` Attribut wird dynamisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="ec7ea-144">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec7ea-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="ec7ea-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec7ea-145">Example</span></span>  
 <span data-ttu-id="ec7ea-146">Im folgenden Beispiel wird die Spitze Klammer-Syntax, um den Wert des XML-Attributs mit dem Namen abzurufen `number-type`, das ist nicht in Visual Basic ein gültiger Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="ec7ea-147">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec7ea-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="ec7ea-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec7ea-148">Example</span></span>  
 <span data-ttu-id="ec7ea-149">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="ec7ea-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="ec7ea-150">Klicken Sie dann das Namespacepräfix des Namespace eine XML-literal erstellt und der Zugriff auf den ersten untergeordneten Knoten mit dem qualifizierten Namen verwendet "`ns:name`".</span><span class="sxs-lookup"><span data-stu-id="ec7ea-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="ec7ea-151">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ec7ea-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="ec7ea-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec7ea-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="ec7ea-153">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="ec7ea-153">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="ec7ea-154">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="ec7ea-154">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="ec7ea-155">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ec7ea-155">Creating XML in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="ec7ea-156">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="ec7ea-156">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
