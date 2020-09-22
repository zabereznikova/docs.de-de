---
title: XML Attribute Axis Property
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
ms.openlocfilehash: 9eddd132b2d4dd6ffbd935a0c8c57a03a3d65435
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869434"
---
# <a name="xml-attribute-axis-property-visual-basic"></a><span data-ttu-id="1e832-102">XML-Attributachseneigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e832-102">XML Attribute Axis Property (Visual Basic)</span></span>

<span data-ttu-id="1e832-103">Bietet Zugriff auf den Wert eines Attributs für ein <xref:System.Xml.Linq.XElement> Objekt oder auf das erste Element in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten.</span><span class="sxs-lookup"><span data-stu-id="1e832-103">Provides access to the value of an attribute for an <xref:System.Xml.Linq.XElement> object or to the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e832-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1e832-104">Syntax</span></span>  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a><span data-ttu-id="1e832-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1e832-105">Parts</span></span>  

 `object`  
 <span data-ttu-id="1e832-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e832-106">Required.</span></span> <span data-ttu-id="1e832-107">Ein- <xref:System.Xml.Linq.XElement> Objekt oder eine Auflistung von- <xref:System.Xml.Linq.XElement> Objekten.</span><span class="sxs-lookup"><span data-stu-id="1e832-107">An <xref:System.Xml.Linq.XElement> object or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="1e832-108">.@</span><span class="sxs-lookup"><span data-stu-id="1e832-108">.@</span></span>  
 <span data-ttu-id="1e832-109">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e832-109">Required.</span></span> <span data-ttu-id="1e832-110">Gibt den Anfang einer Attribut Achsen Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1e832-110">Denotes the start of an attribute axis property.</span></span>  
  
 <  
 <span data-ttu-id="1e832-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1e832-111">Optional.</span></span> <span data-ttu-id="1e832-112">Gibt den Anfang des Namens des Attributs an, wenn `attribute` in Visual Basic kein gültiger Bezeichner ist.</span><span class="sxs-lookup"><span data-stu-id="1e832-112">Denotes the beginning of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
 `attribute`  
 <span data-ttu-id="1e832-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e832-113">Required.</span></span> <span data-ttu-id="1e832-114">Der Name des Attributs, auf das im Format [ `prefix` :] zugegriffen werden soll `name` .</span><span class="sxs-lookup"><span data-stu-id="1e832-114">Name of the attribute to access, of the form [`prefix`:]`name`.</span></span>  
  
|<span data-ttu-id="1e832-115">Teil</span><span class="sxs-lookup"><span data-stu-id="1e832-115">Part</span></span>|<span data-ttu-id="1e832-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1e832-116">Description</span></span>|  
|----------|-----------------|  
|`prefix`|<span data-ttu-id="1e832-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1e832-117">Optional.</span></span> <span data-ttu-id="1e832-118">Das XML-Namespace Präfix für das Attribut.</span><span class="sxs-lookup"><span data-stu-id="1e832-118">XML namespace prefix for the attribute.</span></span> <span data-ttu-id="1e832-119">Muss ein globaler XML-Namespace sein, der mit einer `Imports`-Anweisung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1e832-119">Must be a global XML namespace defined with an `Imports` statement.</span></span>|  
|`name`|<span data-ttu-id="1e832-120">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1e832-120">Required.</span></span> <span data-ttu-id="1e832-121">Name des lokalen Attributs.</span><span class="sxs-lookup"><span data-stu-id="1e832-121">Local attribute name.</span></span> <span data-ttu-id="1e832-122">Siehe [Namen von deklarierten XML-Elementen und Attributen](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1e832-122">See [Names of Declared XML Elements and Attributes](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>|  
  
 \>  
 <span data-ttu-id="1e832-123">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1e832-123">Optional.</span></span> <span data-ttu-id="1e832-124">Bezeichnet das Ende des Namens des Attributs, wenn `attribute` kein gültiger Bezeichner in Visual Basic ist.</span><span class="sxs-lookup"><span data-stu-id="1e832-124">Denotes the end of the name of the attribute when `attribute` is not a valid identifier in Visual Basic.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e832-125">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1e832-125">Return Value</span></span>  

 <span data-ttu-id="1e832-126">Eine Zeichenfolge, die den Wert von enthält `attribute` .</span><span class="sxs-lookup"><span data-stu-id="1e832-126">A string that contains the value of `attribute`.</span></span> <span data-ttu-id="1e832-127">Wenn der Attribut Name nicht vorhanden ist, `Nothing` wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1e832-127">If the attribute name does not exist, `Nothing` is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e832-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1e832-128">Remarks</span></span>  

 <span data-ttu-id="1e832-129">Sie können eine XML-Attribut Achsen Eigenschaft verwenden, um auf den Wert eines Attributs anhand des Namens aus einem <xref:System.Xml.Linq.XElement> Objekt oder aus dem ersten Element in einer Auflistung von- <xref:System.Xml.Linq.XElement> Objekten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1e832-129">You can use an XML attribute axis property to access the value of an attribute by name from an <xref:System.Xml.Linq.XElement> object or from the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="1e832-130">Sie können einen Attribut Wert anhand des Namens abrufen oder einem Element ein neues Attribut hinzufügen, indem Sie einen neuen Namen mit vorangestelltem @-Bezeichner angeben.</span><span class="sxs-lookup"><span data-stu-id="1e832-130">You can retrieve an attribute value by name, or add a new attribute to an element by specifying a new name preceded by the @ identifier.</span></span>  
  
 <span data-ttu-id="1e832-131">Wenn Sie auf ein XML-Attribut mit dem @-Bezeichner verweisen, wird der-Attribut Wert als Zeichenfolge zurückgegeben, und Sie müssen die-Eigenschaft nicht explizit angeben <xref:System.Xml.Linq.XAttribute.Value%2A> .</span><span class="sxs-lookup"><span data-stu-id="1e832-131">When you refer to an XML attribute using the @ identifier, the attribute value is returned as a string and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>  
  
 <span data-ttu-id="1e832-132">Die Benennungs Regeln für XML-Attribute unterscheiden sich von den Benennungs Regeln für Visual Basic Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="1e832-132">The naming rules for XML attributes differ from the naming rules for Visual Basic identifiers.</span></span> <span data-ttu-id="1e832-133">Um auf ein XML-Attribut zuzugreifen, das über einen Namen verfügt, der kein gültiger Visual Basic Bezeichner ist, müssen Sie den Namen in spitzen Klammern ( \< and > ) einschließen.</span><span class="sxs-lookup"><span data-stu-id="1e832-133">To access an XML attribute that has a name that is not a valid Visual Basic identifier, enclose the name in angle brackets (\< and >).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="1e832-134">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="1e832-134">XML Namespaces</span></span>  

 <span data-ttu-id="1e832-135">Der Name in einer Attribut Achsen Eigenschaft kann nur XML-Namespace Präfixe verwenden, die Global mithilfe der-Anweisung deklariert werden `Imports` .</span><span class="sxs-lookup"><span data-stu-id="1e832-135">The name in an attribute axis property can use only XML namespace prefixes declared globally by using the `Imports` statement.</span></span> <span data-ttu-id="1e832-136">Es können keine XML-Namespacepräfixe verwendet werden, die lokal innerhalb von XML-Elementliteralen deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="1e832-136">It cannot use XML namespace prefixes declared locally within XML element literals.</span></span> <span data-ttu-id="1e832-137">Weitere Informationen finden Sie unter [Imports-Anweisung (XML-Namespace)](../statements/imports-statement-xml-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="1e832-137">For more information, see [Imports Statement (XML Namespace)](../statements/imports-statement-xml-namespace.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e832-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e832-138">Example</span></span>  

 <span data-ttu-id="1e832-139">Im folgenden Beispiel wird gezeigt, wie Sie die Werte der XML-Attribute aus einer Auflistung von XML-Elementen mit dem Namen "" `type` aus einer Auflistung von XML-Elementen `phone`</span><span class="sxs-lookup"><span data-stu-id="1e832-139">The following example shows how to get the values of the XML attributes named `type` from a collection of XML elements that are named `phone`.</span></span>  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 <span data-ttu-id="1e832-140">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e832-140">This code displays the following text:</span></span>  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a><span data-ttu-id="1e832-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e832-141">Example</span></span>  

 <span data-ttu-id="1e832-142">Im folgenden Beispiel wird gezeigt, wie Attribute für ein XML-Element sowohl deklarativ als auch als Teil des XML-Codes erstellt werden, und dynamisch durch Hinzufügen eines Attributs zu einer Instanz eines <xref:System.Xml.Linq.XElement> Objekts.</span><span class="sxs-lookup"><span data-stu-id="1e832-142">The following example shows how to create attributes for an XML element both declaratively, as part of the XML, and dynamically by adding an attribute to an instance of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="1e832-143">Das `type` Attribut wird deklarativ erstellt, und das `owner` Attribut wird dynamisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="1e832-143">The `type` attribute is created declaratively and the `owner` attribute is created dynamically.</span></span>  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 <span data-ttu-id="1e832-144">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e832-144">This code displays the following text:</span></span>  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a><span data-ttu-id="1e832-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e832-145">Example</span></span>  

 <span data-ttu-id="1e832-146">Im folgenden Beispiel wird die Spitze Klammer Syntax verwendet, um den Wert des XML-Attributs mit dem Namen zu erhalten `number-type` , der kein gültiger Bezeichner in Visual Basic ist.</span><span class="sxs-lookup"><span data-stu-id="1e832-146">The following example uses the angle bracket syntax to get the value of the XML attribute named `number-type`, which is not a valid identifier in Visual Basic.</span></span>  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 <span data-ttu-id="1e832-147">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e832-147">This code displays the following text:</span></span>  
  
 `Phone type: work`  
  
## <a name="example"></a><span data-ttu-id="1e832-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1e832-148">Example</span></span>  

 <span data-ttu-id="1e832-149">Das folgende Beispiel deklariert `ns` als ein XML-Namespacepräfix.</span><span class="sxs-lookup"><span data-stu-id="1e832-149">The following example declares `ns` as an XML namespace prefix.</span></span> <span data-ttu-id="1e832-150">Anschließend wird das Präfix des-Namespace verwendet, um ein XML-Literalelement zu erstellen und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen " `ns:name` " zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1e832-150">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name "`ns:name`".</span></span>  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 <span data-ttu-id="1e832-151">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1e832-151">This code displays the following text:</span></span>  
  
 `Phone type: home`  
  
## <a name="see-also"></a><span data-ttu-id="1e832-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1e832-152">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- [<span data-ttu-id="1e832-153">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1e832-153">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="1e832-154">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="1e832-154">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="1e832-155">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1e832-155">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="1e832-156">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="1e832-156">Names of Declared XML Elements and Attributes</span></span>](../../programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
