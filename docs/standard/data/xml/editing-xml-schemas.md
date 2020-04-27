---
title: Bearbeiten von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: d7d9f8e0d4ec2f343b50e68e942bf94e93576f25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710946"
---
# <a name="editing-xml-schemas"></a><span data-ttu-id="4a0c3-102">Bearbeiten von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="4a0c3-102">Editing XML Schemas</span></span>

<span data-ttu-id="4a0c3-103">Die Bearbeitung von XML-Schemata ist eines der wichtigsten Funktionen des Schemaobjektmodells (SOM).</span><span class="sxs-lookup"><span data-stu-id="4a0c3-103">Editing an XML schema is one of the most important features of the Schema Object Model (SOM).</span></span> <span data-ttu-id="4a0c3-104">Alle Eigenschaften des SOM vor der Kompilierung des Schemas können zum Ändern der vorhandenen Werte eines XML-Schemas verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-104">All of the pre-schema-compilation properties of the SOM can be used to change the existing values in an XML schema.</span></span> <span data-ttu-id="4a0c3-105">Das XML-Schema kann dann erneut kompiliert werden, um die Änderungen widerzuspiegeln.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-105">The XML schema can then be recompiled to reflect the changes.</span></span>

<span data-ttu-id="4a0c3-106">Der erste Bearbeitungsschritt eines in das DOM geladenen Schemas ist das Durchlaufen des Schemas.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-106">The first step in editing a schema loaded into the SOM is to traverse the schema.</span></span> <span data-ttu-id="4a0c3-107">Sie sollten mit dem Durchlaufen eines Schemas mithilfe der SOM-API vertraut sein, bevor Sie versuchen, ein Schema zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-107">You should be familiar with traversing a schema using the SOM API before you attempt to edit a schema.</span></span> <span data-ttu-id="4a0c3-108">Sie sollten auch mit den Eigenschaften vor und nach der Kompilierung des Schemas im Post-Schema-Compilation-Infoset (PSCI) vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-108">You should also be familiar with the pre- and post-schema-compilation properties of the Post-Schema-Compilation-Infoset (PSCI).</span></span>

## <a name="editing-an-xml-schema"></a><span data-ttu-id="4a0c3-109">Bearbeiten eines XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-109">Editing an XML Schema</span></span>

<span data-ttu-id="4a0c3-110">In diesem Abschnitt finden Sie zwei Codebeispiele, in denen das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellte Kundenschema bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-110">In this section, two code examples are provided, both of which edit the customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span> <span data-ttu-id="4a0c3-111">Im ersten Codebeispiel wird dem `PhoneNumber`-Element ein neues `Customer`-Element hinzugefügt, und im zweiten Codebeispiel wird dem `Title`-Element ein neues `FirstName`-Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-111">The first code example adds a new `PhoneNumber` element to the `Customer` element and the second code example adds a new `Title` attribute to the `FirstName` element.</span></span> <span data-ttu-id="4a0c3-112">Im ersten Beispiel wird die <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas zum Durchlaufen des Kundenschemas verwendet, während im zweiten Codebeispiel die <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-112">The first sample also uses the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection as the means of traversing the customer schema while the second code example uses the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

### <a name="phonenumber-element-example"></a><span data-ttu-id="4a0c3-113">Beispiel: "PhoneNumber"-Element</span><span class="sxs-lookup"><span data-stu-id="4a0c3-113">PhoneNumber Element Example</span></span>

<span data-ttu-id="4a0c3-114">Im ersten Codebeispiel wird dem `PhoneNumber`-Element des Kundenschemas ein neues `Customer`-Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-114">This first code example adds a new `PhoneNumber` element to the `Customer` element of the customer schema.</span></span> <span data-ttu-id="4a0c3-115">Im Codebeispiel wird das Kundenschema in den folgenden Schritten bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-115">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="4a0c3-116">Fügt das Kundenschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert es anschließend.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-116">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="4a0c3-117">Alle beim Lesen oder Kompilieren des Schemas aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-117">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="4a0c3-118">Ruft das kompilierte <xref:System.Xml.Schema.XmlSchema>-Objekt aus <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-118">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="4a0c3-119">Da das Schema kompiliert ist, kann auf die Eigenschaften im PSCI zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-119">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="4a0c3-120">Erstellt mithilfe der `PhoneNumber`-Klasse das <xref:System.Xml.Schema.XmlSchemaElement>-Element und mithilfe der `xs:string`-Klasse und der <xref:System.Xml.Schema.XmlSchemaSimpleType>-Klasse die Einschränkung des einfachen <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>-Typs. Fügt außerdem der <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A>-Eigenschaft der Einschränkung ein pattern<xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A>-Facet hinzu, und fügt der <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A>-Eigenschaft des einfachen Typs die Einschränkung sowie dem `PhoneNumber` des -Elements den einfachen Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-120">Creates the `PhoneNumber` element using the <xref:System.Xml.Schema.XmlSchemaElement> class, the `xs:string` simple type restriction using the <xref:System.Xml.Schema.XmlSchemaSimpleType> and <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> classes, adds a pattern facet to the <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> property of the restriction, and adds the restriction to the <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> property of the simple type and the simple type to the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> of the `PhoneNumber` element.</span></span>

4. <span data-ttu-id="4a0c3-121">Durchläuft jedes <xref:System.Xml.Schema.XmlSchemaElement> in der <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A>-Auflistung der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-121">Iterates over each <xref:System.Xml.Schema.XmlSchemaElement> in the <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> collection of the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span>

5. <span data-ttu-id="4a0c3-122">Ruft mithilfe der <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Klasse den komplexen Typ des `"Customer"`-Elements ab und mithilfe der `Customer`-Klasse den sequence<xref:System.Xml.Schema.XmlSchemaComplexType>-Partikel des komplexen Typs, wenn der <xref:System.Xml.Schema.XmlSchemaSequence> des Elements  ist.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-122">If the <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> of the element is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

6. <span data-ttu-id="4a0c3-123">Fügt der Sequenz mit dem vorhandenen `PhoneNumber`-Element und dem vorhandenen `FirstName`-Element mithilfe der `LastName`-Auflistung vor der Kompilierung des Schemas das neue <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-123">Adds the new `PhoneNumber` element to the sequence containing the existing `FirstName` and `LastName` elements using the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> collection of the sequence.</span></span>

7. <span data-ttu-id="4a0c3-124">Schließlich wird das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-124">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="4a0c3-125">Nachfolgend ist das vollständige Codebeispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-125">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

<span data-ttu-id="4a0c3-126">Im Folgenden finden Sie das geänderte Kundenschema, das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-126">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="xs:string" />
        <xs:element name="LastName" type="tns:LastNameType" />
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

### <a name="title-attribute-example"></a><span data-ttu-id="4a0c3-127">Beispiel: "Title"-Attribut</span><span class="sxs-lookup"><span data-stu-id="4a0c3-127">Title Attribute Example</span></span>

<span data-ttu-id="4a0c3-128">Im zweiten Codebeispiel wird dem `Title`-Element des Kundenschemas ein neues `FirstName`-Attribut hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-128">This second code example, adds a new `Title` attribute to the `FirstName` element of the customer schema.</span></span> <span data-ttu-id="4a0c3-129">Im ersten Codebeispiel ist der Typ des `FirstName`-Elements `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-129">In the first code example, the type of the `FirstName` element is `xs:string`.</span></span> <span data-ttu-id="4a0c3-130">Da das `FirstName`-Element ein Attribut mit Zeichenfolgeninhalt enthalten soll, muss sein Typ mit einem Inhaltsmodell zur Erweiterung einfachen Inhalts in einen komplexen Typ geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-130">For the `FirstName` element to have an attribute along with string content, its type must be changed to a complex type with a simple content extension content model.</span></span>

<span data-ttu-id="4a0c3-131">Im Codebeispiel wird das Kundenschema in den folgenden Schritten bearbeitet.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-131">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="4a0c3-132">Fügt das Kundenschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert es anschließend.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-132">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="4a0c3-133">Alle beim Lesen oder Kompilieren des Schemas aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-133">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="4a0c3-134">Ruft das kompilierte <xref:System.Xml.Schema.XmlSchema>-Objekt aus <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-134">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="4a0c3-135">Da das Schema kompiliert ist, kann auf die Eigenschaften im PSCI zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-135">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="4a0c3-136">Erstellt mithilfe der `FirstName`-Klasse einen neuen komplexen Typ für das <xref:System.Xml.Schema.XmlSchemaComplexType>-Element.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-136">Creates a new complex type for the `FirstName` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>

4. <span data-ttu-id="4a0c3-137">Erstellt mithilfe der `xs:string`-Klasse und der <xref:System.Xml.Schema.XmlSchemaSimpleContent>-Klasse eine neue Erweiterung für einfachen Inhalt mit dem Basistyp <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-137">Creates a new simple content extension, with a base type of `xs:string`, using the <xref:System.Xml.Schema.XmlSchemaSimpleContent> and <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension> classes.</span></span>

5. <span data-ttu-id="4a0c3-138">Erstellt mithilfe der `Title`-Klasse das neue <xref:System.Xml.Schema.XmlSchemaAttribute>-Attribut mit dem <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> von `xs:string`, und fügt der Erweiterung für einfachen Inhalt das Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-138">Creates the new `Title` attribute using the <xref:System.Xml.Schema.XmlSchemaAttribute> class, with a <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> of `xs:string` and adds the attribute to the simple content extension.</span></span>

6. <span data-ttu-id="4a0c3-139">Legt das Inhaltsmodell für einfachen Inhalt auf die Erweiterung für einfachen Inhalt und das Inhaltsmodell für den komplexen Typ auf den einfachen Inhalt fest.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-139">Sets the content model of the simple content to the simple content extension and the content model of the complex type to the simple content.</span></span>

7. <span data-ttu-id="4a0c3-140">Fügt der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas den neuen komplexen Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-140">Adds the new complex type to the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

8. <span data-ttu-id="4a0c3-141">Durchläuft alle <xref:System.Xml.Schema.XmlSchemaObject> in der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-141">Iterates over each <xref:System.Xml.Schema.XmlSchemaObject> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

> [!NOTE]
> <span data-ttu-id="4a0c3-142">Da das `FirstName`-Element in diesem Schema kein globales Element ist, ist es in der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung oder der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-142">Because the `FirstName` element is not a global element in the schema, it is not available in the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> or <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collections.</span></span> <span data-ttu-id="4a0c3-143">Im Codebeispiel wird das `FirstName`-Element gefunden, indem zuerst nach dem `Customer`-Element gesucht wird.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-143">The code example locates the `FirstName` element by first locating the `Customer` element.</span></span>
>
> <span data-ttu-id="4a0c3-144">Im ersten Codebeispiel wird das Schema mithilfe der <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>-Auflistung nach der Kompilierung des Schemas durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-144">The first code example traversed the schema using the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="4a0c3-145">In diesem Beispiel wird das Schema mithilfe der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-145">In this sample, the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection is used to traverse the schema.</span></span> <span data-ttu-id="4a0c3-146">Während beide Auflistungen den Zugriff auf die globalen Elemente im Schema bereitstellen, ist das Durchlaufen der <xref:System.Xml.Schema.XmlSchema.Items%2A>-Auflistung zeitaufwendiger, da alle globalen Elemente im Schema durchlaufen werden müssen und das Schema keine PSCI-Eigenschaften aufweist.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-146">While both collections provide access to the global elements in the schema, iterating through the <xref:System.Xml.Schema.XmlSchema.Items%2A> collection is more time consuming because you must iterate over all global elements in the schema and it does not have any PSCI properties.</span></span> <span data-ttu-id="4a0c3-147">Die PSCI-Auflistungen (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType> usw.) bieten direkten Zugriff auf die globalen Elemente, Attribute und Typen mit den PSCI-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-147">The PSCI collections (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, and so on) provide direct access to their global elements, attributes, and types and their PSCI properties.</span></span>

1. <span data-ttu-id="4a0c3-148">Ruft mithilfe der <xref:System.Xml.Schema.XmlSchemaObject>-Klasse den komplexen Typ des <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Elements ab sowie mithilfe der `"Customer"`-Klasse den sequence`Customer`-Partikel des komplexen Typs, wenn das <xref:System.Xml.Schema.XmlSchemaComplexType> ein Element ist, dessen <xref:System.Xml.Schema.XmlSchemaSequence> gleich  ist.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-148">If the <xref:System.Xml.Schema.XmlSchemaObject> is an element, whose <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

2. <span data-ttu-id="4a0c3-149">Durchläuft alle <xref:System.Xml.Schema.XmlSchemaParticle> in der <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType>-Auflistung vor der Kompilierung des Schemas.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-149">Iterates over each <xref:System.Xml.Schema.XmlSchemaParticle> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="4a0c3-150">Legt den <xref:System.Xml.Schema.XmlSchemaParticle> des <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A>-Elements auf den neuen komplexen `"FirstName"`-Typ fest, wenn <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> ein Element ist, dessen `FirstName` gleich `FirstName` ist.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-150">If the <xref:System.Xml.Schema.XmlSchemaParticle> is an element, who's <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"FirstName"`, sets the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> of the `FirstName` element to the new `FirstName` complex type.</span></span>

4. <span data-ttu-id="4a0c3-151">Schließlich wird das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-151">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="4a0c3-152">Nachfolgend ist das vollständige Codebeispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-152">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

<span data-ttu-id="4a0c3-153">Im Folgenden finden Sie das geänderte Kundenschema, das im Thema [Erstellen von XML-Schemata](../../../../docs/standard/data/xml/building-xml-schemas.md) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a0c3-153">The following is the modified customer schema created in the [Building XML Schemas](../../../../docs/standard/data/xml/building-xml-schemas.md) topic.</span></span>

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
        <xs:element name="LastName" type="tns:LastNameType" />
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="4a0c3-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a0c3-154">See also</span></span>

- [<span data-ttu-id="4a0c3-155">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="4a0c3-155">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="4a0c3-156">Lesen und Schreiben von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-156">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="4a0c3-157">Erstellen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-157">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="4a0c3-158">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-158">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="4a0c3-159">Einfügen oder Importieren von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-159">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="4a0c3-160">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="4a0c3-160">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="4a0c3-161">Post-Schema-Compilation-Infoset</span><span class="sxs-lookup"><span data-stu-id="4a0c3-161">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
