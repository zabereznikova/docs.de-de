---
title: Zugreifen auf streng typisierte XML-Daten mit 'XPathNavigator'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
ms.openlocfilehash: fcf46a0716d79fd27cb06924bf74c119b8435147
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822827"
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a><span data-ttu-id="b9bf5-102">Zugreifen auf streng typisierte XML-Daten mit 'XPathNavigator'</span><span class="sxs-lookup"><span data-stu-id="b9bf5-102">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>
<span data-ttu-id="b9bf5-103">Als Instanz des XPath 2.0-Datenmodells kann die <xref:System.Xml.XPath.XPathNavigator>-Klasse stark typisierte Daten enthalten, die den CLR-Typen (Common Language Runtime) zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-103">As an instance of the XPath 2.0 data model, the <xref:System.Xml.XPath.XPathNavigator> class can contain strongly typed data that maps to common language runtime (CLR) types.</span></span> <span data-ttu-id="b9bf5-104">Gemäß des XPath 2.0-Datenmodells können nur Elemente und Attribute stark typisierte Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-104">According to the XPath 2.0 data model, only elements and attributes can contain strongly typed data.</span></span> <span data-ttu-id="b9bf5-105">Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt Mechanismen zum Zugreifen auf Daten in einem <xref:System.Xml.XPath.XPathDocument>-Objekt oder einem <xref:System.Xml.XmlDocument>-Objekt als stark typisierte Daten sowie Mechanismen zum Konvertieren von einem Datentyp in einen anderen bereit.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-105">The <xref:System.Xml.XPath.XPathNavigator> class provides mechanisms for accessing data within an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object as strongly typed data as well as mechanisms for converting from one data type to another.</span></span>  
  
## <a name="type-information-exposed-by-xpathnavigator"></a><span data-ttu-id="b9bf5-106">Von XPathNavigator verfügbar gemachte Typinformationen</span><span class="sxs-lookup"><span data-stu-id="b9bf5-106">Type Information Exposed by XPathNavigator</span></span>  
 <span data-ttu-id="b9bf5-107">XML 1.0-Daten weisen im Allgemeinen keinen Typ auf, es sei denn, sie wurden mit einer DTD, einem XSD-Schema (XML Schema Definition Language) oder anderen Mechanismen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-107">XML 1.0 data is technically without type, unless processed with a DTD, XML schema definition language (XSD) schema, or other mechanism.</span></span> <span data-ttu-id="b9bf5-108">Es gibt verschiedene Kategorien von Typinformationen, die einem XML-Element oder XML-Attribut zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-108">There are a number of categories of type information that can be associated with an XML element or attribute.</span></span>  
  
- <span data-ttu-id="b9bf5-109">Einfache CLR-Typen: Keine der XML-Schemasprachen unterstützt CLR-Typen (Common Language Runtime) direkt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-109">Simple CLR Types: None of the XML Schema languages support Common Language Runtime (CLR) types directly.</span></span> <span data-ttu-id="b9bf5-110">Da das Anzeigen des Inhalts von einfachen Elementen und Attributen im am besten geeigneten CLR-Typ hilfreich ist, können alle einfachen Inhalte als <xref:System.String> mit allen hinzugefügten Schemainformationen typisiert werden, die den Inhalt möglicherweise einem besser geeigneten Typ anpassen, ohne dass Schemainformationen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-110">Because it is useful to be able to view simple element and attribute content as the most appropriate CLR type, all simple content can be typed as <xref:System.String> in the absence of schema information with any added schema information potentially refining this content to a more appropriate type.</span></span> <span data-ttu-id="b9bf5-111">Mithilfe der <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>-Eigenschaft können Sie den am besten geeigneten CLR-Typ des Inhalts von einfachen Elementen und Attributen ermitteln.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-111">You can find the best matching CLR type of simple element and attribute content by using the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property.</span></span> <span data-ttu-id="b9bf5-112">Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-112">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="b9bf5-113">Liste der einfachen (CLR-)Typen: Ein Element oder Attribut mit einfachem Inhalt kann eine Liste mit Werten enthalten, die durch ein Leerzeichen voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-113">Lists of Simple (CLR) Types: An element or attribute with simple content can contain a list of values separated by white space.</span></span> <span data-ttu-id="b9bf5-114">Die Werte werden von einem XML-Schema als ein "list type" angegeben.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-114">The values are specified by an XML Schema to be a "list type."</span></span> <span data-ttu-id="b9bf5-115">Wenn kein XML-Schema vorhanden ist, wird einfacher Inhalt als ein einzelner Textknoten behandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-115">In the absence of an XML Schema, such simple content would be treated as a single text node.</span></span> <span data-ttu-id="b9bf5-116">Wenn ein XML-Schema verfügbar ist, kann dieser einfache Inhalt als eine Serie von atomaren Werten verfügbar gemacht werden, die alle einen einfachen Typ aufweisen, der einer Auflistung von CLR-Objekten zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-116">When an XML Schema is available, this simple content can be exposed as a series of atomic values each having a simple type that maps to a collection of CLR objects.</span></span> <span data-ttu-id="b9bf5-117">Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-117">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="b9bf5-118">Typisierter Wert: Ein für ein Schema validiertes Attribut oder Element mit einem einfachen Typ weist einen typisierten Wert auf.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-118">Typed Value: A schema-validated attribute or element with a simple type has a typed value.</span></span> <span data-ttu-id="b9bf5-119">Dieser Wert ist ein primitiver Typ, z. B. ein numerischer Typ, ein Zeichenfolgentyp oder ein Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-119">This value is a primitive type such as a numeric, string, or date type.</span></span> <span data-ttu-id="b9bf5-120">Alle integrierten einfachen Typen in XSD können CLR-Typen zugeordnet werden, die Zugriff auf den Wert eines Knotens als einen besser geeigneten Typ anstatt nur als einen <xref:System.String> bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-120">All the built-in simple types in XSD can be mapped to CLR types that provide access to the value of a node as a more appropriate type instead of just as a <xref:System.String>.</span></span> <span data-ttu-id="b9bf5-121">Ein Element mit Attributen oder untergeordneten Elementen wird als komplexer Typ betrachtet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-121">An element with attributes or element children is considered to be a complex type.</span></span> <span data-ttu-id="b9bf5-122">Der typisierte Wert eines komplexen Typs mit einfachem Inhalt (nur Textknoten als untergeordnete Elemente) ist der gleiche wie der Wert des einfachen Typs dieses Inhalts.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-122">The typed value of a complex type with simple content (only text nodes as children) is the same as that of the simple type of its content.</span></span> <span data-ttu-id="b9bf5-123">Der typisierte Wert eines komplexen Typs mit komplexem Inhalt (ein oder mehr untergeordnete Elemente) ist der Zeichenfolgenwert der Verkettung aller untergeordneten Textknoten, die als ein <xref:System.String> zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-123">The typed value of a complex type with complex content (one or more child elements) is the string value of the concatenation of all its child text nodes returned as a <xref:System.String>.</span></span> <span data-ttu-id="b9bf5-124">Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-124">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
- <span data-ttu-id="b9bf5-125">Schemasprachenspezifischer Typname: In den meisten Fällen werden die CLR-Typen, die als Nebeneffekt beim Übernehmen eines externen Schemas festgelegt werden, zum Bereitstellen des Zugriffs auf den Wert eines Knotens verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-125">Schema-Language Specific Type Name: In most cases, the CLR types, which are set as a side-effect of applying an external schema, are used to provide access to the value of a node.</span></span> <span data-ttu-id="b9bf5-126">In manchen Situationen ist es jedoch empfehlenswert, den Typ zu überprüfen, der einem bestimmten auf ein XML-Dokument angewendeten Schema zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-126">However, there may be situations where you may want to examine the type associated with a particular schema applied to an XML document.</span></span> <span data-ttu-id="b9bf5-127">Zum Beispiel möchten Sie möglicherweise ein XML-Dokument durchsuchen und dabei alle Elemente extrahieren, die Inhalt vom Typ "PurchaseOrder" gemäß eines zugewiesenen Schemas aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-127">For example, you may wish to search through an XML document, extracting all elements that are determined to have content of type "PurchaseOrder" according to an attached schema.</span></span> <span data-ttu-id="b9bf5-128">Diese Typinformationen können nur durch Schemavalidierung festgelegt werden. Auf diese Informationen wird über die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft und die <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-128">Such type information can be set only as a result of schema validation and this information is accessed through the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> and <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="b9bf5-129">Weitere Informationen finden Sie im Abschnitt „Das Post-Schema-Validation-Infoset (PSVI)“ weiter unten.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-129">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
- <span data-ttu-id="b9bf5-130">Schemasprachenspezifische Typreflektion: In anderen Fällen sollten Sie nähere Informationen zum schemaspezifischen Typ abrufen, der auf ein XML-Dokument angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-130">Schema-Language Specific Type Reflection: In other cases, you may want to obtain further details of the schema-specific type applied to an XML document.</span></span> <span data-ttu-id="b9bf5-131">Zum Beispiel möchten Sie eventuell beim Lesen einer XML-Datei die `maxOccurs`-Attribute aller gültigen Knoten im XML-Dokument extrahieren, um eine benutzerdefinierte Berechnung durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-131">For example, when reading an XML file, you may want to extract the `maxOccurs` attribute for each valid node in the XML document in order to perform some custom calculation.</span></span> <span data-ttu-id="b9bf5-132">Da diese Informationen nur durch Schemavalidierung festgelegt wird, wird darauf über die <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-132">Because this information is set only through schema validation, it is accessed through the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="b9bf5-133">Weitere Informationen finden Sie im Abschnitt „Das Post-Schema-Validation-Infoset (PSVI)“ weiter unten.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-133">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
## <a name="xpathnavigator-typed-accessors"></a><span data-ttu-id="b9bf5-134">Mit "XPathNavigator" typisierte Accessoren</span><span class="sxs-lookup"><span data-stu-id="b9bf5-134">XPathNavigator Typed Accessors</span></span>  
 <span data-ttu-id="b9bf5-135">Die folgenden Tabelle enthält die verschiedenen Eigenschaften und Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, mit denen auf die Typinformationen eines Knotens zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-135">The following table shows the various properties and methods of the <xref:System.Xml.XPath.XPathNavigator> class that can be used to access the type information about a node.</span></span>  
  
|<span data-ttu-id="b9bf5-136">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b9bf5-136">Property</span></span>|<span data-ttu-id="b9bf5-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9bf5-137">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|<span data-ttu-id="b9bf5-138">Dieses Objekt enthält die XML-Schematypinformationen des Knotens, sofern dieser gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-138">This contains the XML schema type information for the node if it is valid.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|<span data-ttu-id="b9bf5-139">Dieses Objekt enthält das Post-Schema-Validation-Infoset des Knotens, der nach der Validierung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-139">This contains the Post Schema Validation Infoset of the node that is added after validation.</span></span> <span data-ttu-id="b9bf5-140">Darin sind die XML-Schematypinformationen sowie die Gültigkeitsinformationen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-140">This includes the XML schema type information, as well as validity information.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|<span data-ttu-id="b9bf5-141">Der CLR-Typ des typisierten Werts des Knotens.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-141">The CLR type of the typed value of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|<span data-ttu-id="b9bf5-142">Der Inhalt des Knotens als mindestens ein CLR-Wert, dessen Typ am ehesten dem XML-Schematyp des Knotens entspricht.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-142">The content of the node as one or more CLR values whose type is the closest match to the XML schema type of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|<span data-ttu-id="b9bf5-143">Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Boolean> in einen `xs:boolean`-Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-143">The <xref:System.String> value of the current node cast to a <xref:System.Boolean> value, according to the XPath 2.0 casting rules for `xs:boolean`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|<span data-ttu-id="b9bf5-144">Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.DateTime> in einen `xs:datetime`-Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-144">The <xref:System.String> value of the current node cast to a <xref:System.DateTime> value, according to the XPath 2.0 casting rules for `xs:datetime`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|<span data-ttu-id="b9bf5-145">Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Double> in einen `xsd:double`-Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-145">The <xref:System.String> value of the current node cast to a <xref:System.Double> value, according to the XPath 2.0 casting rules for `xsd:double`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|<span data-ttu-id="b9bf5-146">Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Int32> in einen `xs:integer`-Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-146">The <xref:System.String> value of the current node cast to a <xref:System.Int32> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|<span data-ttu-id="b9bf5-147">Der <xref:System.String>-Wert des aktuellen Knotens, gemäß der Umwandlungsregeln für XPath 2.0 für <xref:System.Int64> in einen `xs:integer`-Wert umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-147">The <xref:System.String> value of the current node cast to a <xref:System.Int64> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|<span data-ttu-id="b9bf5-148">Der Inhalt des Knotens, gemäß der Umwandlungsregeln für XPath 2.0 in den Zieltyp umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-148">The contents of the node cast to the target type according to the XPath 2.0 casting rules.</span></span>|  
  
 <span data-ttu-id="b9bf5-149">Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-149">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="the-post-schema-validation-infoset-psvi"></a><span data-ttu-id="b9bf5-150">Das Post-Schema-Validation-Infoset (PSVI)</span><span class="sxs-lookup"><span data-stu-id="b9bf5-150">The Post Schema Validation Infoset (PSVI)</span></span>  
 <span data-ttu-id="b9bf5-151">Ein XML-Schemaprozessor akzeptiert ein XML-Infoset als Eingabe und konvertiert es in ein Post-Schema-Validation-Infoset (PSVI).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-151">An XML Schema processor accepts an XML Infoset as input and converts it into a Post Schema Validation Infoset (PSVI).</span></span> <span data-ttu-id="b9bf5-152">Ein PSVI stellt das ursprüngliche Eingabe-XML-Infoset dar, dem neue Informationselemente hinzugefügt wurden. Vorhandenen Informationselementen wurden neue Eigenschaften hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-152">A PSVI is the original input XML infoset with new information items added and new properties added to existing information items.</span></span> <span data-ttu-id="b9bf5-153">Es gibt drei komplexe Klassen von Informationen, die dem XML-Infoset im PSVI hinzugefügt wurden und vom <xref:System.Xml.XPath.XPathNavigator> verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-153">There are three broad classes of information added to the XML Infoset in the PSVI that are exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
1. <span data-ttu-id="b9bf5-154">Validierungsergebnisse: Informationen dazu, ob ein Element oder ein Attribut erfolgreich validiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-154">Validation Outcomes: Information as to whether an element or attribute was successfully validated or not.</span></span> <span data-ttu-id="b9bf5-155">Diese werden von der <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-155">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
2. <span data-ttu-id="b9bf5-156">Standardinformationen: Angaben dazu, ob der Wert des Elements oder des Attributs über im Schema angegebene Standardwerte abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-156">Default Information: Indications as to whether the value of the element or attribute was obtained via default values specified in the schema or not.</span></span> <span data-ttu-id="b9bf5-157">Diese werden von der <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-157">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
3. <span data-ttu-id="b9bf5-158">Typanmerkungen: Verweise auf Schemakomponenten, die möglicherweise Typdefinitionen oder Element- und Attributdeklarationen sind.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-158">Type Annotations: References to schema components that may be type definitions or element and attribute declarations.</span></span> <span data-ttu-id="b9bf5-159">Die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft von <xref:System.Xml.XPath.XPathNavigator> enthält die bestimmten Typinformationen des Knotens, sofern dieser gültig ist.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-159">The <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property of the <xref:System.Xml.XPath.XPathNavigator> contains the specific type information of the node if it is valid.</span></span> <span data-ttu-id="b9bf5-160">Wenn die Gültigkeit eines Knotens unbekannt ist, das heißt, er wurde überprüft und anschließend bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-160">If the validity of a node is unknown, such as when it was validated then subsequently edited.</span></span> <span data-ttu-id="b9bf5-161">dann wird die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft auf `null` festgelegt, wobei die Typinformationen jedoch weiterhin in den verschiedenen Eigenschaften der <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-161">then the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property is set to `null` but type information is still available from the various properties of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="b9bf5-162">Im folgenden Beispiel wird das Verwenden der Informationen im Post-Schema-Validation-Infoset veranschaulicht, die von <xref:System.Xml.XPath.XPathNavigator> verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-162">The following example illustrates using information in the Post Schema Validation Infoset exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 <span data-ttu-id="b9bf5-163">In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-163">The example takes the `books.xml` file as input.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="b9bf5-164">In diesem Beispiel wird auch das `books.xsd`-Schema als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-164">The example also takes the `books.xsd` schema as input.</span></span>  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"
attributeFormDefault="unqualified" elementFormDefault="qualified"
targetNamespace="http://www.contoso.com/books"
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a><span data-ttu-id="b9bf5-165">Abrufen von typisierten Werten mithilfe von ValueAs-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b9bf5-165">Obtain Typed Values Using ValueAs Properties</span></span>  
 <span data-ttu-id="b9bf5-166">Der typisierte Wert eines Knotens kann durch Zugreifen auf die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft von <xref:System.Xml.XPath.XPathNavigator> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-166">The typed value of a node can be retrieved by accessing the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="b9bf5-167">In bestimmten Fällen soll der typisierte Wert eines Knotens möglicherweise in einen anderen Typ konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-167">In certain cases you may want to convert the typed value of a node to a different type.</span></span> <span data-ttu-id="b9bf5-168">Ein häufig verwendetes Beispiel ist das Abrufen eines numerischen Werts aus einem XML-Knoten.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-168">A common example is to get a numeric value from an XML node.</span></span> <span data-ttu-id="b9bf5-169">Betrachten Sie z. B. das folgende nicht validierte und nicht typisierte XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-169">For example, consider the following unvalidated and untyped XML document.</span></span>  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="b9bf5-170">Wenn <xref:System.Xml.XPath.XPathNavigator> auf dem `price`-Element positioniert wird, ist die <xref:System.Xml.XPath.XPathNavigator.XmlType%2A>-Eigenschaft `null`, die <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>-Eigenschaft ist <xref:System.String> und die <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>-Eigenschaft entspricht der Zeichenfolge `10.00`.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-170">If the <xref:System.Xml.XPath.XPathNavigator> is positioned on the `price` element the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property would be `null`, the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property would be <xref:System.String>, and the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property would be the string `10.00`.</span></span>  
  
 <span data-ttu-id="b9bf5-171">Es ist jedoch trotzdem möglich, den Wert mithilfe der Methoden und Eigenschaften <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> und <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> als einen numerischen Wert zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-171">However, it is still possible to extract the value as a numeric value using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>, or <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> method and properties.</span></span> <span data-ttu-id="b9bf5-172">Im folgenden Beispiel wird das Durchführen einer solchen Umwandlung mithilfe der <xref:System.Xml.XPath.XPathItem.ValueAs%2A>-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b9bf5-172">The following example illustrates performing such a cast using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A> method.</span></span>  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 <span data-ttu-id="b9bf5-173">Weitere Informationen zum Zuordnen von integrierten Schematypen zu CLR-Typen finden Sie unter [Typenunterstützung in den System.Xml-Klassen](type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="b9bf5-173">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9bf5-174">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9bf5-174">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="b9bf5-175">Type Support in the System.Xml Classes (Typenunterstützung in den System.Xml-Klassen)</span><span class="sxs-lookup"><span data-stu-id="b9bf5-175">Type Support in the System.Xml Classes</span></span>](type-support-in-the-system-xml-classes.md)
- [<span data-ttu-id="b9bf5-176">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="b9bf5-176">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="b9bf5-177">Navigieren in Knotengruppen mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b9bf5-177">Node Set Navigation Using XPathNavigator</span></span>](node-set-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="b9bf5-178">Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b9bf5-178">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [<span data-ttu-id="b9bf5-179">Extrahieren von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="b9bf5-179">Extract XML Data Using XPathNavigator</span></span>](extract-xml-data-using-xpathnavigator.md)
