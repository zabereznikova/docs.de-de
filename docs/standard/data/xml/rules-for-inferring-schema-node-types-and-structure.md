---
title: Regeln für Rückschlussschemaknotentypen und Struktur
ms.date: 03/30/2017
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
ms.openlocfilehash: e49e50dc21951d739b12cdfa60c6a48f67576873
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697596"
---
# <a name="rules-for-inferring-schema-node-types-and-structure"></a><span data-ttu-id="1f96d-102">Regeln für Rückschlussschemaknotentypen und Struktur</span><span class="sxs-lookup"><span data-stu-id="1f96d-102">Rules for Inferring Schema Node Types and Structure</span></span>

<span data-ttu-id="1f96d-103">In diesem Thema wird beschrieben, wie der Schemarückschlussprozess die in einem XML-Dokument auftretenden Knotentypen in eine XSD-Struktur (XML Schema Definition) übersetzt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-103">This topic describes how the schema inference process translates the node types in an XML document to an XML Schema definition language (XSD) structure.</span></span>  
  
## <a name="element-inference-rules"></a><span data-ttu-id="1f96d-104">Rückschlussregeln für Elemente</span><span class="sxs-lookup"><span data-stu-id="1f96d-104">Element Inference Rules</span></span>  

 <span data-ttu-id="1f96d-105">In diesem Abschnitt werden die Rückschlussregeln für Elementdeklarationen erläutert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-105">This section describes the inference rules for element declarations.</span></span> <span data-ttu-id="1f96d-106">Es existieren acht Strukturen zur Elementdeklaration, die hergeleitet werden können:</span><span class="sxs-lookup"><span data-stu-id="1f96d-106">There are eight structures of element declarations that will be inferred:</span></span>  
  
1. <span data-ttu-id="1f96d-107">Einfaches Element</span><span class="sxs-lookup"><span data-stu-id="1f96d-107">Element of simple type</span></span>  
  
2. <span data-ttu-id="1f96d-108">Leeres Element</span><span class="sxs-lookup"><span data-stu-id="1f96d-108">Empty element</span></span>  
  
3. <span data-ttu-id="1f96d-109">Leeres Element mit Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-109">Empty element with attributes</span></span>  
  
4. <span data-ttu-id="1f96d-110">Element mit Attributen und einfachem Inhalt</span><span class="sxs-lookup"><span data-stu-id="1f96d-110">Element with attributes and simple content</span></span>  
  
5. <span data-ttu-id="1f96d-111">Element mit einer Sequenz von direkt untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="1f96d-111">Element with a sequence of child elements</span></span>  
  
6. <span data-ttu-id="1f96d-112">Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-112">Element with a sequence of child elements and attributes</span></span>  
  
7. <span data-ttu-id="1f96d-113">Element mit einer Sequenz von Auswahlmöglichkeiten direkt untergeordneter Elemente</span><span class="sxs-lookup"><span data-stu-id="1f96d-113">Element with a sequence of choices of child elements</span></span>  
  
8. <span data-ttu-id="1f96d-114">Element mit einer Sequenz von Auswahlmöglichkeiten direkt untergeordneter Elemente und Attribute</span><span class="sxs-lookup"><span data-stu-id="1f96d-114">Element with a sequence of choices of child elements and attributes</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f96d-115">Alle `complexType`-Deklarationen werden als anonyme Typen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1f96d-115">All `complexType` declarations are inferred as anonymous types.</span></span> <span data-ttu-id="1f96d-116">Das einzige globale hergeleitete Element ist das Stammelement. Alle anderen Elemente sind lokal.</span><span class="sxs-lookup"><span data-stu-id="1f96d-116">The only global element inferred is the root element; all other elements are local.</span></span>  
  
 <span data-ttu-id="1f96d-117">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-117">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
### <a name="simple-typed-element"></a><span data-ttu-id="1f96d-118">Element eines einfachen Typs</span><span class="sxs-lookup"><span data-stu-id="1f96d-118">Simple Typed Element</span></span>  

 <span data-ttu-id="1f96d-119">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-119">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-120">Das fett formatierte Element stellt das Schema dar, das für das Element eines einfachen Typs hergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="1f96d-120">The bolded element shows the schema inferred for the simple type element.</span></span>  
  
 <span data-ttu-id="1f96d-121">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-121">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-122">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-122">XML</span></span>|<span data-ttu-id="1f96d-123">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-123">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root" type="xs:string" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element"></a><span data-ttu-id="1f96d-124">Leeres Element</span><span class="sxs-lookup"><span data-stu-id="1f96d-124">Empty Element</span></span>  

 <span data-ttu-id="1f96d-125">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-125">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-126">Das fett formatierte Element stellt das für das leere Element hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-126">The bolded element shows the schema inferred for the empty element.</span></span>  
  
 <span data-ttu-id="1f96d-127">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-127">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-128">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-128">XML</span></span>|<span data-ttu-id="1f96d-129">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-129">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty" />`<br /><br /> `</xs:schema>`|  
  
### <a name="empty-element-with-attributes"></a><span data-ttu-id="1f96d-130">Leeres Element mit Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-130">Empty Element with Attributes</span></span>  

 <span data-ttu-id="1f96d-131">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-131">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-132">Die fett formatierten Elemente stellen das für das leere Element mit Attributen hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-132">The bolded elements show the schema inferred for the empty element with attributes.</span></span>  
  
 <span data-ttu-id="1f96d-133">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-133">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-134">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-134">XML</span></span>|<span data-ttu-id="1f96d-135">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-135">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="empty">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-attributes-and-simple-content"></a><span data-ttu-id="1f96d-136">Element mit Attributen und einfachem Inhalt</span><span class="sxs-lookup"><span data-stu-id="1f96d-136">Element with Attributes and Simple Content</span></span>  

 <span data-ttu-id="1f96d-137">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-137">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-138">Die fett formatierten Elemente stellen das für ein Element mit Attributen und einfachem Inhalt hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-138">The bolded elements show the schema inferred for an element with attributes and simple content.</span></span>  
  
 <span data-ttu-id="1f96d-139">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-139">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-140">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-140">XML</span></span>|<span data-ttu-id="1f96d-141">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-141">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:simpleContent>`<br /><br /> `<xs:extension base="xs:string">`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:extension>`<br /><br /> `</xs:simpleContent>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements"></a><span data-ttu-id="1f96d-142">Element mit einer Sequenz von direkt untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="1f96d-142">Element with a Sequence of Child Elements</span></span>  

 <span data-ttu-id="1f96d-143">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-143">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-144">Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz von direkt untergeordneten Elementen hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-144">The bolded elements show the schema inferred for an element with a sequence of child elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f96d-145">Ein Element wird auch wie eine Sequenz behandelt, wenn es nur über ein direkt untergeordnetes Element verfügt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-145">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="1f96d-146">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-146">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-147">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-147">XML</span></span>|<span data-ttu-id="1f96d-148">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-148">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement" />`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-of-child-elements-and-attributes"></a><span data-ttu-id="1f96d-149">Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-149">Element with a Sequence of Child Elements and Attributes</span></span>  

 <span data-ttu-id="1f96d-150">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-150">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-151">Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz von direkt untergeordneten Elementen und Attributen hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-151">The bolded elements show the schema inferred for an element with a sequence of child elements and attributes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f96d-152">Ein Element wird auch wie eine Sequenz behandelt, wenn es nur über ein direkt untergeordnetes Element verfügt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-152">Even if an element has only one child element, it is still treated as a sequence.</span></span>  
  
 <span data-ttu-id="1f96d-153">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-153">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-154">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-154">XML</span></span>|<span data-ttu-id="1f96d-155">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-155">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choices-of-child-elements"></a><span data-ttu-id="1f96d-156">Element mit einer Sequenz und Auswahlmöglichkeiten von direkt untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="1f96d-156">Element with a Sequence and Choices of Child Elements</span></span>  

 <span data-ttu-id="1f96d-157">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-157">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-158">Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz und Auswahlmöglichkeiten von direkt untergeordneten Elementen hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-158">The bolded elements show the schema inferred for an element with a sequence and choice of child elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f96d-159">Das `maxOccurs`-Attribut des `xs:choice`-Elements wird im hergeleiteten Schema auf `"unbounded"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-159">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="1f96d-160">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-160">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-161">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-161">XML</span></span>|<span data-ttu-id="1f96d-162">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-162">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="element-with-a-sequence-and-choice-of-child-elements-and-attributes"></a><span data-ttu-id="1f96d-163">Element mit einer Sequenz und Auswahlmöglichkeit von direkt untergeordneten Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-163">Element with a Sequence and Choice of Child Elements and Attributes</span></span>  

 <span data-ttu-id="1f96d-164">In der folgenden Tabelle wird die XML-Eingabe für die <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A>-Methode und das generierte XML-Schema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-164">The following table shows the XML input to the <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> method, and the XML schema generated.</span></span> <span data-ttu-id="1f96d-165">Die fett formatierten Elemente stellen das für ein Element mit einer Sequenz und Auswahlmöglichkeit von direkt untergeordneten Elementen und Attributen hergeleitete Schema dar.</span><span class="sxs-lookup"><span data-stu-id="1f96d-165">The bolded elements show the schema inferred for an element with a sequence and choice of child elements and attributes.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f96d-166">Das `maxOccurs`-Attribut des `xs:choice`-Elements wird im hergeleiteten Schema auf `"unbounded"` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-166">The `maxOccurs` attribute of the `xs:choice` element is set to `"unbounded"` in the inferred schema.</span></span>  
  
 <span data-ttu-id="1f96d-167">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-167">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
|<span data-ttu-id="1f96d-168">XML</span><span class="sxs-lookup"><span data-stu-id="1f96d-168">XML</span></span>|<span data-ttu-id="1f96d-169">Schema</span><span class="sxs-lookup"><span data-stu-id="1f96d-169">Schema</span></span>|  
|---------|------------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> `<xs:element name="root">`<br /><br /> `<xs:complexType>`<br /><br /> `<xs:sequence>`<br /><br /> `<xs:choice maxOccurs="unbounded">`<br /><br /> `<xs:element name="subElement1" />`<br /><br /> `<xs:element name="subElement2" />`<br /><br /> `</xs:choice>`<br /><br /> `</xs:sequence>`<br /><br /> `<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `</xs:complexType>`<br /><br /> `</xs:element>`<br /><br /> `</xs:schema>`|  
  
### <a name="attribute-processing"></a><span data-ttu-id="1f96d-170">Verarbeitung von Attributen</span><span class="sxs-lookup"><span data-stu-id="1f96d-170">Attribute Processing</span></span>  

 <span data-ttu-id="1f96d-171">Sobald eine neues Attribut in einem Knoten auftritt, wird es der hergeleiteten Definition des Knotens mit `use="required"` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-171">Whenever a new attribute is encountered within a node, it is added to the inferred definition of the node with `use="required"`.</span></span> <span data-ttu-id="1f96d-172">Wenn derselbe Knoten das nächste Mal in der Instanz gefunden wird, werden die Attribute der aktuellen Instanz mit den bereits hergeleiteten im Rückschlussprozess verglichen.</span><span class="sxs-lookup"><span data-stu-id="1f96d-172">The next time the same node is found in the instance, the inference process will compare attributes of the current instance with the ones already inferred.</span></span> <span data-ttu-id="1f96d-173">Wenn einige der bereits hergeleiteten Attribute in der Instanz nicht vorhanden sind, wird der Attributdefinition `use="optional"` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-173">If some of the already inferred ones are missing in the instance, `use="optional"` is added to the attribute definition.</span></span> <span data-ttu-id="1f96d-174">Neue Attribute werden vorhandenen Deklarationen mit `use="optional"` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-174">New attributes are added to existing declarations with `use="optional"`.</span></span>  
  
### <a name="occurrence-constraints"></a><span data-ttu-id="1f96d-175">Beschränkungen hinsichtlich des Vorkommens</span><span class="sxs-lookup"><span data-stu-id="1f96d-175">Occurrence Constraints</span></span>  

 <span data-ttu-id="1f96d-176">Während des Schemarückschlussprozesses wird das `minOccurs`-Attribut und das `maxOccurs`-Attribut mit den Werten `"0"` oder `"1"` und `"1"` oder `"unbounded"` für hergeleitete Komponenten eines Schemas generiert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-176">During the schema inference process, the `minOccurs` and `maxOccurs` attributes are generated, for inferred components of a schema, with the values `"0"` or `"1"` and `"1"` or `"unbounded"`.</span></span> <span data-ttu-id="1f96d-177">Die Werte `"1"` und `"unbounded"` werden nur verwendet, wenn die Werte `"0"` und `"1"` keine Validierung für das XML-Dokument durchführen können (wenn `MinOccurs="0"` ein Element beispielsweise nicht genau beschreibt, wird `minOccurs="1"` verwendet).</span><span class="sxs-lookup"><span data-stu-id="1f96d-177">The values `"1"` and `"unbounded"` are used only when the values `"0"` and `"1"` cannot validate the XML document (for example, if `MinOccurs="0"` does not accurately describe an element, `minOccurs="1"` is used).</span></span>  
  
### <a name="mixed-content"></a><span data-ttu-id="1f96d-178">Gemischter Inhalt</span><span class="sxs-lookup"><span data-stu-id="1f96d-178">Mixed Content</span></span>  

 <span data-ttu-id="1f96d-179">Wenn ein Element gemischte Inhalte (z. B. Text mit eingefügten Elementen) enthält, wird das `mixed="true"`-Attribut für die hergeleitete komplexe Typdefinition generiert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-179">If an element contains mixed content (for example text interspersed with elements), the `mixed="true"` attribute is generated for the inferred complex type definition.</span></span>  
  
## <a name="other-node-type-inference-rules"></a><span data-ttu-id="1f96d-180">Rückschlussregeln für andere Knotentypen</span><span class="sxs-lookup"><span data-stu-id="1f96d-180">Other Node Type Inference Rules</span></span>  

 <span data-ttu-id="1f96d-181">In der folgenden Tabelle sind Rückschlussregeln für Verarbeitungsanweisungs-, Kommentar-, Entitätsverweis-, CDATA-, Dokumenttypen- und Namespaceknoten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1f96d-181">The following table describes the inference rules for processing instruction, comment, entity reference, CDATA, document type, and namespace nodes.</span></span>  
  
|<span data-ttu-id="1f96d-182">Knotentyp</span><span class="sxs-lookup"><span data-stu-id="1f96d-182">Node Type</span></span>|<span data-ttu-id="1f96d-183">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="1f96d-183">Translation</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1f96d-184">Verarbeitungsanweisung</span><span class="sxs-lookup"><span data-stu-id="1f96d-184">Processing instruction</span></span>|<span data-ttu-id="1f96d-185">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-185">Ignored.</span></span>|  
|<span data-ttu-id="1f96d-186">Kommentar</span><span class="sxs-lookup"><span data-stu-id="1f96d-186">Comment</span></span>|<span data-ttu-id="1f96d-187">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-187">Ignored.</span></span>|  
|<span data-ttu-id="1f96d-188">Entitätsverweis</span><span class="sxs-lookup"><span data-stu-id="1f96d-188">Entity reference</span></span>|<span data-ttu-id="1f96d-189">Die <xref:System.Xml.Schema.XmlSchemaInference>-Klasse behandelt keine Entitätsverweise.</span><span class="sxs-lookup"><span data-stu-id="1f96d-189">The <xref:System.Xml.Schema.XmlSchemaInference> class does not handle entity references.</span></span> <span data-ttu-id="1f96d-190">Wenn ein XML-Dokument Entitätsverweise enthält, müssen Sie einen Reader verwenden, der die Entitäten erweitert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-190">If an XML document contains entity references, you need to use a reader that expands the entities.</span></span> <span data-ttu-id="1f96d-191">Sie können beispielsweise eine <xref:System.Xml.XmlTextReader>-Klasse mit der <xref:System.Xml.XmlTextReader.EntityHandling%2A>-Eigenschaft übergeben, die auf den <xref:System.Xml.EntityHandling.ExpandEntities>-Member als Parameter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1f96d-191">For example, you can pass an <xref:System.Xml.XmlTextReader> with the <xref:System.Xml.XmlTextReader.EntityHandling%2A> property set to <xref:System.Xml.EntityHandling.ExpandEntities> as a parameter.</span></span> <span data-ttu-id="1f96d-192">Wenn Entitätsverweise auftreten und der Reader Entitäten nicht erweitert, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1f96d-192">If entity references are encountered and the reader does not expand entities, an exception is throw.</span></span>|  
|<span data-ttu-id="1f96d-193">CDATA</span><span class="sxs-lookup"><span data-stu-id="1f96d-193">CDATA</span></span>|<span data-ttu-id="1f96d-194">Alle `<![CDATA[ … ]]`-Abschnitte in einem XML-Dokument werden als `xs:string` hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="1f96d-194">Any `<![CDATA[ … ]]` sections in an XML document will be inferred as `xs:string`.</span></span>|  
|<span data-ttu-id="1f96d-195">Dokumenttyp</span><span class="sxs-lookup"><span data-stu-id="1f96d-195">Document type</span></span>|<span data-ttu-id="1f96d-196">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-196">Ignored.</span></span>|  
|<span data-ttu-id="1f96d-197">Namespaces</span><span class="sxs-lookup"><span data-stu-id="1f96d-197">Namespaces</span></span>|<span data-ttu-id="1f96d-198">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1f96d-198">Ignored.</span></span>|  
  
 <span data-ttu-id="1f96d-199">Weitere Informationen zum Schemarückschlussprozess finden Sie unter [Herleiten von Schemata aus XML-Dokumenten](inferring-schemas-from-xml-documents.md).</span><span class="sxs-lookup"><span data-stu-id="1f96d-199">For more information about the schema inference process, see [Inferring Schemas from XML Documents](inferring-schemas-from-xml-documents.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f96d-200">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f96d-200">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaInference>
- [<span data-ttu-id="1f96d-201">XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))</span><span class="sxs-lookup"><span data-stu-id="1f96d-201">XML Schema Object Model (SOM)</span></span>](xml-schema-object-model-som.md)
- [<span data-ttu-id="1f96d-202">Herleiten eines XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="1f96d-202">Inferring an XML Schema</span></span>](inferring-an-xml-schema.md)
- [<span data-ttu-id="1f96d-203">Herleiten von Schemas aus XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="1f96d-203">Inferring Schemas from XML Documents</span></span>](inferring-schemas-from-xml-documents.md)
- [<span data-ttu-id="1f96d-204">Regeln zum Herleiten einfacher Typen</span><span class="sxs-lookup"><span data-stu-id="1f96d-204">Rules for Inferring Simple Types</span></span>](rules-for-inferring-simple-types.md)
