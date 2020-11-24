---
title: Pushbasierte Validierung mit „XmlSchemaValidator“
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 9daf6f416d22cd06932cdaba1276889e319d3d90
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824895"
---
# <a name="xmlschemavalidator-push-based-validation"></a><span data-ttu-id="346cb-102">Pushbasierte Validierung mit „XmlSchemaValidator“</span><span class="sxs-lookup"><span data-stu-id="346cb-102">XmlSchemaValidator Push-Based Validation</span></span>

<span data-ttu-id="346cb-103">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt eine effiziente leistungsstarke Methode zum Validieren von XML-Daten anhand von XML-Schemata in einem Push-Verfahren bereit.</span><span class="sxs-lookup"><span data-stu-id="346cb-103">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides an efficient, high-performance mechanism to validate XML data against XML schemas in a push-based manner.</span></span> <span data-ttu-id="346cb-104">Zum Beispiel ermöglicht Ihnen die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse das direkte Validieren eines XML-Infosets, ohne es als XML-Dokument serialisieren zu müssen, und das anschließende erneute Analysieren des XML-Infosets mithilfe eines validierenden XML-Readers.</span><span class="sxs-lookup"><span data-stu-id="346cb-104">For example, the <xref:System.Xml.Schema.XmlSchemaValidator> class allows you to validate an XML infoset in-place without having to serialize it as an XML document and then reparse the document using a validating XML reader.</span></span>

<span data-ttu-id="346cb-105">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse kann in erweiterten Szenarios verwendet werden, z. B. beim Erstellen von Validierungs-Engines für benutzerdefinierte XML-Datenquellen oder als eine Möglichkeit zum Erstellen eines validierenden XML-Writers.</span><span class="sxs-lookup"><span data-stu-id="346cb-105">The <xref:System.Xml.Schema.XmlSchemaValidator> class can be used in advanced scenarios such as building validation engines over custom XML data sources or as a way to build a validating XML writer.</span></span>

<span data-ttu-id="346cb-106">Im folgenden Beispiel wird mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse die `contosoBooks.xml`-Datei anhand des `contosoBooks.xsd`-Schemas validiert.</span><span class="sxs-lookup"><span data-stu-id="346cb-106">The following is an example of using the <xref:System.Xml.Schema.XmlSchemaValidator> class to validate the `contosoBooks.xml` file against the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="346cb-107">Im Beispiel wird mit der <xref:System.Xml.Serialization.XmlSerializer>-Klasse die `contosoBooks.xml`-Datei deserialisiert, und der Wert der Knoten wird an die Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse übergeben.</span><span class="sxs-lookup"><span data-stu-id="346cb-107">The example uses the <xref:System.Xml.Serialization.XmlSerializer> class to deserialize the `contosoBooks.xml` file and pass the value of the nodes to the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

> [!NOTE]
> <span data-ttu-id="346cb-108">Dieses Beispiel wird in allen Abschnitten dieses Themas verwendet.</span><span class="sxs-lookup"><span data-stu-id="346cb-108">This example is used throughout the sections of this topic.</span></span>

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

<span data-ttu-id="346cb-109">In diesem Beispiel wird die Datei `contosoBooks.xml` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="346cb-109">The example takes the `contosoBooks.xml` file as input.</span></span>

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

<span data-ttu-id="346cb-110">In diesem Beispiel wird auch `contosoBooks.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="346cb-110">The example also takes the `contosoBooks.xsd` as an input.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a><span data-ttu-id="346cb-111">Validieren von XML-Daten mithilfe von "XmlSchemaValidator"</span><span class="sxs-lookup"><span data-stu-id="346cb-111">Validating XML Data using XmlSchemaValidator</span></span>

<span data-ttu-id="346cb-112">Um die Validierung eines XML-Infosets zu starten, müssen Sie zuerst eine neue Instanz der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse mithilfe des <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktors initialisieren.</span><span class="sxs-lookup"><span data-stu-id="346cb-112">To begin validating an XML infoset, you must first initialize a new instance of the <xref:System.Xml.Schema.XmlSchemaValidator> class using the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor.</span></span>

<span data-ttu-id="346cb-113">Der <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor nimmt die Objekte <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> und <xref:System.Xml.XmlNamespaceManager> sowie den <xref:System.Xml.Schema.XmlSchemaValidationFlags>-Wert als Parameter an.</span><span class="sxs-lookup"><span data-stu-id="346cb-113">The <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor takes <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, and <xref:System.Xml.XmlNamespaceManager> objects as parameters as well as a <xref:System.Xml.Schema.XmlSchemaValidationFlags> value as a parameter.</span></span> <span data-ttu-id="346cb-114">Mit dem <xref:System.Xml.XmlNameTable>-Objekt werden bekannte Namespacezeichenfolgen, z. B. der Schemanamespace, der XML-Namespace usw., atomisiert und während der Validierung von einfachem Inhalt an die <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A>-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="346cb-114">The <xref:System.Xml.XmlNameTable> object is used to atomize well-known namespace strings like the schema namespace, the XML namespace, and so on, and is passed to the <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> method while validating simple content.</span></span> <span data-ttu-id="346cb-115">Das <xref:System.Xml.Schema.XmlSchemaSet>-Objekt enthält die XML-Schemata, mit denen die XML-Infosets validiert werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-115">The <xref:System.Xml.Schema.XmlSchemaSet> object contains the XML schemas used to validate the XML infoset.</span></span> <span data-ttu-id="346cb-116">Mit dem <xref:System.Xml.XmlNamespaceManager>-Objekt werden während der Validierung gefundene Namespaces aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="346cb-116">The <xref:System.Xml.XmlNamespaceManager> object is used to resolve namespaces encountered during validation.</span></span> <span data-ttu-id="346cb-117">Mit dem <xref:System.Xml.Schema.XmlSchemaValidationFlags>-Wert werden bestimmte Validierungsfunktionen deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="346cb-117">The <xref:System.Xml.Schema.XmlSchemaValidationFlags> value is used to disable certain features of validation.</span></span>

<span data-ttu-id="346cb-118">Weitere Informationen zum <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-118">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="initializing-validation"></a><span data-ttu-id="346cb-119">Initialisieren der Validierung</span><span class="sxs-lookup"><span data-stu-id="346cb-119">Initializing Validation</span></span>

<span data-ttu-id="346cb-120">Nach dem Erstellen eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts wird mit zwei überladenen <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden der Zustand des <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts initialisiert.</span><span class="sxs-lookup"><span data-stu-id="346cb-120">After an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed, there are two overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods used to initialize the state of the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="346cb-121">Nachfolgend sind die zwei <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden dargestellt.</span><span class="sxs-lookup"><span data-stu-id="346cb-121">The following are the two <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

<span data-ttu-id="346cb-122">Die Standard-<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen Anfangszustand, und die überladene <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen Anfangszustand zur teilweisen Validierung.</span><span class="sxs-lookup"><span data-stu-id="346cb-122">The default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state, and the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="346cb-123">Beide <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methoden können nur unmittelbar nach dem Erstellen eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts oder nach einem Aufruf von <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A> aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-123">Both <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods can only be called immediately after an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed or after a call to <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span></span>

<span data-ttu-id="346cb-124">Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-124">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method, see the example in the introduction.</span></span> <span data-ttu-id="346cb-125">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-125">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="partial-validation"></a><span data-ttu-id="346cb-126">Teilweise Validierung</span><span class="sxs-lookup"><span data-stu-id="346cb-126">Partial Validation</span></span>

<span data-ttu-id="346cb-127">Die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, initialisiert ein <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt mit dessen anfänglichem Zustand zur teilweisen Validierung.</span><span class="sxs-lookup"><span data-stu-id="346cb-127">The <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="346cb-128">Im folgenden Beispiel wird ein <xref:System.Xml.Schema.XmlSchemaObject> mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>-Methode zur teilweisen Validierung initialisiert.</span><span class="sxs-lookup"><span data-stu-id="346cb-128">In the following example, an <xref:System.Xml.Schema.XmlSchemaObject> is initialized for partial validation using the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="346cb-129">Das `orderNumber`-Schemaelement wird durch Auswählen des Schemaelements durch <xref:System.Xml.XmlQualifiedName> in der <xref:System.Xml.Schema.XmlSchemaObjectTable>-Auflistung übergeben, die von der <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A>-Eigenschaft des <xref:System.Xml.Schema.XmlSchemaSet>-Objekts zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="346cb-129">The `orderNumber` schema element is passed by selecting the schema element by <xref:System.Xml.XmlQualifiedName> in the <xref:System.Xml.Schema.XmlSchemaObjectTable> collection returned by the <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> object.</span></span> <span data-ttu-id="346cb-130">Das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt validiert dann dieses bestimmte Element.</span><span class="sxs-lookup"><span data-stu-id="346cb-130">The <xref:System.Xml.Schema.XmlSchemaValidator> object then validates this specific element.</span></span>

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

<span data-ttu-id="346cb-131">In diesem Beispiel wird das folgende XML-Schema als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="346cb-131">The example takes the following XML schema as input.</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

<span data-ttu-id="346cb-132">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-132">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="adding-additional-schemas"></a><span data-ttu-id="346cb-133">Hinzufügen von zusätzlichen Schemata</span><span class="sxs-lookup"><span data-stu-id="346cb-133">Adding Additional Schemas</span></span>

<span data-ttu-id="346cb-134">Mit der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse wird der Gruppe von Schemata, die während der Validierung verwendet werden, ein XML-Schema hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="346cb-134">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method of the <xref:System.Xml.Schema.XmlSchemaValidator> class is used to add an XML schema to the set of schemas used during validation.</span></span> <span data-ttu-id="346cb-135">Mit der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode können die Auswirkungen des Findens eines XML-Inlineschemas in dem XML-Infoset simuliert werden, das validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-135">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method can be used to simulate the effect of encountering an inline XML schema in the XML infoset being validated.</span></span>

> [!NOTE]
> <span data-ttu-id="346cb-136">Der Zielnamespace des <xref:System.Xml.Schema.XmlSchema>-Parameters darf nicht mit dem Namespace eines der Elemente oder Attribute übereinstimmen, die bereits vom <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="346cb-136">The target namespace of the <xref:System.Xml.Schema.XmlSchema> parameter cannot match that of any element or attribute already encountered by the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>
>
> <span data-ttu-id="346cb-137">Wenn der <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType>-Wert nicht als Parameter an den <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>-Konstruktor übergeben wurde, hat die <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="346cb-137">If the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> value was not passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method does nothing.</span></span>

<span data-ttu-id="346cb-138">Das Ergebnis der <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode hängt von dem aktuellen XML-Knotenkontext ab, der validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-138">The result of the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method is dependant on the current XML node context being validated.</span></span> <span data-ttu-id="346cb-139">Weitere Informationen zu Validierungskontexten finden Sie in diesem Thema im Abschnitt „Validierungskontext“.</span><span class="sxs-lookup"><span data-stu-id="346cb-139">For more information about validation contexts, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="346cb-140">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-140">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="validating-elements-attributes-and-content"></a><span data-ttu-id="346cb-141">Validieren von Elementen, Attributen und Inhalt</span><span class="sxs-lookup"><span data-stu-id="346cb-141">Validating Elements, Attributes, and Content</span></span>

<span data-ttu-id="346cb-142">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt verschiedene Methoden zum Validieren von Elementen, Attributen und Inhalt in einem XML-Infoset anhand von XML-Schemata bereit.</span><span class="sxs-lookup"><span data-stu-id="346cb-142">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides several methods used to validate elements, attributes, and content in an XML infoset against XML schemas.</span></span> <span data-ttu-id="346cb-143">In der folgenden Tabelle werden diese Methoden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="346cb-143">The following table describes each of these methods.</span></span>

|<span data-ttu-id="346cb-144">Methode</span><span class="sxs-lookup"><span data-stu-id="346cb-144">Method</span></span>|<span data-ttu-id="346cb-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="346cb-145">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="346cb-146">Validiert den Elementnamen im aktuellen Kontext.</span><span class="sxs-lookup"><span data-stu-id="346cb-146">Validates the element name in the current context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="346cb-147">Validiert das Attribut im aktuellen Elementkontext oder anhand des <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekts, das als Parameter an die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="346cb-147">Validates the attribute in the current element context or against the <xref:System.Xml.Schema.XmlSchemaAttribute> object passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="346cb-148">Überprüft, ob alle erforderlichen Attribute im Elementkontext vorhanden sind, und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt auf das Validieren des untergeordneten Inhalts des Elements vor.</span><span class="sxs-lookup"><span data-stu-id="346cb-148">Verifies whether all the required attributes in the element context are present and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate the child content of the element.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="346cb-149">Validiert, ob Text im aktuellen Elementkontext zulässig ist, und sammelt den Text zum Validieren, ob das aktuelle Element einfachen Inhalt aufweist.</span><span class="sxs-lookup"><span data-stu-id="346cb-149">Validates whether text is allowed in the current element context, and accumulates the text for validation if the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="346cb-150">Validiert, ob Leerraum im aktuellen Elementkontext zulässig ist, und sammelt den Leerraum zum Validieren, ob das aktuelle Element einfachen Inhalt aufweist.</span><span class="sxs-lookup"><span data-stu-id="346cb-150">Validates whether white-space is allowed in the current element context, and accumulates the white-space for validation whether the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="346cb-151">Überprüft, ob der Textinhalt des Elements gemäß des Datentyps für Elemente mit einfachem Inhalt gültig ist und ob der Inhalt des aktuellen Elements für Elemente mit komplexem Inhalt vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="346cb-151">Verifies whether the text content of the element is valid according to its data type for elements with simple content, and verifies whether the content of the current element is complete for elements with complex content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="346cb-152">Überspringt die Validierung des aktuellen Elementinhalts und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt zum Validieren des Inhalts im Kontext des übergeordneten Elements vor.</span><span class="sxs-lookup"><span data-stu-id="346cb-152">Skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="346cb-153">Beendet die Validierung und überprüft Identitätseinschränkungen für das gesamte XML-Dokument, wenn die <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>-Validierungsoption festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="346cb-153">Ends validation and checks identity constraints for the entire XML document if the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> validation option is set.</span></span>|

> [!NOTE]
> <span data-ttu-id="346cb-154">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse verfügt über einen definierten Zustandsübergang, der die Abfolge und das Vorkommen von Aufrufen der Methoden erzwingt, die in der vorherigen Tabelle beschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="346cb-154">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods described in the previous table.</span></span> <span data-ttu-id="346cb-155">Der bestimmte Zustandsübergang der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse wird im Abschnitt "Zustandsübergang von "XmlSchemaValidator"" dieses Themas beschrieben.</span><span class="sxs-lookup"><span data-stu-id="346cb-155">The specific state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class is described in the "XmlSchemaValidator State Transition" section of this topic.</span></span>

<span data-ttu-id="346cb-156">Ein Beispiel für Methoden zum Validieren von Elementen, Attributen und Inhalt eines XML-Infosets finden Sie im Beispiel des vorherigen Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="346cb-156">For an example of the methods used to validate elements, attributes, and content in an XML infoset, see the example in the previous section.</span></span> <span data-ttu-id="346cb-157">Weitere Informationen zu diesen Methoden finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-157">For more information about these methods, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="validating-content-using-an-xmlvaluegetter"></a><span data-ttu-id="346cb-158">Validieren von Inhalt mithilfe von "XmlValueGetter"</span><span class="sxs-lookup"><span data-stu-id="346cb-158">Validating Content Using an XmlValueGetter</span></span>

<span data-ttu-id="346cb-159">Mit <xref:System.Xml.Schema.XmlValueGetter>`delegate` kann der Wert von Attribut-, Text- oder Leerzeichenknoten als CLR-Typ (Common Language Runtime) übergeben werden, der mit dem XSD-Typ (XML Schema Definition Language) des Attribut-, Text- oder Leerzeichenknotens kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="346cb-159">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` can be used to pass the value of attribute, text, or white-space nodes as a Common Language Runtime (CLR) types compatible with the XML Schema Definition Language (XSD) type of the attribute, text, or white-space node.</span></span> <span data-ttu-id="346cb-160"><xref:System.Xml.Schema.XmlValueGetter>`delegate` ist hilfreich, wenn der CLR-Wert eines Attribut-, Text- oder Leerzeichenknotens bereits verfügbar ist, und erspart die Kosten für die Konvertierung in `string` und die anschließende erneute Analyse zur Validierung.</span><span class="sxs-lookup"><span data-stu-id="346cb-160">An <xref:System.Xml.Schema.XmlValueGetter>`delegate` is useful if the CLR value of an attribute, text, or white-space node is already available, and avoids the cost of converting it to a `string` and then reparsing it again for validation.</span></span>

<span data-ttu-id="346cb-161">Die Methoden <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> sind überladen und akzeptieren den Wert der Attribut-, Text- oder Leerraumknoten als `string` oder <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span><span class="sxs-lookup"><span data-stu-id="346cb-161">The <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> methods are overloaded and accept the value of attribute, text, or white-space nodes as a `string` or <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span></span>

<span data-ttu-id="346cb-162">Die folgenden Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren einen <xref:System.Xml.Schema.XmlValueGetter>`delegate` als Parameter.</span><span class="sxs-lookup"><span data-stu-id="346cb-162">The following methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlValueGetter>`delegate` as a parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

<span data-ttu-id="346cb-163">Im Folgenden wird ein Beispiel für <xref:System.Xml.Schema.XmlValueGetter>`delegate` aus dem Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse in der Einleitung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="346cb-163">The following is an example <xref:System.Xml.Schema.XmlValueGetter>`delegate` taken from the <xref:System.Xml.Schema.XmlSchemaValidator> class example in the introduction.</span></span> <span data-ttu-id="346cb-164"><xref:System.Xml.Schema.XmlValueGetter>`delegate` gibt den Wert eines Attributs als <xref:System.DateTime>-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-164">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` returns the value of an attribute as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="346cb-165">Zum Validieren dieses von <xref:System.DateTime> zurückgegebenen <xref:System.Xml.Schema.XmlValueGetter>-Objekts wird es zunächst vom <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt in den ValueType (ValueType ist die Standard-CLR-Zuordnung für den XSD-Typ) des Datentyps des Attributs konvertiert und dann werden Facets des konvertierten Werts überprüft.</span><span class="sxs-lookup"><span data-stu-id="346cb-165">To validate this <xref:System.DateTime> object returned by the <xref:System.Xml.Schema.XmlValueGetter>, the <xref:System.Xml.Schema.XmlSchemaValidator> object first converts it to the ValueType (ValueType is the default CLR mapping for the XSD type) for the data type of the attribute and then checks facets on the converted value.</span></span>

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

<span data-ttu-id="346cb-166">Ein vollständiges Beispiel für <xref:System.Xml.Schema.XmlValueGetter>`delegate` finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-166">For a complete example of the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the example in the introduction.</span></span> <span data-ttu-id="346cb-167">Weitere Informationen zum <xref:System.Xml.Schema.XmlValueGetter>`delegate` finden Sie in der Referenzdokumentation zur <xref:System.Xml.Schema.XmlValueGetter>-Klasse und zur <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-167">For more information about the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the <xref:System.Xml.Schema.XmlValueGetter>, and <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="post-schema-validation-information"></a><span data-ttu-id="346cb-168">Informationen zur Post-Schema-Validation</span><span class="sxs-lookup"><span data-stu-id="346cb-168">Post-Schema-Validation-Information</span></span>

<span data-ttu-id="346cb-169">Die <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse stellt einige der Informationen zur Post-Schema-Validation eines XML-Knotens dar, der von der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-169">The <xref:System.Xml.Schema.XmlSchemaInfo> class represents some of the Post-Schema-Validation-Information of an XML node validated by the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="346cb-170">Verschiedene Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren ein <xref:System.Xml.Schema.XmlSchemaInfo>-Objekt als einen optionalen (`null`) `out`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="346cb-170">Various methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an optional, (`null`) `out` parameter.</span></span>

<span data-ttu-id="346cb-171">Bei einer erfolgreichen Validierung werden Eigenschaften des <xref:System.Xml.Schema.XmlSchemaInfo>-Objekts auf die Ergebnisse der Validierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="346cb-171">Upon successful validation, properties of the <xref:System.Xml.Schema.XmlSchemaInfo> object are set with the results of the validation.</span></span> <span data-ttu-id="346cb-172">Bei der erfolgreichen Validierung eines Attributs mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode werden z. B. die Eigenschaften <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> und <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> des <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A>-Objekts, sofern angegeben, auf die Ergebnisse der Validierung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="346cb-172">For example, upon successful validation of an attribute using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the <xref:System.Xml.Schema.XmlSchemaInfo> object's (if specified) <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A>, and <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> properties are set with the results of the validation.</span></span>

<span data-ttu-id="346cb-173">Die folgenden Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse akzeptieren ein <xref:System.Xml.Schema.XmlSchemaInfo>-Objekt als out-Parameter.</span><span class="sxs-lookup"><span data-stu-id="346cb-173">The following <xref:System.Xml.Schema.XmlSchemaValidator> class methods accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an out parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

<span data-ttu-id="346cb-174">Ein vollständiges Beispiel für die <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-174">For a complete example of the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the example in the introduction.</span></span> <span data-ttu-id="346cb-175">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-175">For more information about the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a><span data-ttu-id="346cb-176">Abrufen von erwarteten Partikeln, Attributen und nicht angegebenen Standardattributen</span><span class="sxs-lookup"><span data-stu-id="346cb-176">Retrieving Expected Particles, Attributes, and Unspecified Default Attributes</span></span>

<span data-ttu-id="346cb-177">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse stellt die Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> zum Abrufen der erwarteten Partikel, Attribute und nicht angegebenen Standardattribute im aktuellen Validierungskontext bereit.</span><span class="sxs-lookup"><span data-stu-id="346cb-177">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> methods to retrieve the expected particles, attributes, and unspecified default attributes in the current validation context.</span></span>

#### <a name="retrieving-expected-particles"></a><span data-ttu-id="346cb-178">Abrufen von erwarteten Partikeln</span><span class="sxs-lookup"><span data-stu-id="346cb-178">Retrieving Expected Particles</span></span>

<span data-ttu-id="346cb-179">Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode gibt ein Array von <xref:System.Xml.Schema.XmlSchemaParticle>-Objekten mit den erwarteten Partikeln im aktuellen Elementkontext zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-179">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaParticle> objects containing the expected particles in the current element context.</span></span> <span data-ttu-id="346cb-180">Die gültigen Partikel, die von der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode zurückgegeben werden können, sind Instanzen der <xref:System.Xml.Schema.XmlSchemaElement>-Klasse und der <xref:System.Xml.Schema.XmlSchemaAny>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-180">The valid particles that can be returned by the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method are instances of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAny> classes.</span></span>

<span data-ttu-id="346cb-181">Wenn der Compositor für das Inhaltsmodell eine `xs:sequence` ist, wird nur der nächste Partikel in der Abfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="346cb-181">When the compositor for the content model is an `xs:sequence`, only the next particle in the sequence is returned.</span></span> <span data-ttu-id="346cb-182">Wenn der Compositor für das Inhaltsmodell `xs:all` oder `xs:choice` ist, werden alle gültigen Partikel zurückgegeben, die im aktuellen Elementkontext folgen können.</span><span class="sxs-lookup"><span data-stu-id="346cb-182">If the compositor for the content model is an `xs:all` or an `xs:choice`, then all valid particles that could follow in the current element context are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="346cb-183">Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode unmittelbar nach dem Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode aufgerufen wird, gibt die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode alle globalen Elemente zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-183">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called immediately after calling the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns all global elements.</span></span>

<span data-ttu-id="346cb-184">Im folgenden XSD-Schema (XML Schema Definition Language) und XML-Dokument entspricht z. B. nach dem Validieren des `book`-Elements das `book`-Element dem aktuellen Elementkontext.</span><span class="sxs-lookup"><span data-stu-id="346cb-184">For example, in the XML Schema Definition Language (XSD) schema and XML document that follow, after validating the `book` element, the `book` element is the current element context.</span></span> <span data-ttu-id="346cb-185">Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode gibt ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaElement>-Objekt zurück, das das `title`-Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="346cb-185">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `title` element.</span></span> <span data-ttu-id="346cb-186">Wenn der Validierungskontext dem `title`-Element entspricht, gibt die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-186">When the validation context is the `title` element, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an empty array.</span></span> <span data-ttu-id="346cb-187">Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode aufgerufen wird, nachdem das `title`-Element validiert wurde und bevor das `description`-Element validiert wurde, gibt sie ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaElement>-Objekt zurück, das das `description`-Element darstellt.</span><span class="sxs-lookup"><span data-stu-id="346cb-187">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `title` element has been validated but before the `description` element has been validated, it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `description` element.</span></span> <span data-ttu-id="346cb-188">Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode aufgerufen wird, nachdem das `description`-Element validiert wurde, gibt sie ein Array mit einem einzelnen <xref:System.Xml.Schema.XmlSchemaAny>-Objekt zurück, das den Platzhalter darstellt.</span><span class="sxs-lookup"><span data-stu-id="346cb-188">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `description` element has been validated then it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaAny> object representing the wildcard.</span></span>

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 <span data-ttu-id="346cb-189">In diesem Beispiel wird der folgende XML-Code als Eingabe verwendet:</span><span class="sxs-lookup"><span data-stu-id="346cb-189">The example takes the following XML as input:</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="346cb-190">In diesem Beispiel wird das folgende XSD-Schema als Eingabe verwendet:</span><span class="sxs-lookup"><span data-stu-id="346cb-190">The example takes the following XSD schema as input:</span></span>

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> <span data-ttu-id="346cb-191">Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-191">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="346cb-192">Weitere Informationen finden Sie in diesem Thema im Abschnitt „Validierungskontext“.</span><span class="sxs-lookup"><span data-stu-id="346cb-192">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="346cb-193">Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-193">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="346cb-194">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-194">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-expected-attributes"></a><span data-ttu-id="346cb-195">Abrufen von erwarteten Attributen</span><span class="sxs-lookup"><span data-stu-id="346cb-195">Retrieving Expected Attributes</span></span>

<span data-ttu-id="346cb-196">Die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode gibt ein Array von <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekten mit den erwarteten Attributen im aktuellen Elementkontext zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-196">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaAttribute> objects containing the expected attributes in the current element context.</span></span>

<span data-ttu-id="346cb-197">Im Beispiel in der Einleitung werden mit der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode alle Attribute des `book`-Elements abgerufen.</span><span class="sxs-lookup"><span data-stu-id="346cb-197">For example, in the example in the introduction, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method is used to retrieve all the attributes of the `book` element.</span></span>

<span data-ttu-id="346cb-198">Wenn Sie die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode unmittelbar nach der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>-Methode aufrufen, werden alle Attribute zurückgegeben, die im XML-Dokument vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="346cb-198">If you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method immediately after the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> method, all the attributes that could appear in the XML document are returned.</span></span> <span data-ttu-id="346cb-199">Wenn Sie jedoch die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode nach einem oder mehreren Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode aufrufen, werden die Attribute zurückgegeben, die bisher noch nicht für das aktuelle Element validiert wurden.</span><span class="sxs-lookup"><span data-stu-id="346cb-199">However, if you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method after one or more calls to the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the attributes that have not yet been validated for the current element are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="346cb-200">Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-200">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="346cb-201">Weitere Informationen finden Sie in diesem Thema im Abschnitt „Validierungskontext“.</span><span class="sxs-lookup"><span data-stu-id="346cb-201">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="346cb-202">Ein Beispiel für die <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-202">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="346cb-203">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-203">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-unspecified-default-attributes"></a><span data-ttu-id="346cb-204">Abrufen von nicht angegebenen Standardattributen</span><span class="sxs-lookup"><span data-stu-id="346cb-204">Retrieving Unspecified Default Attributes</span></span>

<span data-ttu-id="346cb-205">Die <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode füllt die angegebene <xref:System.Collections.ArrayList> mit den <xref:System.Xml.Schema.XmlSchemaAttribute>-Objekten für alle Attribute mit Standardwerten, die noch nicht mithilfe der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode im Elementkontext validiert wurden.</span><span class="sxs-lookup"><span data-stu-id="346cb-205">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method populates the <xref:System.Collections.ArrayList> specified with <xref:System.Xml.Schema.XmlSchemaAttribute> objects for any attributes with default values that have not been previously validated using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method in the element context.</span></span> <span data-ttu-id="346cb-206">Die <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode muss nach einem Aufruf der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>-Methode für alle Attribute im Elementkontext aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-206">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be called after calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method on each attribute in the element context.</span></span> <span data-ttu-id="346cb-207">Mit der <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode muss bestimmt werden, welche Standardattribute in das XML-Dokument eingefügt werden sollen, das validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-207">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be used to determine what default attributes are to be inserted into the XML document being validated.</span></span>

<span data-ttu-id="346cb-208">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>-Methode finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-208">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="handling-schema-validation-events"></a><span data-ttu-id="346cb-209">Behandeln von Schemavalidierungsereignissen</span><span class="sxs-lookup"><span data-stu-id="346cb-209">Handling Schema Validation Events</span></span>

<span data-ttu-id="346cb-210">Schemavalidierungswarnungen und -fehler, die während der Validierung gefunden wurden, werden vom <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>-Ereignis der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse behandelt.</span><span class="sxs-lookup"><span data-stu-id="346cb-210">Schema validation warnings and errors encountered during validation are handled by the <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> event of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

<span data-ttu-id="346cb-211">Schemavalidierungswarnungen weisen einen <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Warning> auf, und Schemavalidierungsfehler weisen einen <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Error> auf.</span><span class="sxs-lookup"><span data-stu-id="346cb-211">Schema validation warnings have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning> and schema validation errors have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="346cb-212">Wenn kein <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> zugewiesen wurde, wird eine <xref:System.Xml.Schema.XmlSchemaValidationException> für alle Schemavalidierungsfehler mit einem <xref:System.Xml.Schema.XmlSeverityType>-Wert von <xref:System.Xml.Schema.XmlSeverityType.Error> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="346cb-212">If no <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> has been assigned, an <xref:System.Xml.Schema.XmlSchemaValidationException> is thrown for all schema validation errors with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="346cb-213">Für Schemavalidierungswarnungen mit einem <xref:System.Xml.Schema.XmlSchemaValidationException>-Wert von <xref:System.Xml.Schema.XmlSeverityType> wird jedoch keine <xref:System.Xml.Schema.XmlSeverityType.Warning> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="346cb-213">However, an <xref:System.Xml.Schema.XmlSchemaValidationException> is not thrown for schema validation warnings with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span></span>

<span data-ttu-id="346cb-214">Das folgende Beispiel für einen <xref:System.Xml.Schema.ValidationEventHandler>, der Schemavalidierungswarnungen und -fehler während der Schemavalidierung empfängt, stammt aus dem Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-214">The following is an example of a <xref:System.Xml.Schema.ValidationEventHandler> that receives schema validation warnings and errors encountered during schema validation taken from the example in the introduction.</span></span>

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

<span data-ttu-id="346cb-215">Ein vollständiges Beispiel von <xref:System.Xml.Schema.ValidationEventHandler> finden Sie im Beispiel in der Einleitung.</span><span class="sxs-lookup"><span data-stu-id="346cb-215">For a complete example of the <xref:System.Xml.Schema.ValidationEventHandler>, see the example in the introduction.</span></span> <span data-ttu-id="346cb-216">Weitere Informationen finden Sie in der Referenzdokumentation der <xref:System.Xml.Schema.XmlSchemaInfo>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="346cb-216">For more information, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

## <a name="xmlschemavalidator-state-transition"></a><span data-ttu-id="346cb-217">Zustandsübergänge von "XmlSchemaValidator"</span><span class="sxs-lookup"><span data-stu-id="346cb-217">XmlSchemaValidator State Transition</span></span>

<span data-ttu-id="346cb-218">Die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse verfügt über einen definierten Zustandsübergang, der die Abfolge und das Vorkommen von Aufrufen der Methoden erzwingt, mit denen Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-218">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods used to validate elements, attributes, and content in an XML infoset.</span></span>

<span data-ttu-id="346cb-219">In der folgenden Tabelle werden die Zustandsübergänge der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse und die Abfolge und das Vorkommen von Methodenaufrufen erläutert, die in den einzelnen Zuständen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="346cb-219">The following table describes the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class, and the sequence and occurrence of method calls that can be made in each state.</span></span>

|<span data-ttu-id="346cb-220">Zustand</span><span class="sxs-lookup"><span data-stu-id="346cb-220">State</span></span>|<span data-ttu-id="346cb-221">Übergang</span><span class="sxs-lookup"><span data-stu-id="346cb-221">Transition</span></span>|
|-----------|----------------|
|<span data-ttu-id="346cb-222">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="346cb-222">Validate</span></span>|<span data-ttu-id="346cb-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span><span class="sxs-lookup"><span data-stu-id="346cb-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span></span>|
|<span data-ttu-id="346cb-224">TopLevel</span><span class="sxs-lookup"><span data-stu-id="346cb-224">TopLevel</span></span>|<span data-ttu-id="346cb-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="346cb-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|
|<span data-ttu-id="346cb-226">Element</span><span class="sxs-lookup"><span data-stu-id="346cb-226">Element</span></span>|<span data-ttu-id="346cb-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span><span class="sxs-lookup"><span data-stu-id="346cb-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span></span> <span data-ttu-id="346cb-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="346cb-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="346cb-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="346cb-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="346cb-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="346cb-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span>|
|<span data-ttu-id="346cb-231">Inhalt</span><span class="sxs-lookup"><span data-stu-id="346cb-231">Content</span></span>|<span data-ttu-id="346cb-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="346cb-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|

> [!NOTE]
> <span data-ttu-id="346cb-233">Von den einzelnen Methoden in der Tabelle oben wird eine <xref:System.InvalidOperationException> ausgelöst, wenn der Aufruf der Methode gemäß des aktuellen Zustands eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts in der falschen Abfolge ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="346cb-233">An <xref:System.InvalidOperationException> is thrown by each of the methods in the table above when the call to the method is made in the incorrect sequence according to the current state of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>

<span data-ttu-id="346cb-234">In der Tabelle der Zustandsübergänge oben werden Satzzeichen verwendet, um die Methoden und andere Zustände zu beschreiben, die für jeden Zustand des Zustandübergangs der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="346cb-234">The state transition table above uses punctuation symbols to describe the methods and other states that can be called for each state of the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="346cb-235">Die verwendeten Symbole entsprechen den Symbolen der XML-Richtlinien für DTD (Document Type Definition).</span><span class="sxs-lookup"><span data-stu-id="346cb-235">The symbols used are the same symbols found in the XML Standards reference for Document Type Definition (DTD).</span></span>

<span data-ttu-id="346cb-236">In der folgenden Tabelle wird beschrieben, welche Auswirkungen die Satzzeichen in der Tabelle der Zustandsübergänge oben auf die Methoden und andere Zustände haben, die für jeden Zustand im Zustandsübergang der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="346cb-236">The following table describes how the punctuation symbols found in the state transition table above affect the methods and other states that can be called for each state in the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

|<span data-ttu-id="346cb-237">Symbol</span><span class="sxs-lookup"><span data-stu-id="346cb-237">Symbol</span></span>|<span data-ttu-id="346cb-238">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="346cb-238">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="346cb-239">&#124;</span><span class="sxs-lookup"><span data-stu-id="346cb-239">&#124;</span></span>|<span data-ttu-id="346cb-240">Entweder die Methode bzw. der Zustand vor oder die Methode bzw. der Zustand nach dem senkrechten Strich, kann aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-240">Either method or state (the one before the bar or the one after it) can be called.</span></span>|
|<span data-ttu-id="346cb-241">?</span><span class="sxs-lookup"><span data-stu-id="346cb-241">?</span></span>|<span data-ttu-id="346cb-242">Die Methode oder der Zustand nach dem Fragezeichen ist optional, es kann jedoch nur ein Aufruf der Methode bzw. des Zustands erfolgen.</span><span class="sxs-lookup"><span data-stu-id="346cb-242">The method or state that precedes the question mark is optional but if it is called it can only be called once.</span></span>|
|\*|<span data-ttu-id="346cb-243">Die Methode bzw. der Zustand nach dem Zeichen \* ist optional und kann mehr als einmal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-243">The method or state that precedes the \* symbol is optional, and can be called more than once.</span></span>|

## <a name="validation-context"></a><span data-ttu-id="346cb-244">Validierungskontext</span><span class="sxs-lookup"><span data-stu-id="346cb-244">Validation Context</span></span>

<span data-ttu-id="346cb-245">Die Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse, mit denen Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden, ändern den Validierungskontext eines <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="346cb-245">The methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset, change the validation context of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="346cb-246">Die <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>-Methode überspringt die Validierung des aktuellen Elementinhalts und bereitet das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt zum Validieren des Inhalts im Kontext des übergeordneten Elements vor. Dies entspricht dem Überspringen der Validierung aller untergeordneten Elemente des aktuellen Elements und dem anschließenden Aufrufen der <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="346cb-246">For example, the <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> method skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context; it is equivalent to skipping validation for all the children of the current element and then calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> method.</span></span>

<span data-ttu-id="346cb-247">Die Ergebnisse der Methoden <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> und <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse hängen vom aktuellen Kontext ab, der validiert wird.</span><span class="sxs-lookup"><span data-stu-id="346cb-247">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span>

<span data-ttu-id="346cb-248">In der folgenden Tabelle werden die Ergebnisse der Aufrufe dieser Methoden nach dem Aufrufen einer der Methoden der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse erläutert, mit der Elemente, Attribute und Inhalt in einem XML-Infoset validiert werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-248">The following table describes the results of calling these methods after calling one of the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset.</span></span>

|<span data-ttu-id="346cb-249">Methode</span><span class="sxs-lookup"><span data-stu-id="346cb-249">Method</span></span>|<span data-ttu-id="346cb-250">GetExpectedParticles</span><span class="sxs-lookup"><span data-stu-id="346cb-250">GetExpectedParticles</span></span>|<span data-ttu-id="346cb-251">GetExpectedAttributes</span><span class="sxs-lookup"><span data-stu-id="346cb-251">GetExpectedAttributes</span></span>|<span data-ttu-id="346cb-252">AddSchema</span><span class="sxs-lookup"><span data-stu-id="346cb-252">AddSchema</span></span>|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|<span data-ttu-id="346cb-253">Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Standardmethode aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein Array mit allen globalen Elementen zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-253">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an array containing all global elements.</span></span><br /><br /> <span data-ttu-id="346cb-254">Wenn die überladene <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, zum Initialisieren der teilweisen Validierung eines Elements aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> nur das Element zurück, mit dem das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="346cb-254">If the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an element, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns only the element to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="346cb-255">Wenn die <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Standardmethode aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-255">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-256">Wenn die Überladung der <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>-Methode, die ein <xref:System.Xml.Schema.XmlSchemaObject> als Parameter annimmt, zum Initialisieren der teilweisen Validierung eines Attributs aufgerufen wird, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> nur das Attribut zurück, mit dem das <xref:System.Xml.Schema.XmlSchemaValidator>-Objekt initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="346cb-256">If the overload of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns only the attribute to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="346cb-257">Fügt dem <xref:System.Xml.Schema.XmlSchemaSet> des <xref:System.Xml.Schema.XmlSchemaValidator>-Objekts das Schema hinzu, wenn es keine Vorverarbeitungsfehler aufweist.</span><span class="sxs-lookup"><span data-stu-id="346cb-257">Adds the schema to the <xref:System.Xml.Schema.XmlSchemaSet> of the <xref:System.Xml.Schema.XmlSchemaValidator> object if it has no preprocessing errors.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="346cb-258">Wenn das Kontextelement gültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die als untergeordnete Elemente des Kontextelements erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-258">If the context element is valid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as children of the context element.</span></span><br /><br /> <span data-ttu-id="346cb-259">Wenn das Kontextelement ungültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-259">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span>|<span data-ttu-id="346cb-260">Wenn das Kontextelement gültig ist und <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> bisher nicht aufgerufen wurde, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine Liste aller im Kontextelement definierten Attribute zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-260">If the context element is valid, and if no call to <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> has been previously made, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of all the attributes defined on the context element.</span></span><br /><br /> <span data-ttu-id="346cb-261">Wenn einige Attribute bereits validiert wurden, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine Liste der noch zu validierenden Attribute zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-261">If some attributes have already been validated, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the remaining attributes to be validated.</span></span><br /><br /> <span data-ttu-id="346cb-262">Wenn das Kontextelement ungültig ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-262">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="346cb-263">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-263">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="346cb-264">Wenn sich das Kontextattribut auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-264">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-265">Andernfalls gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-265">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="346cb-266">Wenn sich das Kontextattribut auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-266">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-267">Andernfalls gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> die Liste der noch zu validierenden Attribute zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-267">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the list of remaining attributes to be validated.</span></span>|<span data-ttu-id="346cb-268">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-268">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<span data-ttu-id="346cb-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="346cb-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt eine Liste der erforderlichen und optionalen Attribute zurück, die noch für das Kontextelement validiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="346cb-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the required and optional attributes that are yet to be validated for the context element.</span></span>|<span data-ttu-id="346cb-271">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-271">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="346cb-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die als das erste untergeordnete Element des Kontextelements erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="346cb-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="346cb-274">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-274">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="346cb-275">Wenn contentType<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> des Kontextelements Mixed ist, gibt  die Abfolge der Elemente zurück, die auf der nächsten Position erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="346cb-275">If the context element's contentType is Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position.</span></span><br /><br /> <span data-ttu-id="346cb-276">Wenn contentType des Kontextelements TextOnly oder Empty ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-276">If the context element's contentType is TextOnly or Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-277">Wenn contentType des Kontextelements ElementOnly ist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> die Abfolge der Elemente zurück, die auf der nächsten Position erwartet werden. Es ist jedoch bereits ein Validierungsfehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="346cb-277">If the context element's contentType is ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position but a validation error has already occurred.</span></span>|<span data-ttu-id="346cb-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt die Liste der nicht validierten Attribute des Kontextelements zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span>|<span data-ttu-id="346cb-279">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-279">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="346cb-280">Wenn sich der Kontextleerraum auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-280">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-281">Andernfalls entspricht das Verhalten der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>-Methode dem von <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="346cb-281">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="346cb-282">Wenn sich der Kontextleerraum auf der obersten Ebene befindet, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-282">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="346cb-283">Andernfalls entspricht das Verhalten der <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>-Methode dem von <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="346cb-283">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="346cb-284">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-284">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="346cb-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> gibt die Abfolge der Elemente zurück, die nach dem Kontextelement erwartet werden (möglicherweise nebengeordnete Elemente).</span><span class="sxs-lookup"><span data-stu-id="346cb-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected after the context element (possible siblings).</span></span>|<span data-ttu-id="346cb-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> gibt die Liste der nicht validierten Attribute des Kontextelements zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span><br /><br /> <span data-ttu-id="346cb-287">Wenn das Kontextelement kein übergeordnetes Element aufweist, gibt <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> eine leere Liste zurück. (Das Kontextelement ist das übergeordnete Element des aktuellen Elements, für das <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> aufgerufen wurde.)</span><span class="sxs-lookup"><span data-stu-id="346cb-287">If the context element has no parent then <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty list (the context element is the parent of the current element on which <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> was called).</span></span>|<span data-ttu-id="346cb-288">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-288">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="346cb-289">Wie in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="346cb-289">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="346cb-290">Wie in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="346cb-290">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="346cb-291">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-291">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="346cb-292">Gibt ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-292">Returns an empty array.</span></span>|<span data-ttu-id="346cb-293">Gibt ein leeres Array zurück.</span><span class="sxs-lookup"><span data-stu-id="346cb-293">Returns an empty array.</span></span>|<span data-ttu-id="346cb-294">Siehe oben.</span><span class="sxs-lookup"><span data-stu-id="346cb-294">Same as above.</span></span>|

> [!NOTE]
> <span data-ttu-id="346cb-295">Die von den verschiedenen Eigenschaften der <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse zurückgegebenen Werte werden nicht durch das Aufrufen einer der Methoden in der oben stehenden Tabelle verändert.</span><span class="sxs-lookup"><span data-stu-id="346cb-295">The values returned by the various properties of the <xref:System.Xml.Schema.XmlSchemaValidator> class are not altered by calling any of the methods in the above table.</span></span>

## <a name="see-also"></a><span data-ttu-id="346cb-296">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="346cb-296">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator>
