---
title: Erstellen von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: adc1a10bb9acb14ee88589c13e28c49773e42100
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291590"
---
# <a name="building-xml-schemas"></a><span data-ttu-id="b8ccc-102">Erstellen von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="b8ccc-102">Building XML Schemas</span></span>
<span data-ttu-id="b8ccc-103">Die Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace werden den Strukturen zugeordnet, die in der XML-Schemaempfehlung des W3C (World Wide Web Consortium) definiert sind, und können zum speicherinternen Erstellen von XML-Schemata verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-103">The classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation and can be used to build XML schemas in-memory.</span></span>  
  
## <a name="building-an-xml-schema"></a><span data-ttu-id="b8ccc-104">Erstellen eines XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-104">Building an XML Schema</span></span>  
 <span data-ttu-id="b8ccc-105">Im folgenden Codebeispiel wird mithilfe der SOM-API speicherintern ein Kunden-XML-Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-105">In the code examples that follow, the SOM API is used to build a customer XML schema in-memory.</span></span>  
  
### <a name="creating-element-and-attributes"></a><span data-ttu-id="b8ccc-106">Erstellen von Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="b8ccc-106">Creating Element and Attributes</span></span>  
 <span data-ttu-id="b8ccc-107">In den Codebeispielen werden die Kundenschemata von unten nach oben erstellt, wobei zuerst die untergeordneten Elemente und Attribute und die entsprechenden Typen erstellt werden, und dann die Elemente der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-107">The code examples build the customer schema from the bottom up, creating the child elements, attributes, and their corresponding types first, and then the top-level elements.</span></span>  
  
 <span data-ttu-id="b8ccc-108">Im folgenden Codebeispiel werden das `FirstName`-Element und das `LastName`-Element sowie das `CustomerId`-Attribut des Kundenschemas mithilfe der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse des SOMs erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-108">In the following code example, the `FirstName` and `LastName` elements, as well as the `CustomerId` attribute of the customer schema are created using the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes of the SOM.</span></span> <span data-ttu-id="b8ccc-109">Außer der <xref:System.Xml.Schema.XmlSchemaElement.Name%2A>-Eigenschaften der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse, die dem "name"-Attribut des `<xs:element />`-Elements und des `<xs:attribute />`-Elements in einem XML-Schema entsprechen, verfügen alle anderen im Schema zulässigen Attribute (`defaultValue`, `fixedValue`, `form` usw.) über entsprechende Eigenschaften in der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-109">Apart from the <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> properties of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes, which correspond to the "name" attribute of the `<xs:element />` and `<xs:attribute />` elements in an XML schema, all other attributes allowed by the schema (`defaultValue`, `fixedValue`, `form`, and so on) have corresponding properties in the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a><span data-ttu-id="b8ccc-110">Erstellen von Schematypen</span><span class="sxs-lookup"><span data-stu-id="b8ccc-110">Creating Schema Types</span></span>  
 <span data-ttu-id="b8ccc-111">Der Inhalt von Elementen und Attributen wird von den jeweiligen Typen definiert.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-111">The content of elements and attributes is defined by their types.</span></span> <span data-ttu-id="b8ccc-112">Zum Erstellen von Elementen und Attributen, deren Typen einem der integrierten Schematypen entsprechen, wird die <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse mithilfe der <xref:System.Xml.XmlQualifiedName>-Klasse mit dem entsprechenden qualifizierten Namen des integrierten Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-112">To create elements and attributes whose types are one of the built-in schema types, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes are set with the corresponding qualified name of the built-in type using the <xref:System.Xml.XmlQualifiedName> class.</span></span> <span data-ttu-id="b8ccc-113">Zum Erstellen eines benutzerdefinierten Typs für Elemente und Attribute wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSimpleType>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaComplexType>-Klasse ein neuer einfacher oder komplexer Typ erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-113">To create a user-defined type for elements and attributes, a new simple or complex type is created using the <xref:System.Xml.Schema.XmlSchemaSimpleType> or <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8ccc-114">Zum Erstellen unbenannter einfacher oder komplexer Typen, die anonyme untergeordnete Elemente eines Elements oder Attributs sind (für Attribute gelten nur einfache Typen), legen Sie die <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse anstelle der <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A>-Eigenschaft der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaAttribute>-Klasse auf den unbenannten einfachen oder komplexen Typ fest.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-114">To create unnamed simple or complex types that are anonymous children of an element or attribute (only simple types apply for attributes), set the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes to the unnamed simple or complex type, instead of the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 <span data-ttu-id="b8ccc-115">Bei XML-Schemata können durch Einschränkung anonyme und benannte einfache Typen von anderen einfachen Typen (integriert oder benutzerdefiniert) abgeleitet werden. Außerdem können diese als Liste oder Union von anderen einfachen Typen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-115">XML schemas allow both anonymous and named simple types to be derived by restriction from other simple types (built-in or user-defined) or constructed as a list or union of other simple types.</span></span> <span data-ttu-id="b8ccc-116">Mithilfe der <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>-Klasse wird ein einfacher Typ durch Einschränkung des integrierten `xs:string`-Typs erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-116">The <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> class is used to create a simple type by restricting the built-in `xs:string` type.</span></span> <span data-ttu-id="b8ccc-117">Sie können auch mit der <xref:System.Xml.Schema.XmlSchemaSimpleTypeList>-Klasse oder der <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion>-Klasse Listentypen oder Union-Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-117">You can also use the <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> or <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> classes to create list or union types.</span></span> <span data-ttu-id="b8ccc-118">Die <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob es sich um eine Einschränkung, eine Liste oder eine Union von einem einfachen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-118">The <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> property denotes whether it is a simple type restriction, list, or union.</span></span>  
  
 <span data-ttu-id="b8ccc-119">Im folgenden Codebeispiel ist der Typ des `FirstName`-Elements der integrierte Typ `xs:string`. Der Typ des `LastName`-Elements ist ein benannter einfacher Typ, der eine Einschränkung des integrierten Typs `xs:string` mit einem Wert des `MaxLength`-Facets von 20 ist. Der Typ des `CustomerId`-Attributs ist der integrierte Typ `xs:positiveInteger`.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-119">In the following code example, the `FirstName` element's type is the built-in type `xs:string`, the `LastName` element's type is a named simple type that is a restriction of the built-in type `xs:string`, with a `MaxLength` facet value of 20, and the `CustomerId` attribute's type is the built-in type `xs:positiveInteger`.</span></span> <span data-ttu-id="b8ccc-120">Das `Customer`-Element ist ein anonymer komplexer Typ, dessen Partikel eine Sequenz des `FirstName`-Elements und des `LastName`-Elements ist und dessen Attribute das `CustomerId`-Attribut enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-120">The `Customer` element is an anonymous complex type whose particle is the sequence of the `FirstName` and `LastName` elements and whose attributes contains the `CustomerId` attribute.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8ccc-121">Die <xref:System.Xml.Schema.XmlSchemaChoice>-Klasse und die <xref:System.Xml.Schema.XmlSchemaAll>-Klasse können auch als Partikel des komplexen Typs zum Replizieren der `<xs:choice />`-Semantik oder der `<xs:all />`-Semantik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-121">You can also use the <xref:System.Xml.Schema.XmlSchemaChoice> or <xref:System.Xml.Schema.XmlSchemaAll> classes as the particle of the complex type to replicate `<xs:choice />` or `<xs:all />` semantics.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a><span data-ttu-id="b8ccc-122">Erstellen und Kompilieren von Schemata</span><span class="sxs-lookup"><span data-stu-id="b8ccc-122">Creating and Compiling Schemas</span></span>  
 <span data-ttu-id="b8ccc-123">Bisher wurden die untergeordneten Elemente und Attribute, deren jeweilige Typen und das `Customer`-Element der obersten Ebene speicherintern mithilfe der SOM-API erstellt.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-123">At this point, the child elements and attributes, their corresponding types, and the top-level `Customer` element have been created in-memory using the SOM API.</span></span> <span data-ttu-id="b8ccc-124">Im folgenden Codebeispiel wird das Schemaelement mithilfe der <xref:System.Xml.Schema.XmlSchema>-Klasse erstellt, diesem werden die Elemente und Typen der obersten Ebene mithilfe der <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType>-Eigenschaft hinzugefügt, und das gesamte Schema wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse kompiliert und auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-124">In the following code example, the schema element is created using the <xref:System.Xml.Schema.XmlSchema> class, the top-level elements and types are added to it using the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> property and the complete schema is compiled using the <xref:System.Xml.Schema.XmlSchemaSet> class and written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 <span data-ttu-id="b8ccc-125">Die <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType>-Methode validiert das Kundenschema anhand der Regeln für ein XML-Schema und macht Post-Schema-Compilation-Eigenschaften verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-125">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> method validates the customer schema against the rules for an XML schema and makes post-schema-compilation properties available.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8ccc-126">Alle Post-Schema-Compilation-Eigenschaften in der SOM-API weichen vom Post-Schema-Validation-Infoset ab.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-126">All post-schema-compilation properties in the SOM API differ from the Post-Schema-Validation-Infoset.</span></span>  
  
 <span data-ttu-id="b8ccc-127">Der dem <xref:System.Xml.Schema.ValidationEventHandler> hinzugefügte <xref:System.Xml.Schema.XmlSchemaSet> ist ein Delegat, der die Rückrufmethode `ValidationCallback` zum Behandeln der Schemavalidierungswarnungen und -fehler aufruft.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-127">The <xref:System.Xml.Schema.ValidationEventHandler> added to the <xref:System.Xml.Schema.XmlSchemaSet> is a delegate that calls the callback method `ValidationCallback` to handle schema validation warnings and errors.</span></span>  
  
 <span data-ttu-id="b8ccc-128">Im Folgenden wird das gesamte Codebeispiel dargestellt und das Kundenschema auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b8ccc-128">The following is the complete code example, and the customer schema written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="Customer">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="FirstName" type="xs:string" />  
            <xs:element name="LastName" type="tns:LastNameType" />  
         </xs:sequence>  
         <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="LastNameType">  
      <xs:restriction base="xs:string">  
         <xs:maxLength value="20" />  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8ccc-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8ccc-129">See also</span></span>

- [<span data-ttu-id="b8ccc-130">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="b8ccc-130">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="b8ccc-131">Lesen und Schreiben von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-131">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="b8ccc-132">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-132">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="b8ccc-133">Bearbeiten von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-133">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="b8ccc-134">Einfügen oder Importieren von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-134">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="b8ccc-135">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="b8ccc-135">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="b8ccc-136">Post-Schema-Compilation-Infoset</span><span class="sxs-lookup"><span data-stu-id="b8ccc-136">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
