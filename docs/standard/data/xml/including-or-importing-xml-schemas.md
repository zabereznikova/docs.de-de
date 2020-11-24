---
title: Einfügen oder Importieren von XML-Schemata
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
ms.openlocfilehash: f382165ca8e2b972c47a080244a3d0054b5eb604
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822736"
---
# <a name="including-or-importing-xml-schemas"></a><span data-ttu-id="a11ef-102">Einfügen oder Importieren von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="a11ef-102">Including or Importing XML Schemas</span></span>
<span data-ttu-id="a11ef-103">Ein XML-Schema kann die Elemente `<xs:import />`, `<xs:include />` und `<xs:redefine />` enthalten.</span><span class="sxs-lookup"><span data-stu-id="a11ef-103">An XML schema may contain `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements.</span></span> <span data-ttu-id="a11ef-104">Diese Schemaelemente verweisen auf andere XML-Schemata, mit denen die Struktur des Schemas ergänzt werden kann, in das Sie eingefügt bzw. importiert werden.</span><span class="sxs-lookup"><span data-stu-id="a11ef-104">These schema elements refer to other XML schemas that can be used to supplement the structure of the schema that includes or imports them.</span></span> <span data-ttu-id="a11ef-105">Im SOM-API (Schemaobjektmodell) werden die Klassen <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> und <xref:System.Xml.Schema.XmlSchemaRedefine> diesen Elementen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a11ef-105">The <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, map to these elements in the Schema Object Model (SOM) API.</span></span>  
  
## <a name="including-or-importing-an-xml-schema"></a><span data-ttu-id="a11ef-106">Einfügen oder Importieren eines XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-106">Including or Importing an XML Schema</span></span>  
 <span data-ttu-id="a11ef-107">Das folgende Codebeispiel ergänzt das im Thema [Erstellen von XML-Schemas](building-xml-schemas.md) erstellte Kundenschema mit dem Adressschema.</span><span class="sxs-lookup"><span data-stu-id="a11ef-107">The following code example supplements the customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic with the address schema.</span></span> <span data-ttu-id="a11ef-108">Wenn das Kundenschema mit dem Adressschema ergänzt wird, werden Adresstypen im Kundenschema verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a11ef-108">Supplementing the customer schema with the address schema makes address types available in the customer schema.</span></span>  
  
 <span data-ttu-id="a11ef-109">Das Adressschema kann mithilfe des `<xs:include />`-Elements oder des `<xs:import />`-Elements eingebunden werden, um Komponenten des Adressschemas im vorliegenden Zustand zu verwenden. Es kann auch mithilfe eines `<xs:redefine />`-Elements zum Ändern der Komponenten verwendet werden, um die Anforderungen des Kundenschemas zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a11ef-109">The address schema can be incorporated using either `<xs:include />` or `<xs:import />` elements to use the components of the address schema as-is, or using an `<xs:redefine />` element to modify any of its components to suit the need of the customer schema.</span></span> <span data-ttu-id="a11ef-110">Da das Adressschema einen `targetNamespace` aufweist, der sich von dem des Kundenschemas unterscheidet, wird Importsemantik in Form des `<xs:import />`-Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="a11ef-110">Because the address schema has a `targetNamespace` that is different from that of the customer schema, the `<xs:import />` element and therefore import semantics is used.</span></span>  
  
 <span data-ttu-id="a11ef-111">Im Codebeispiel wird das Adressschema in den folgenden Schritten eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a11ef-111">The code example includes the address schema in the following steps.</span></span>  
  
1. <span data-ttu-id="a11ef-112">Fügt das Kundenschema und das Adressschema einem neuen <xref:System.Xml.Schema.XmlSchemaSet>-Objekt hinzu und kompiliert diese anschließend.</span><span class="sxs-lookup"><span data-stu-id="a11ef-112">Adds the customer schema and the address schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles them.</span></span> <span data-ttu-id="a11ef-113">Alle beim Lesen oder Kompilieren der Schemata aufgetretenen Schemavalidierungswarnungen und -fehler werden vom <xref:System.Xml.Schema.ValidationEventHandler>-Delegaten behandelt.</span><span class="sxs-lookup"><span data-stu-id="a11ef-113">Any schema validation warnings and errors encountered reading or compiling the schemas are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2. <span data-ttu-id="a11ef-114">Ruft die kompilierten <xref:System.Xml.Schema.XmlSchema>-Objekte für die Kunden- und Adressschemata aus dem <xref:System.Xml.Schema.XmlSchemaSet> ab, indem die <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>-Eigenschaft durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="a11ef-114">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> objects for both the customer and address schemas from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="a11ef-115">Da die Schemata kompiliert sind, kann auf die Eigenschaften im Post-Schema-Compilation-Infoset (PSCI) zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a11ef-115">Because the schemas are compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3. <span data-ttu-id="a11ef-116">Erstellt ein <xref:System.Xml.Schema.XmlSchemaImport>-Objekt, legt die <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A>-Eigenschaft des Imports auf den Namespace des Adressschemas fest, legt die <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A>-Eigenschaft des Imports auf das <xref:System.Xml.Schema.XmlSchema>-Objekt des Adressschemas fest, und fügt der <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft des Kundenschemas den Import hinzu.</span><span class="sxs-lookup"><span data-stu-id="a11ef-116">Creates an <xref:System.Xml.Schema.XmlSchemaImport> object, sets the <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> property of the import to the namespace of the address schema, sets the <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> property of the import to the <xref:System.Xml.Schema.XmlSchema> object of the address schema, and adds the import to the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span>  
  
4. <span data-ttu-id="a11ef-117">Das geänderte <xref:System.Xml.Schema.XmlSchema>-Objekt des Kundenschemas wird mithilfe der <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A>-Methode und der <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaSet>-Klasse erneut verarbeitet, kompiliert und in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a11ef-117">Reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object of the customer schema using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
5. <span data-ttu-id="a11ef-118">Schließlich werden alle in das Kundenschema importierten Schemata mithilfe der <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft des Kundenschemas rekursiv in die Konsole geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a11ef-118">Finally, recursively writes all of the schemas imported into the customer schema to the console using the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span> <span data-ttu-id="a11ef-119">Die <xref:System.Xml.Schema.XmlSchema.Includes%2A>-Eigenschaft bietet Zugriff auf alle einem Schema hinzugefügten Includes, Importe und Neudefinitionen.</span><span class="sxs-lookup"><span data-stu-id="a11ef-119">The <xref:System.Xml.Schema.XmlSchema.Includes%2A> property provides access to all the includes, imports, or redefines added to a schema.</span></span>  
  
 <span data-ttu-id="a11ef-120">Im Folgenden werden das gesamte Codebeispiel dargestellt und die Kunden- und Adressschemata auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a11ef-120">The following is the complete code example and the customer and address schemas written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
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
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 <span data-ttu-id="a11ef-121">Weitere Informationen zu den Elementen `<xs:import />`, `<xs:include />` und `<xs:redefine />` sowie zu den Klassen <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> und <xref:System.Xml.Schema.XmlSchemaRedefine> finden Sie in den [W3C-XML-Schema-Spezifikationen](https://www.w3.org/XML/Schema) und in der Referenzdokumentation zur <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespaceklasse.</span><span class="sxs-lookup"><span data-stu-id="a11ef-121">For more information about the `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements and the <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, see the [W3C XML Schema](https://www.w3.org/XML/Schema) and the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace class reference documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a11ef-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a11ef-122">See also</span></span>

- [<span data-ttu-id="a11ef-123">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="a11ef-123">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="a11ef-124">Lesen und Schreiben von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-124">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="a11ef-125">Erstellen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-125">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="a11ef-126">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-126">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="a11ef-127">Bearbeiten von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-127">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="a11ef-128">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="a11ef-128">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
