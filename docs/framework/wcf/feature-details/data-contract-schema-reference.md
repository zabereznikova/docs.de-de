---
title: Datenvertrags-Schemareferenz
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], schema reference
ms.assetid: 9ebb0ebe-8166-4c93-980a-7c8f1f38f7c0
ms.openlocfilehash: 04d1f753e5788460404942a21a29e1612f674e90
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593567"
---
# <a name="data-contract-schema-reference"></a><span data-ttu-id="ac174-102">Datenvertrags-Schemareferenz</span><span class="sxs-lookup"><span data-stu-id="ac174-102">Data Contract Schema Reference</span></span>

<span data-ttu-id="ac174-103">In diesem Thema wird die von <xref:System.Runtime.Serialization.DataContractSerializer> zur Beschreibung der Common Language Runtime (CLR)-Typen für die XML-Serialisierung verwendete Teilmenge des XML-Schemas (XSD) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac174-103">This topic describes the subset of the XML Schema (XSD) used by <xref:System.Runtime.Serialization.DataContractSerializer> to describe common language runtime (CLR) types for XML serialization.</span></span>

## <a name="datacontractserializer-mappings"></a><span data-ttu-id="ac174-104">DataContractSerializer-Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="ac174-104">DataContractSerializer Mappings</span></span>

<span data-ttu-id="ac174-105">Der ordnet `DataContractSerializer` CLR-Typen XSD zu, wenn Metadaten von einem Windows Communication Foundation (WCF)-Dienst mithilfe eines Metadatenendpunkts oder des [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-105">The `DataContractSerializer` maps CLR types to XSD when metadata is exported from a Windows Communication Foundation (WCF) service using a metadata endpoint or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="ac174-106">Weitere Informationen finden Sie unter [Data Contract Serializer](data-contract-serializer.md).</span><span class="sxs-lookup"><span data-stu-id="ac174-106">For more information, see [Data Contract Serializer](data-contract-serializer.md).</span></span>

<span data-ttu-id="ac174-107">Der `DataContractSerializer` ordnet XSD auch dann CLR-Typen zu, wenn Svcutil.exe für den Zugriff auf WSDL- (Web Services Description Language) oder XSD-Dokumente und für die Generierung von Vertragsdateien für Dienste oder Clients verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ac174-107">The `DataContractSerializer` also maps XSD to CLR types when Svcutil.exe is used to access Web Services Description Language (WSDL) or XSD documents and generate data contracts for services or clients.</span></span>

<span data-ttu-id="ac174-108">Nur XML-Schemainstanzen, die den in diesem Dokument beschriebenen Anforderungen entsprechen, können mit `DataContractSerializer`CLR-Typen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-108">Only XML Schema instances that conform to requirements stated in this document can be mapped to CLR types using `DataContractSerializer`.</span></span>

### <a name="support-levels"></a><span data-ttu-id="ac174-109">Unterstützungsebenen</span><span class="sxs-lookup"><span data-stu-id="ac174-109">Support Levels</span></span>

<span data-ttu-id="ac174-110">Der `DataContractSerializer` stellt die folgenden Unterstützungsebenen für eine gegebene XML-Schemafunktion bereit:</span><span class="sxs-lookup"><span data-stu-id="ac174-110">The `DataContractSerializer` provides the following levels of support for a given XML Schema feature:</span></span>

- <span data-ttu-id="ac174-111">**Unterstützt**.</span><span class="sxs-lookup"><span data-stu-id="ac174-111">**Supported**.</span></span> <span data-ttu-id="ac174-112">Es gibt eine explizite Zuordnung dieser Funktion zu CLR-Typen oder -Attributen (oder beiden) mit `DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="ac174-112">There is explicit mapping from this feature to CLR types or attributes (or both) using `DataContractSerializer`.</span></span>

- <span data-ttu-id="ac174-113">Wird **ignoriert**.</span><span class="sxs-lookup"><span data-stu-id="ac174-113">**Ignored**.</span></span> <span data-ttu-id="ac174-114">Die Funktion ist in vom `DataContractSerializer`importierten Schemas zugelassen, hat aber keine Auswirkungen auf die Codegenerierung.</span><span class="sxs-lookup"><span data-stu-id="ac174-114">The feature is allowed in schemas imported by the `DataContractSerializer`, but has no effect on code generation.</span></span>

- <span data-ttu-id="ac174-115">**Forbidden**Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-115">**Forbidden**.</span></span> <span data-ttu-id="ac174-116">Der `DataContractSerializer` unterstützt nicht den Import eines Schemas, das diese Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac174-116">The `DataContractSerializer` does not support importing a schema using the feature.</span></span> <span data-ttu-id="ac174-117">Svcutil.exe verwendet beispielsweise wieder den <xref:System.Xml.Serialization.XmlSerializer> , wenn auf ein WSDL mit einem Schema zugegriffen wird, das eine solche Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac174-117">For example, Svcutil.exe, when accessing a WSDL with a schema that uses such a feature, falls back to using the <xref:System.Xml.Serialization.XmlSerializer> instead.</span></span> <span data-ttu-id="ac174-118">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ac174-118">This is by default.</span></span>

## <a name="general-information"></a><span data-ttu-id="ac174-119">Allgemeine Informationen</span><span class="sxs-lookup"><span data-stu-id="ac174-119">General Information</span></span>

- <span data-ttu-id="ac174-120">Der Schemanamespace wird unter [XML-Schema](https://www.w3.org/2001/XMLSchema)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ac174-120">The schema namespace is described at [XML Schema](https://www.w3.org/2001/XMLSchema).</span></span> <span data-ttu-id="ac174-121">In diesem Dokument wird das Präfix "xs" verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac174-121">The prefix "xs" is used in this document.</span></span>

- <span data-ttu-id="ac174-122">Alle Attribute mit einem Nicht-Schema-Namespace werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-122">Any attributes with a non-schema namespace are ignored.</span></span>

- <span data-ttu-id="ac174-123">Alle Anmerkungen (außer den in diesem Dokument beschriebenen) werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-123">Any annotations (except for those described in this document) are ignored.</span></span>

### <a name="xsschema-attributes"></a><span data-ttu-id="ac174-124">\<xs:schema>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-124">\<xs:schema>: attributes</span></span>

|<span data-ttu-id="ac174-125">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-125">Attribute</span></span>|<span data-ttu-id="ac174-126">DataContract</span><span class="sxs-lookup"><span data-stu-id="ac174-126">DataContract</span></span>|
|---------------|------------------|
|`attributeFormDefault`|<span data-ttu-id="ac174-127">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-127">Ignored.</span></span>|
|`blockDefault`|<span data-ttu-id="ac174-128">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-128">Ignored.</span></span>|
|`elementFormDefault`|<span data-ttu-id="ac174-129">Muss qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-129">Must be qualified.</span></span> <span data-ttu-id="ac174-130">Damit ein Schema vom `DataContractSerializer`unterstützt wird, müssen alle Elemente qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-130">All elements must be qualified for a schema to be supported by `DataContractSerializer`.</span></span> <span data-ttu-id="ac174-131">Dies kann erreicht werden, indem entweder xs:schema/@elementFormDefault auf "qualified" festgelegt oder xs:element/@form auf "qualified" für jede einzelne Element Deklaration festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="ac174-131">This can be accomplished by either setting xs:schema/@elementFormDefault to "qualified" or by setting xs:element/@form to "qualified" on each individual element declaration.</span></span>|
|`finalDefault`|<span data-ttu-id="ac174-132">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-132">Ignored.</span></span>|
|`Id`|<span data-ttu-id="ac174-133">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-133">Ignored.</span></span>|
|`targetNamespace`|<span data-ttu-id="ac174-134">Unterstützt und wird dem Datenvertragsnamespace zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-134">Supported and mapped to the data contract namespace.</span></span> <span data-ttu-id="ac174-135">Wenn dieses Attribut nicht angegeben ist, wird ein leerer Namespace verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac174-135">If this attribute is not specified, the blank namespace is used.</span></span> <span data-ttu-id="ac174-136">Kann nicht der reservierte Namespace sein `http://schemas.microsoft.com/2003/10/Serialization/` .</span><span class="sxs-lookup"><span data-stu-id="ac174-136">Cannot be the reserved namespace `http://schemas.microsoft.com/2003/10/Serialization/`.</span></span>|
|`version`|<span data-ttu-id="ac174-137">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-137">Ignored.</span></span>|

### <a name="xsschema-contents"></a><span data-ttu-id="ac174-138">\<xs:schema>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-138">\<xs:schema>: contents</span></span>

|<span data-ttu-id="ac174-139">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-139">Contents</span></span>|<span data-ttu-id="ac174-140">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-140">Schema</span></span>|
|--------------|------------|
|`include`|<span data-ttu-id="ac174-141">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-141">Supported.</span></span> <span data-ttu-id="ac174-142">`DataContractSerializer` unterstützt xs:include und xs:import.</span><span class="sxs-lookup"><span data-stu-id="ac174-142">`DataContractSerializer` supports xs:include and xs:import.</span></span> <span data-ttu-id="ac174-143">Svcutil.exe schränkt jedoch darauf folgende `xs:include/@schemaLocation` - und `xs:import/@location` -Verweise ein, wenn Metadaten aus einer lokalen Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-143">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="ac174-144">Die Liste der Schemadateien muss in diesem Fall über einen Out-of-Band-Mechanismus und nicht mittels `include` übergeben werden. Mit `include`angegebene Schemadokumente werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-144">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`redefine`|<span data-ttu-id="ac174-145">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-145">Forbidden.</span></span> <span data-ttu-id="ac174-146">Die Verwendung von `xs:redefine` durch `DataContractSerializer` ist aus Sicherheitsgründen unzulässig: `x:redefine` erfordert, dass `schemaLocation` befolgt wird.</span><span class="sxs-lookup"><span data-stu-id="ac174-146">The use of `xs:redefine` is forbidden by `DataContractSerializer` for security reasons: `x:redefine` requires `schemaLocation` to be followed.</span></span> <span data-ttu-id="ac174-147">Unter bestimmten Umständen schränkt Svcutil.exe mit DataContract die Verwendung von `schemaLocation`ein.</span><span class="sxs-lookup"><span data-stu-id="ac174-147">In certain circumstances, Svcutil.exe using DataContract restricts use of `schemaLocation`.</span></span>|
|`import`|<span data-ttu-id="ac174-148">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-148">Supported.</span></span> <span data-ttu-id="ac174-149">`DataContractSerializer` unterstützt `xs:include` und `xs:import`.</span><span class="sxs-lookup"><span data-stu-id="ac174-149">`DataContractSerializer` supports `xs:include` and `xs:import`.</span></span> <span data-ttu-id="ac174-150">Svcutil.exe schränkt jedoch darauf folgende `xs:include/@schemaLocation` - und `xs:import/@location` -Verweise ein, wenn Metadaten aus einer lokalen Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-150">However, Svcutil.exe restricts following `xs:include/@schemaLocation` and `xs:import/@location` references when metadata is loaded from a local file.</span></span> <span data-ttu-id="ac174-151">Die Liste der Schemadateien muss in diesem Fall über einen Out-of-Band-Mechanismus und nicht mittels `include` übergeben werden. Mit `include`angegebene Schemadokumente werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-151">The list of schema files must be passed through an out-of-band mechanism and not through `include` in this case; `include`d schema documents are ignored.</span></span>|
|`simpleType`|<span data-ttu-id="ac174-152">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-152">Supported.</span></span> <span data-ttu-id="ac174-153">Siehe den Abschnitt `xs:simpleType` .</span><span class="sxs-lookup"><span data-stu-id="ac174-153">See the `xs:simpleType` section.</span></span>|
|`complexType`|<span data-ttu-id="ac174-154">Unterstützt, wird Datenverträgen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-154">Supported, maps to data contracts.</span></span> <span data-ttu-id="ac174-155">Siehe den Abschnitt `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="ac174-155">See the `xs:complexType` section.</span></span>|
|`group`|<span data-ttu-id="ac174-156">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-156">Ignored.</span></span> <span data-ttu-id="ac174-157">`DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="ac174-157">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="ac174-158">Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-158">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`attributeGroup`|<span data-ttu-id="ac174-159">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-159">Ignored.</span></span> <span data-ttu-id="ac174-160">`DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="ac174-160">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="ac174-161">Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-161">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`element`|<span data-ttu-id="ac174-162">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-162">Supported.</span></span> <span data-ttu-id="ac174-163">Siehe Globale Elementdeklaration (GED).</span><span class="sxs-lookup"><span data-stu-id="ac174-163">See Global Element Declaration (GED).</span></span>|
|`attribute`|<span data-ttu-id="ac174-164">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-164">Ignored.</span></span> <span data-ttu-id="ac174-165">`DataContractSerializer` bietet keine Unterstützung für `xs:group`, `xs:attributeGroup`und `xs:attribute`.</span><span class="sxs-lookup"><span data-stu-id="ac174-165">`DataContractSerializer` does not support use of `xs:group`, `xs:attributeGroup`, and `xs:attribute`.</span></span> <span data-ttu-id="ac174-166">Diese Deklarationen werden als untergeordnete Elemente von `xs:schema`ignoriert; auf sie kann jedoch nicht innerhalb von `complexType` oder anderer unterstützter Konstrukte verwiesen werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-166">These declarations are ignored as children of `xs:schema`, but cannot be referenced from within `complexType` or other supported constructs.</span></span>|
|`notation`|<span data-ttu-id="ac174-167">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-167">Ignored.</span></span>|

## <a name="complex-types--xscomplextype"></a><span data-ttu-id="ac174-168">Komplexe Typen –\<xs:complexType></span><span class="sxs-lookup"><span data-stu-id="ac174-168">Complex Types – \<xs:complexType></span></span>

### <a name="general-information"></a><span data-ttu-id="ac174-169">Allgemeine Informationen</span><span class="sxs-lookup"><span data-stu-id="ac174-169">General Information</span></span>

<span data-ttu-id="ac174-170">Jeder komplexe Typ wird \<xs:complexType> einem Datenvertrag zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-170">Each complex type \<xs:complexType> maps to a data contract.</span></span>

### <a name="xscomplextype-attributes"></a><span data-ttu-id="ac174-171">\<xs:complexType>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-171">\<xs:complexType>: attributes</span></span>

|<span data-ttu-id="ac174-172">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-172">Attribute</span></span>|<span data-ttu-id="ac174-173">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-173">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="ac174-174">Muss den Wert false aufweisen (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="ac174-174">Must be false (default).</span></span>|
|`block`|<span data-ttu-id="ac174-175">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-175">Forbidden.</span></span>|
|`final`|<span data-ttu-id="ac174-176">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-176">Ignored.</span></span>|
|`id`|<span data-ttu-id="ac174-177">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-177">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="ac174-178">Muss den Wert false aufweisen (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="ac174-178">Must be false (default).</span></span>|
|`name`|<span data-ttu-id="ac174-179">Unterstützt. Wird dem Namen des Datenvertrags zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-179">Supported and mapped to the data contract name.</span></span> <span data-ttu-id="ac174-180">Wenn der Name Punkte enthält, wird versucht, den Typ einem inneren Typ zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="ac174-180">If there are periods in the name, an attempt is made to map the type to an inner type.</span></span> <span data-ttu-id="ac174-181">Beispielsweise wird ein komplexer Typ namens `A.B` einem Datenvertragstyp zugeordnet, der ein innerer Typ mit dem Datenvertragsnamen `A`ist. Dies geschieht jedoch nur dann, wenn ein solcher Datenvertragstyp vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ac174-181">For example, a complex type named `A.B` maps to a data contract type that is an inner type of a type with the data contract name `A`, but only if such a data contract type exists.</span></span> <span data-ttu-id="ac174-182">Es ist mehr als eine Verschachtelungsebene möglich: `A.B.C` z.&#160;B. kann ein innerer Typ sein, jedoch nur dann, wenn sowohl `A` als auch `A.B` vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ac174-182">More than one level of nesting is possible: for example, `A.B.C` can be an inner type, but only if `A` and `A.B` both exist.</span></span>|

### <a name="xscomplextype-contents"></a><span data-ttu-id="ac174-183">\<xs:complexType>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-183">\<xs:complexType>: contents</span></span>

|<span data-ttu-id="ac174-184">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-184">Contents</span></span>|<span data-ttu-id="ac174-185">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-185">Schema</span></span>|
|--------------|------------|
|`simpleContent`|<span data-ttu-id="ac174-186">Erweiterungen sind unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-186">Extensions are forbidden.</span></span><br /><br /> <span data-ttu-id="ac174-187">Einschränkung wird nur von `anySimpleType`zugelassen.</span><span class="sxs-lookup"><span data-stu-id="ac174-187">Restriction is allowed only from `anySimpleType`.</span></span>|
|`complexContent`|<span data-ttu-id="ac174-188">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-188">Supported.</span></span> <span data-ttu-id="ac174-189">Siehe "Vererbung".</span><span class="sxs-lookup"><span data-stu-id="ac174-189">See "Inheritance".</span></span>|
|`group`|<span data-ttu-id="ac174-190">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-190">Forbidden.</span></span>|
|`all`|<span data-ttu-id="ac174-191">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-191">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="ac174-192">Verboten</span><span class="sxs-lookup"><span data-stu-id="ac174-192">Forbidden</span></span>|
|`sequence`|<span data-ttu-id="ac174-193">Unterstützt, wird Datenmembern eines Datenvertrags zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-193">Supported, maps to data members of a data contract.</span></span>|
|`attribute`|<span data-ttu-id="ac174-194">Unzulässig, auch wenn use="prohibited" (mit einer Ausnahme).</span><span class="sxs-lookup"><span data-stu-id="ac174-194">Forbidden, even if use="prohibited" (with one exception).</span></span> <span data-ttu-id="ac174-195">Nur optionale Attribute aus dem Standardserialisierungsschema-Namespace werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-195">Only optional attributes from the Standard Serialization Schema namespace are supported.</span></span> <span data-ttu-id="ac174-196">Sie werden Datenmembern im Datenvertragsprogrammiermodell nicht zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-196">They do not map to data members in the data contract programming model.</span></span> <span data-ttu-id="ac174-197">Aktuell hat nur ein solches Attribut Bedeutung, es wird im Abschnitt ISerializable erläutert.</span><span class="sxs-lookup"><span data-stu-id="ac174-197">Currently, only one such attribute has meaning and is discussed in the ISerializable section.</span></span> <span data-ttu-id="ac174-198">Alle anderen werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-198">All others are ignored.</span></span>|
|`attributeGroup`|<span data-ttu-id="ac174-199">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-199">Forbidden.</span></span> <span data-ttu-id="ac174-200">In der WCF v1-Version `DataContractSerializer` ignoriert das vorhanden sein von in `attributeGroup` `xs:complexType` .</span><span class="sxs-lookup"><span data-stu-id="ac174-200">In the WCF v1 release, `DataContractSerializer` ignores the presence of `attributeGroup` inside `xs:complexType`.</span></span>|
|`anyAttribute`|<span data-ttu-id="ac174-201">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-201">Forbidden.</span></span>|
|<span data-ttu-id="ac174-202">(leer)</span><span class="sxs-lookup"><span data-stu-id="ac174-202">(empty)</span></span>|<span data-ttu-id="ac174-203">Wird einem Datenvertrag ohne Datenmember zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-203">Maps to a data contract with no data members.</span></span>|

### <a name="xssequence-in-a-complex-type-attributes"></a><span data-ttu-id="ac174-204">\<xs:sequence>in einem komplexen Typ: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-204">\<xs:sequence> in a complex type: attributes</span></span>

|<span data-ttu-id="ac174-205">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-205">Attribute</span></span>|<span data-ttu-id="ac174-206">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-206">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="ac174-207">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-207">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="ac174-208">Muss 1 (Standard) sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-208">Must be 1 (default).</span></span>|
|`minOccurs`|<span data-ttu-id="ac174-209">Muss 1 (Standard) sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-209">Must be 1 (default).</span></span>|

### <a name="xssequence-in-a-complex-type-contents"></a><span data-ttu-id="ac174-210">\<xs:sequence>in einem komplexen Typ: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-210">\<xs:sequence> in a complex type: contents</span></span>

|<span data-ttu-id="ac174-211">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-211">Contents</span></span>|<span data-ttu-id="ac174-212">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-212">Schema</span></span>|
|--------------|------------|
|`element`|<span data-ttu-id="ac174-213">Jede Instanz wird einem Datenmember zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-213">Each instance maps to a data member.</span></span>|
|`group`|<span data-ttu-id="ac174-214">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-214">Forbidden.</span></span>|
|`choice`|<span data-ttu-id="ac174-215">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-215">Forbidden.</span></span>|
|`sequence`|<span data-ttu-id="ac174-216">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-216">Forbidden.</span></span>|
|`any`|<span data-ttu-id="ac174-217">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-217">Forbidden.</span></span>|
|<span data-ttu-id="ac174-218">(leer)</span><span class="sxs-lookup"><span data-stu-id="ac174-218">(empty)</span></span>|<span data-ttu-id="ac174-219">Wird einem Datenvertrag ohne Datenmember zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-219">Maps to a data contract with no data members.</span></span>|

## <a name="elements--xselement"></a><span data-ttu-id="ac174-220">Aspekte\<xs:element></span><span class="sxs-lookup"><span data-stu-id="ac174-220">Elements – \<xs:element></span></span>

### <a name="general-information"></a><span data-ttu-id="ac174-221">Allgemeine Informationen</span><span class="sxs-lookup"><span data-stu-id="ac174-221">General Information</span></span>

<span data-ttu-id="ac174-222">`<xs:element>` kann in den folgenden Kontexten auftreten:</span><span class="sxs-lookup"><span data-stu-id="ac174-222">`<xs:element>` can occur in the following contexts:</span></span>

- <span data-ttu-id="ac174-223">Es kann innerhalb eines `<xs:sequence>`-Elements auftreten, das einen Datenmember eines regulären Datenvertrags (keines Auflistungsdatenvertrags) beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ac174-223">It can occur within an `<xs:sequence>`, which describes a data member of a regular (non-collection) data contract.</span></span> <span data-ttu-id="ac174-224">In diesem Fall muss das `maxOccurs` -Attribut 1 sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-224">In this case, the `maxOccurs` attribute must be 1.</span></span> <span data-ttu-id="ac174-225">(Der Wert 0 ist nicht zulässig.)</span><span class="sxs-lookup"><span data-stu-id="ac174-225">(A value of 0 is not allowed).</span></span>

- <span data-ttu-id="ac174-226">Es kann innerhalb eines `<xs:sequence>`-Elements auftreten, das einen Datenmember eines Auflistungsdatenvertrags beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ac174-226">It can occur within an `<xs:sequence>`, which describes a data member of a collection data contract.</span></span> <span data-ttu-id="ac174-227">In diesem Fall muss der Wert des `maxOccurs` -Attributs größer&#160;1 oder "unbounded" sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-227">In this case, the `maxOccurs` attribute must be greater than 1 or "unbounded".</span></span>

- <span data-ttu-id="ac174-228">Es kann innerhalb eines `<xs:schema>` -Elements als eine globale Elementdeklaration (GED) auftreten.</span><span class="sxs-lookup"><span data-stu-id="ac174-228">It can occur within an `<xs:schema>` as a Global Element Declaration (GED).</span></span>

### <a name="xselement-with-maxoccurs1-within-an-xssequence-data-members"></a><span data-ttu-id="ac174-229">\<xs:element>with maxvorkommen = 1 innerhalb eines- \<xs:sequence> Datentyps (Datenmember)</span><span class="sxs-lookup"><span data-stu-id="ac174-229">\<xs:element> with maxOccurs=1 within an \<xs:sequence> (Data Members)</span></span>

|<span data-ttu-id="ac174-230">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-230">Attribute</span></span>|<span data-ttu-id="ac174-231">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-231">Schema</span></span>|
|---------------|------------|
|`ref`|<span data-ttu-id="ac174-232">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-232">Forbidden.</span></span>|
|`name`|<span data-ttu-id="ac174-233">Unterstützt, wird dem Datenmembernamen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-233">Supported, maps to the data member name.</span></span>|
|`type`|<span data-ttu-id="ac174-234">Unterstützt, wird dem Datenmembertyp zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-234">Supported, maps to the data member type.</span></span> <span data-ttu-id="ac174-235">Weitere Informationen finden Sie unter Zuordnung von Typen zu primitivem Typen.</span><span class="sxs-lookup"><span data-stu-id="ac174-235">For more information, see Type/primitive mapping.</span></span> <span data-ttu-id="ac174-236">Wenn nicht angegeben (und wenn das Element keinen anonymen Typ enthält), wird `xs:anyType` angenommen.</span><span class="sxs-lookup"><span data-stu-id="ac174-236">If not specified (and the element does not contain an anonymous type), `xs:anyType` is assumed.</span></span>|
|`block`|<span data-ttu-id="ac174-237">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-237">Ignored.</span></span>|
|`default`|<span data-ttu-id="ac174-238">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-238">Forbidden.</span></span>|
|`fixed`|<span data-ttu-id="ac174-239">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-239">Forbidden.</span></span>|
|`form`|<span data-ttu-id="ac174-240">Muss qualifiziert sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-240">Must be qualified.</span></span> <span data-ttu-id="ac174-241">Dieses Attribut kann über `elementFormDefault` auf `xs:schema`festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ac174-241">This attribute can be set through `elementFormDefault` on `xs:schema`.</span></span>|
|`id`|<span data-ttu-id="ac174-242">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-242">Ignored.</span></span>|
|`maxOccurs`|<span data-ttu-id="ac174-243">1</span><span class="sxs-lookup"><span data-stu-id="ac174-243">1</span></span>|
|`minOccurs`|<span data-ttu-id="ac174-244">Wird der <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> -Eigenschaft eines Datenmembers zugeordnet (`IsRequired` hat den Wert true, wenn `minOccurs` &#160;1 ist).</span><span class="sxs-lookup"><span data-stu-id="ac174-244">Maps to the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of a data member (`IsRequired` is true when `minOccurs` is 1).</span></span>|
|`nillable`|<span data-ttu-id="ac174-245">Beeinflusst die Typzuordnung.</span><span class="sxs-lookup"><span data-stu-id="ac174-245">Affects type mapping.</span></span> <span data-ttu-id="ac174-246">Siehe Zuordnung von Typen zu primitivem Typen.</span><span class="sxs-lookup"><span data-stu-id="ac174-246">See Type/primitive mapping.</span></span>|

### <a name="xselement-with-maxoccurs1-within-an-xssequence-collections"></a><span data-ttu-id="ac174-247">\<xs:element>with maxvorkommen>1 innerhalb einer (Auflistungen \<xs:sequence> )</span><span class="sxs-lookup"><span data-stu-id="ac174-247">\<xs:element> with maxOccurs>1 within an \<xs:sequence> (Collections)</span></span>

- <span data-ttu-id="ac174-248">Wird einem <xref:System.Runtime.Serialization.CollectionDataContractAttribute>zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-248">Maps to a <xref:System.Runtime.Serialization.CollectionDataContractAttribute>.</span></span>

- <span data-ttu-id="ac174-249">In Auflistungstypen ist nur ein xs:element innerhalb eines xs:sequence-Elements zugelassen.</span><span class="sxs-lookup"><span data-stu-id="ac174-249">In collection types, only one xs:element is allowed within an xs:sequence.</span></span>

 <span data-ttu-id="ac174-250">Auflistungen können einen der folgenden Typen aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ac174-250">Collections can be of the following types:</span></span>

- <span data-ttu-id="ac174-251">Reguläre Auflistungen (z. B. Arrays).</span><span class="sxs-lookup"><span data-stu-id="ac174-251">Regular collections (for example, arrays).</span></span>

- <span data-ttu-id="ac174-252">Wörterbuchauflistungen (die einen Wert einem anderen zuordnen, z.&#160;B. eine <xref:System.Collections.Hashtable>).</span><span class="sxs-lookup"><span data-stu-id="ac174-252">Dictionary collections (mapping one value to another; for example, a <xref:System.Collections.Hashtable>).</span></span>

- <span data-ttu-id="ac174-253">Der einzige Unterschied zwischen einem Wörterbuchtyp und einem Array mit Schlüssel-Wert-Paaren liegt im generierten Programmiermodell.</span><span class="sxs-lookup"><span data-stu-id="ac174-253">The only difference between a dictionary and an array of a key/value pair type is in the generated programming model.</span></span> <span data-ttu-id="ac174-254">Es gibt einen Schemaanmerkungsmechanismus, der verwendet werden kann, um anzugeben, dass ein bestimmter Typ eine Wörterbuchauflistung ist.</span><span class="sxs-lookup"><span data-stu-id="ac174-254">There is a schema annotation mechanism that can be used to indicate that a given type is a dictionary collection.</span></span>

<span data-ttu-id="ac174-255">Die Regeln für die Attribute `ref`, `block`, `default`, `fixed`, `form`und `id` sind die gleichen wie für diejenigen, die keine Auflistungstypen sind.</span><span class="sxs-lookup"><span data-stu-id="ac174-255">The rules for the `ref`, `block`, `default`, `fixed`, `form`, and `id` attributes are the same as for the non-collection case.</span></span> <span data-ttu-id="ac174-256">Die anderen Attribute sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="ac174-256">Other attributes include those in the following table.</span></span>

|<span data-ttu-id="ac174-257">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-257">Attribute</span></span>|<span data-ttu-id="ac174-258">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-258">Schema</span></span>|
|---------------|------------|
|`name`|<span data-ttu-id="ac174-259">Unterstützt, wird der <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> -Eigenschaft des `CollectionDataContractAttribute` -Attributs zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-259">Supported, maps to the <xref:System.Runtime.Serialization.CollectionDataContractAttribute.ItemName%2A> property in the `CollectionDataContractAttribute` attribute.</span></span>|
|`type`|<span data-ttu-id="ac174-260">Unterstützt, wird dem in der Auflistung gespeicherten Typ zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-260">Supported, maps to the type stored in the collection.</span></span>|
|`maxOccurs`|<span data-ttu-id="ac174-261">Größer&#160;1 oder "unbounded".</span><span class="sxs-lookup"><span data-stu-id="ac174-261">Greater than 1 or "unbounded".</span></span> <span data-ttu-id="ac174-262">Das DC-Schema sollte "unbounded" verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac174-262">The DC schema should use "unbounded".</span></span>|
|`minOccurs`|<span data-ttu-id="ac174-263">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-263">Ignored.</span></span>|
|`nillable`|<span data-ttu-id="ac174-264">Beeinflusst die Typzuordnung.</span><span class="sxs-lookup"><span data-stu-id="ac174-264">Affects type mapping.</span></span> <span data-ttu-id="ac174-265">Dieses Attribut wird für Wörterbuchauflistungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-265">This attribute is ignored for dictionary collections.</span></span>|

### <a name="xselement-within-an-xsschema-global-element-declaration"></a><span data-ttu-id="ac174-266">\<xs:element>innerhalb einer \<xs:schema> globalen Element Deklaration</span><span class="sxs-lookup"><span data-stu-id="ac174-266">\<xs:element> within an \<xs:schema> Global Element Declaration</span></span>

- <span data-ttu-id="ac174-267">Eine globale Elementdeklaration (GED), die den gleichen Namen und Namespace wie ein Typ im Schema besitzt, oder die innerhalb ihrer selbst einen anonymen Typ definiert, wird als diesem Typ zugeordnet angesehen.</span><span class="sxs-lookup"><span data-stu-id="ac174-267">A Global Element Declaration (GED) that has the same name and namespace as a type in schema, or that defines an anonymous type inside itself, is said to be associated with the type.</span></span>

- <span data-ttu-id="ac174-268">Schemaexport: Für alle generierten Typen, sowohl einfache als auch komplexe, werden zugeordnete GEDs generiert.</span><span class="sxs-lookup"><span data-stu-id="ac174-268">Schema export: associated GEDs are generated for every generated type, both simple and complex.</span></span>

- <span data-ttu-id="ac174-269">Deserialisierung/Serialisierung: Zugeordnete GEDs werden als Stammelemente für den Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac174-269">Deserialization/serialization: associated GEDs are used as root elements for the type.</span></span>

- <span data-ttu-id="ac174-270">Schemaimport: Zugeordnete GEDs sind nicht erforderlich und werden ignoriert, wenn sie den folgenden Regeln entsprechen (es sei denn, sie definieren Typen).</span><span class="sxs-lookup"><span data-stu-id="ac174-270">Schema import: associated GEDs are not required and are ignored if they follow the following rules (unless they define types).</span></span>

|<span data-ttu-id="ac174-271">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-271">Attribute</span></span>|<span data-ttu-id="ac174-272">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-272">Schema</span></span>|
|---------------|------------|
|`abstract`|<span data-ttu-id="ac174-273">Muss für zugeordnete GEDs den Wert false aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac174-273">Must be false for associated GEDs.</span></span>|
|`block`|<span data-ttu-id="ac174-274">Unzulässig in zugeordneten GEDs.</span><span class="sxs-lookup"><span data-stu-id="ac174-274">Forbidden in associated GEDs.</span></span>|
|`default`|<span data-ttu-id="ac174-275">Unzulässig in zugeordneten GEDs.</span><span class="sxs-lookup"><span data-stu-id="ac174-275">Forbidden in associated GEDs.</span></span>|
|`final`|<span data-ttu-id="ac174-276">Muss für zugeordnete GEDs den Wert false aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac174-276">Must be false for associated GEDs.</span></span>|
|`fixed`|<span data-ttu-id="ac174-277">Unzulässig in zugeordneten GEDs.</span><span class="sxs-lookup"><span data-stu-id="ac174-277">Forbidden in associated GEDs.</span></span>|
|`id`|<span data-ttu-id="ac174-278">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-278">Ignored.</span></span>|
|`name`|<span data-ttu-id="ac174-279">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-279">Supported.</span></span> <span data-ttu-id="ac174-280">Siehe die Definition von zugeordneten GEDs.</span><span class="sxs-lookup"><span data-stu-id="ac174-280">See the definition of associated GEDs.</span></span>|
|`nillable`|<span data-ttu-id="ac174-281">Muss für zugeordnete GEDs den Wert true aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac174-281">Must be true for associated GEDs.</span></span>|
|`substitutionGroup`|<span data-ttu-id="ac174-282">Unzulässig in zugeordneten GEDs.</span><span class="sxs-lookup"><span data-stu-id="ac174-282">Forbidden in associated GEDs.</span></span>|
|`type`|<span data-ttu-id="ac174-283">Unterstützt. Muss dem zugeordneten Typ für zugeordnete GEDs entsprechen (außer wenn das Element einen anonymen Typ enthält).</span><span class="sxs-lookup"><span data-stu-id="ac174-283">Supported, and must match the associated type for associated GEDs (unless the element contains an anonymous type).</span></span>|

### <a name="xselement-contents"></a><span data-ttu-id="ac174-284">\<xs:element>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-284">\<xs:element>: contents</span></span>

|<span data-ttu-id="ac174-285">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-285">Contents</span></span>|<span data-ttu-id="ac174-286">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-286">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="ac174-287">Unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="ac174-287">Supported.\*</span></span>|
|`complexType`|<span data-ttu-id="ac174-288">Unterstützt.\*</span><span class="sxs-lookup"><span data-stu-id="ac174-288">Supported.\*</span></span>|
|`unique`|<span data-ttu-id="ac174-289">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-289">Ignored.</span></span>|
|`key`|<span data-ttu-id="ac174-290">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-290">Ignored.</span></span>|
|`keyref`|<span data-ttu-id="ac174-291">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-291">Ignored.</span></span>|
|<span data-ttu-id="ac174-292">(leer)</span><span class="sxs-lookup"><span data-stu-id="ac174-292">(blank)</span></span>|<span data-ttu-id="ac174-293">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-293">Supported.</span></span>|

<span data-ttu-id="ac174-294">\*Bei der Verwendung der `simpleType` -und- `complexType,` Zuordnung für anonyme Typen ist dasselbe wie bei nicht anonymen Typen, mit dem Unterschied, dass es keine anonymen Datenverträge gibt und daher ein benannter Datenvertrag mit einem generierten Namen erstellt wird, der vom Elementnamen abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="ac174-294">\* When using the `simpleType` and `complexType,` mapping for anonymous types is the same as for non-anonymous types, except that there is no anonymous data contracts, and so a named data contract is created, with a generated name derived from the element name.</span></span> <span data-ttu-id="ac174-295">Die folgende Liste enthält die Regeln für anonyme Typen:</span><span class="sxs-lookup"><span data-stu-id="ac174-295">The rules for anonymous types are in the following list:</span></span>

- <span data-ttu-id="ac174-296">WCF-Implementierungsdetail: Wenn der `xs:element` Name keine Punkte enthält, wird der anonyme Typ einem inneren Typ des äußeren Daten Vertrags Typs zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-296">WCF implementation detail: If the `xs:element` name does not contain periods, the anonymous type maps to an inner type of the outer data contract type.</span></span> <span data-ttu-id="ac174-297">Wenn der Name Punkte enthält, ist der resultierende Datenvertragstyp unabhängig (kein innerer Typ).</span><span class="sxs-lookup"><span data-stu-id="ac174-297">If the name contains periods, the resulting data contract type is independent (not an inner type).</span></span>

- <span data-ttu-id="ac174-298">Der generierte Datenvertragsname des inneren Typs setzt sich zusammen aus dem Namen des äußeren Typs, gefolgt von einem Punkt, dem Namen des Elements und der Zeichenfolge "Type".</span><span class="sxs-lookup"><span data-stu-id="ac174-298">The generated data contract name of the inner type is the data contract name of the outer type followed by a period, the name of the element, and the string "Type".</span></span>

- <span data-ttu-id="ac174-299">Ist ein Datenvertrag mit diesem Namen bereits vorhanden, wird dem Namen&#160;"1", "2", "3" usw. angehängt, um ihn eindeutig zu machen.</span><span class="sxs-lookup"><span data-stu-id="ac174-299">If a data contract with such a name already exists, the name is made unique by appending "1", "2", "3", and so on until a unique name is created.</span></span>

## <a name="simple-types---xssimpletype"></a><span data-ttu-id="ac174-300">Einfache Typen:\<xs:simpleType></span><span class="sxs-lookup"><span data-stu-id="ac174-300">Simple Types - \<xs:simpleType></span></span>

### <a name="xssimpletype-attributes"></a><span data-ttu-id="ac174-301">\<xs:simpleType>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-301">\<xs:simpleType>: attributes</span></span>

|<span data-ttu-id="ac174-302">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-302">Attribute</span></span>|<span data-ttu-id="ac174-303">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-303">Schema</span></span>|
|---------------|------------|
|`final`|<span data-ttu-id="ac174-304">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-304">Ignored.</span></span>|
|`id`|<span data-ttu-id="ac174-305">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-305">Ignored.</span></span>|
|`name`|<span data-ttu-id="ac174-306">Unterstützt, wird dem Namen des Datenvertrags zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-306">Supported, maps to the data contract name.</span></span>|

### <a name="xssimpletype-contents"></a><span data-ttu-id="ac174-307">\<xs:simpleType>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-307">\<xs:simpleType>: contents</span></span>

|<span data-ttu-id="ac174-308">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-308">Contents</span></span>|<span data-ttu-id="ac174-309">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-309">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="ac174-310">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-310">Supported.</span></span> <span data-ttu-id="ac174-311">Wird Enumerationsdatenverträgen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-311">Maps to enumeration data contracts.</span></span> <span data-ttu-id="ac174-312">Dieses Attribut wird ignoriert, wenn es nicht zum Enumerationsmuster passt.</span><span class="sxs-lookup"><span data-stu-id="ac174-312">This attribute is ignored if it does not match the enumeration pattern.</span></span> <span data-ttu-id="ac174-313">Siehe den Abschnitt `xs:simpleType` -Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ac174-313">See the `xs:simpleType` restrictions section.</span></span>|
|`list`|<span data-ttu-id="ac174-314">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-314">Supported.</span></span> <span data-ttu-id="ac174-315">Wird Flagenumerationsdatenverträgen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-315">Maps to flag enumeration data contracts.</span></span> <span data-ttu-id="ac174-316">Siehe den Abschnitt `xs:simpleType` -Listen.</span><span class="sxs-lookup"><span data-stu-id="ac174-316">See the `xs:simpleType` lists section.</span></span>|
|`union`|<span data-ttu-id="ac174-317">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-317">Forbidden.</span></span>|

### \<xs:restriction>

- <span data-ttu-id="ac174-318">Einschränkungen komplexer Typen werden nur für base="`xs:anyType`" unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-318">Complex type restrictions are supported only for base="`xs:anyType`".</span></span>

- <span data-ttu-id="ac174-319">Einfache Typeinschränkungen von `xs:string` , die keine anderen Einschränkungsfacets als `xs:enumeration` haben, werden Enumerationsdatenverträgen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-319">Simple type restrictions of `xs:string` that do not have any restriction facets other than `xs:enumeration` are mapped to enumeration data contracts.</span></span>

- <span data-ttu-id="ac174-320">Alle anderen einfachen Typeinschränkungen werden den Typen zugeordnet, die sie einschränken.</span><span class="sxs-lookup"><span data-stu-id="ac174-320">All other simple type restrictions are mapped to the types they restrict.</span></span> <span data-ttu-id="ac174-321">Beispielsweise wird eine Einschränkung von `xs:int` einem Integer zugeordnet, wie es auch bei `xs:int` selbst der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="ac174-321">For example, a restriction of `xs:int` maps to an integer, just as `xs:int` itself does.</span></span> <span data-ttu-id="ac174-322">Weitere Informationen zur primitiven Typzuordnung finden Sie unter Type/primitive Mapping.</span><span class="sxs-lookup"><span data-stu-id="ac174-322">For more information about primitive type mapping, see Type/primitive mapping.</span></span>

### <a name="xsrestriction-attributes"></a><span data-ttu-id="ac174-323">\<xs:restriction>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-323">\<xs:restriction>: attributes</span></span>

|<span data-ttu-id="ac174-324">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-324">Attribute</span></span>|<span data-ttu-id="ac174-325">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-325">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="ac174-326">Muss ein unterstützter einfacher Typ oder `xs:anyType`sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-326">Must be a supported simple type or `xs:anyType`.</span></span>|
|`id`|<span data-ttu-id="ac174-327">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-327">Ignored.</span></span>|

### <a name="xsrestriction-for-all-other-cases-contents"></a><span data-ttu-id="ac174-328">\<xs:restriction>für alle anderen Fälle: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-328">\<xs:restriction> for all other cases: contents</span></span>

|<span data-ttu-id="ac174-329">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-329">Contents</span></span>|<span data-ttu-id="ac174-330">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-330">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="ac174-331">Muss, falls vorhanden, von einem unterstützten primitiven Typ abgeleitet sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-331">If present, must be derived from a supported primitive type.</span></span>|
|`minExclusive`|<span data-ttu-id="ac174-332">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-332">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="ac174-333">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-333">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="ac174-334">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-334">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="ac174-335">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-335">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="ac174-336">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-336">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="ac174-337">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-337">Ignored.</span></span>|
|`length`|<span data-ttu-id="ac174-338">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-338">Ignored.</span></span>|
|`minLength`|<span data-ttu-id="ac174-339">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-339">Ignored.</span></span>|
|`maxLength`|<span data-ttu-id="ac174-340">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-340">Ignored.</span></span>|
|`enumeration`|<span data-ttu-id="ac174-341">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-341">Ignored.</span></span>|
|`whiteSpace`|<span data-ttu-id="ac174-342">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-342">Ignored.</span></span>|
|`pattern`|<span data-ttu-id="ac174-343">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-343">Ignored.</span></span>|
|<span data-ttu-id="ac174-344">(leer)</span><span class="sxs-lookup"><span data-stu-id="ac174-344">(blank)</span></span>|<span data-ttu-id="ac174-345">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-345">Supported.</span></span>|

## <a name="enumeration"></a><span data-ttu-id="ac174-346">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ac174-346">Enumeration</span></span>

### <a name="xsrestriction-for-enumerations-attributes"></a><span data-ttu-id="ac174-347">\<xs:restriction>für Enumerationen: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-347">\<xs:restriction> for enumerations: attributes</span></span>

|<span data-ttu-id="ac174-348">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-348">Attribute</span></span>|<span data-ttu-id="ac174-349">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-349">Schema</span></span>|
|---------------|------------|
|`base`|<span data-ttu-id="ac174-350">Muss, falls vorhanden, `xs:string`sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-350">If present, must be `xs:string`.</span></span>|
|`id`|<span data-ttu-id="ac174-351">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-351">Ignored.</span></span>|

### <a name="xsrestriction-for-enumerations-contents"></a><span data-ttu-id="ac174-352">\<xs:restriction>für Enumerationen: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-352">\<xs:restriction> for enumerations: contents</span></span>

|<span data-ttu-id="ac174-353">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-353">Contents</span></span>|<span data-ttu-id="ac174-354">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-354">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="ac174-355">Muss, falls vorhanden, eine vom Datenvertrag (dieser Abschnitt) unterstützte Enumerationsbeschränkung sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-355">If present, must be an enumeration restriction supported by the data contract (this section).</span></span>|
|`minExclusive`|<span data-ttu-id="ac174-356">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-356">Ignored.</span></span>|
|`minInclusive`|<span data-ttu-id="ac174-357">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-357">Ignored.</span></span>|
|`maxExclusive`|<span data-ttu-id="ac174-358">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-358">Ignored.</span></span>|
|`maxInclusive`|<span data-ttu-id="ac174-359">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-359">Ignored.</span></span>|
|`totalDigits`|<span data-ttu-id="ac174-360">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-360">Ignored.</span></span>|
|`fractionDigits`|<span data-ttu-id="ac174-361">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-361">Ignored.</span></span>|
|`length`|<span data-ttu-id="ac174-362">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-362">Forbidden.</span></span>|
|`minLength`|<span data-ttu-id="ac174-363">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-363">Forbidden.</span></span>|
|`maxLength`|<span data-ttu-id="ac174-364">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-364">Forbidden.</span></span>|
|`enumeration`|<span data-ttu-id="ac174-365">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-365">Supported.</span></span> <span data-ttu-id="ac174-366">Enumerations-"ID" wird ignoriert, und "value" wird dem Wertnamen im Enumerationsdatenvertrag zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-366">Enumeration "id" is ignored, and "value" maps to the value name in the enumeration data contract.</span></span>|
|`whiteSpace`|<span data-ttu-id="ac174-367">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-367">Forbidden.</span></span>|
|`pattern`|<span data-ttu-id="ac174-368">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-368">Forbidden.</span></span>|
|<span data-ttu-id="ac174-369">(leer)</span><span class="sxs-lookup"><span data-stu-id="ac174-369">(empty)</span></span>|<span data-ttu-id="ac174-370">Unterstützt, wird leerem Enumerationstyp zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-370">Supported, maps to empty enumeration type.</span></span>|

 <span data-ttu-id="ac174-371">Der folgende Code zeigt eine C#-Enumerationsklasse.</span><span class="sxs-lookup"><span data-stu-id="ac174-371">The following code shows a C# enumeration class.</span></span>

```csharp
public enum MyEnum
{
  first = 3,
  second = 4,
  third =5
}
```

<span data-ttu-id="ac174-372">Diese Klasse wird vom `DataContractSerializer`dem folgenden Schema zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-372">This class maps to the following schema by the `DataContractSerializer`.</span></span> <span data-ttu-id="ac174-373">Wenn die Enumerationswerte mit&#160;1 beginnen, werden keine `xs:annotation` -Blöcke generiert.</span><span class="sxs-lookup"><span data-stu-id="ac174-373">If enumeration values start from 1, `xs:annotation` blocks are not generated.</span></span>

```xml
<xs:simpleType name="MyEnum">
  <xs:restriction base="xs:string">
    <xs:enumeration value="first">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          3
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
    <xs:enumeration value="second">
      <xs:annotation>
        <xs:appinfo>
          <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">
          4
          </EnumerationValue>
        </xs:appinfo>
      </xs:annotation>
    </xs:enumeration>
  </xs:restriction>
</xs:simpleType>
```

### \<xs:list>

<span data-ttu-id="ac174-374">`DataContractSerializer` ordnet mit `System.FlagsAttribute` markierte Enumerationstypen einer von `xs:list` abgeleiteten `xs:string`zu.</span><span class="sxs-lookup"><span data-stu-id="ac174-374">`DataContractSerializer` maps enumeration types marked with `System.FlagsAttribute` to `xs:list` derived from `xs:string`.</span></span> <span data-ttu-id="ac174-375">Andere `xs:list` -Variationen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-375">No other `xs:list` variations are supported.</span></span>

### <a name="xslist-attributes"></a><span data-ttu-id="ac174-376">\<xs:list>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-376">\<xs:list>: attributes</span></span>

|<span data-ttu-id="ac174-377">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-377">Attribute</span></span>|<span data-ttu-id="ac174-378">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-378">Schema</span></span>|
|---------------|------------|
|`itemType`|<span data-ttu-id="ac174-379">Unzulässig.</span><span class="sxs-lookup"><span data-stu-id="ac174-379">Forbidden.</span></span>|
|`id`|<span data-ttu-id="ac174-380">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-380">Ignored.</span></span>|

### <a name="xslist-contents"></a><span data-ttu-id="ac174-381">\<xs:list>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-381">\<xs:list>: contents</span></span>

|<span data-ttu-id="ac174-382">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-382">Contents</span></span>|<span data-ttu-id="ac174-383">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-383">Schema</span></span>|
|--------------|------------|
|`simpleType`|<span data-ttu-id="ac174-384">Muss eine Einschränkung von `xs:string` mit `xs:enumeration` -Facet sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-384">Must be restriction from `xs:string` using `xs:enumeration` facet.</span></span>|

<span data-ttu-id="ac174-385">Sind die Enumerationswerte keine Folge mit Potenzen des Werts&#160;2 (für Flags der Standard), wird der Wert im `xs:annotation/xs:appInfo/ser:EnumerationValue` -Element gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ac174-385">If enumeration value does not follow a power of 2 progression (default for Flags), the value is stored in the `xs:annotation/xs:appInfo/ser:EnumerationValue` element.</span></span>

<span data-ttu-id="ac174-386">Der folgende Code definiert z.&#160;B. einen Enumerationstyp für Flags.</span><span class="sxs-lookup"><span data-stu-id="ac174-386">For example, the following code flags an enumeration type.</span></span>

```csharp
[Flags]
public enum AuthFlags
{
  AuthAnonymous = 1,
  AuthBasic = 2,
  AuthNTLM = 4,
  AuthMD5 = 16,
  AuthWindowsLiveID = 64,
}
```

<span data-ttu-id="ac174-387">Dieser Typ wird dem folgenden Schema zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-387">This type maps to the following schema.</span></span>

```xml
<xs:simpleType name="AuthFlags">
    <xs:list>
      <xs:simpleType>
        <xs:restriction base="xs:string">
          <xs:enumeration value="AuthAnonymous" />
          <xs:enumeration value="AuthBasic" />
          <xs:enumeration value="AuthNTLM" />
          <xs:enumeration value="AuthMD5">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">16</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
          <xs:enumeration value="AuthWindowsLiveID">
            <xs:annotation>
              <xs:appinfo>
                <EnumerationValue xmlns="http://schemas.microsoft.com/2003/10/Serialization/">64</EnumerationValue>
              </xs:appinfo>
            </xs:annotation>
          </xs:enumeration>
        </xs:restriction>
      </xs:simpleType>
    </xs:list>
  </xs:simpleType>
```

## <a name="inheritance"></a><span data-ttu-id="ac174-388">Vererbung</span><span class="sxs-lookup"><span data-stu-id="ac174-388">Inheritance</span></span>

### <a name="general-rules"></a><span data-ttu-id="ac174-389">Allgemeine Regeln</span><span class="sxs-lookup"><span data-stu-id="ac174-389">General rules</span></span>

<span data-ttu-id="ac174-390">Ein Datenvertrag kann von einem anderen Datenvertrag erben.</span><span class="sxs-lookup"><span data-stu-id="ac174-390">A data contract can inherit from another data contract.</span></span> <span data-ttu-id="ac174-391">Solche Datenverträge werden einem Basistyp zugeordnet und durch Erweiterungstypen mithilfe des `<xs:extension>` -XML-Schemakonstrukts abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ac174-391">Such data contracts map to a base and are derived by extension types using the `<xs:extension>` XML Schema construct.</span></span>

<span data-ttu-id="ac174-392">Ein Datenvertrag kann nicht von einem Auflistungsdatenvertrag erben.</span><span class="sxs-lookup"><span data-stu-id="ac174-392">A data contract cannot inherit from a collection data contract.</span></span>

<span data-ttu-id="ac174-393">Der folgende Code stellt z.&#160;B. einen Datenvertrag dar.</span><span class="sxs-lookup"><span data-stu-id="ac174-393">For example, the following code is a data contract.</span></span>

```csharp
[DataContract]
public class Person
{
  [DataMember]
  public string Name;
}
[DataContract]
public class Employee : Person
{
  [DataMember]
  public int ID;
}
```

<span data-ttu-id="ac174-394">Dieser Datenvertrag wird der folgenden XML-Schema-Typdeklaration zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-394">This data contract maps to the following XML Schema type declaration.</span></span>

```xml
<xs:complexType name="Employee">
 <xs:complexContent mixed="false">
  <xs:extension base="tns:Person">
   <xs:sequence>
    <xs:element minOccurs="0" name="ID" type="xs:int"/>
   </xs:sequence>
  </xs:extension>
 </xs:complexContent>
</xs:complexType>
<xs:complexType name="Person">
 <xs:sequence>
  <xs:element minOccurs="0" name="Name"
    nillable="true" type="xs:string"/>
 </xs:sequence>
</xs:complexType>
```

### <a name="xscomplexcontent-attributes"></a><span data-ttu-id="ac174-395">\<xs:complexContent>: Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-395">\<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="ac174-396">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-396">Attribute</span></span>|<span data-ttu-id="ac174-397">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-397">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="ac174-398">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-398">Ignored.</span></span>|
|`mixed`|<span data-ttu-id="ac174-399">Muss den Wert false aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ac174-399">Must be false.</span></span>|

### <a name="xscomplexcontent-contents"></a><span data-ttu-id="ac174-400">\<xs:complexContent>: Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-400">\<xs:complexContent>: contents</span></span>

|<span data-ttu-id="ac174-401">Contents</span><span class="sxs-lookup"><span data-stu-id="ac174-401">Contents</span></span>|<span data-ttu-id="ac174-402">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-402">Schema</span></span>|
|--------------|------------|
|`restriction`|<span data-ttu-id="ac174-403">Unzulässig, außer wenn base="`xs:anyType`".</span><span class="sxs-lookup"><span data-stu-id="ac174-403">Forbidden, except when base="`xs:anyType`".</span></span> <span data-ttu-id="ac174-404">Letzteres entspricht der Platzierung des Inhalts von `xs:restriction` direkt unter den Container von `xs:complexContent`.</span><span class="sxs-lookup"><span data-stu-id="ac174-404">The latter is equivalent to placing the content of the `xs:restriction` directly under the container of the `xs:complexContent`.</span></span>|
|`extension`|<span data-ttu-id="ac174-405">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-405">Supported.</span></span> <span data-ttu-id="ac174-406">Wird der Datenvertragsvererbung zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-406">Maps to data contract inheritance.</span></span>|

### <a name="xsextension-in-xscomplexcontent-attributes"></a><span data-ttu-id="ac174-407">\<xs:extension>in \<xs:complexContent> : Attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-407">\<xs:extension> in \<xs:complexContent>: attributes</span></span>

|<span data-ttu-id="ac174-408">attribute</span><span class="sxs-lookup"><span data-stu-id="ac174-408">Attribute</span></span>|<span data-ttu-id="ac174-409">Schema</span><span class="sxs-lookup"><span data-stu-id="ac174-409">Schema</span></span>|
|---------------|------------|
|`id`|<span data-ttu-id="ac174-410">Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac174-410">Ignored.</span></span>|
|`base`|<span data-ttu-id="ac174-411">Unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac174-411">Supported.</span></span> <span data-ttu-id="ac174-412">Wird dem Basisdatenvertragstyp zugeordnet, von dem dieser Typ erbt.</span><span class="sxs-lookup"><span data-stu-id="ac174-412">Maps to the base data contract type that this type inherits from.</span></span>|

### <a name="xsextension-in-xscomplexcontent-contents"></a><span data-ttu-id="ac174-413">\<xs:extension>in \<xs:complexContent> : Inhalt</span><span class="sxs-lookup"><span data-stu-id="ac174-413">\<xs:extension> in \<xs:complexContent>: contents</span></span>

<span data-ttu-id="ac174-414">Die Regeln sind die gleichen wie für den `<xs:complexType>` -Inhalt.</span><span class="sxs-lookup"><span data-stu-id="ac174-414">The rules are the same as for `<xs:complexType>` contents.</span></span>

<span data-ttu-id="ac174-415">Wird `<xs:sequence>` angegeben, werden dessen Memberelemente den zusätzlichen Datenmembern zugeordnet, die im abgeleiteten Datenvertrag vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ac174-415">If an `<xs:sequence>` is provided, its member elements map to additional data members that are present in the derived data contract.</span></span>

<span data-ttu-id="ac174-416">Wenn ein abgeleiteter Typ ein Element mit dem gleichen Namen wie ein Element in einem Basistyp enthält, wird die doppelte Elementdeklaration einem Datenmember zugeordnet, für den ein eindeutiger Name generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ac174-416">If a derived type contains an element with the same name as an element in a base type, the duplicate element declaration maps to a data member with a name that is generated to be unique.</span></span> <span data-ttu-id="ac174-417">Dazu werden dem Datenmember so lange positive Ganzzahlen hinzugefügt ("member1", "member2" usw.), bis ein eindeutiger Name gefunden ist.</span><span class="sxs-lookup"><span data-stu-id="ac174-417">Positive integer numbers are added to the data member name ("member1", "member2", and so on) until a unique name is found.</span></span> <span data-ttu-id="ac174-418">Umgekehrt:</span><span class="sxs-lookup"><span data-stu-id="ac174-418">Conversely:</span></span>

- <span data-ttu-id="ac174-419">Wenn ein abgeleiteter Datenvertrag einen Datenmember mit dem gleichen Namen und Typ wie ein Datenmember in einem Basisdatenvertrag enthält, generiert der `DataContractSerializer` dieses entsprechende Element im abgeleiteten Typ.</span><span class="sxs-lookup"><span data-stu-id="ac174-419">If a derived data contract has a data member with the same name and type as a data member in a base data contract, `DataContractSerializer` generates this corresponding element in the derived type.</span></span>

- <span data-ttu-id="ac174-420">Wenn ein abgeleiteter Datenvertrag einen Datenmember mit dem gleichen Namen, jedoch einem anderen Typ als ein Datenmember in einem Basisdatenvertrag enthält, importiert der `DataContractSerializer` ein Schema mit einem Element des Typs `xs:anyType` in die Deklarationen sowohl des Basistyps als auch des abgeleiteten Typs.</span><span class="sxs-lookup"><span data-stu-id="ac174-420">If a derived data contract has a data member with the same name as a data member in a base data contract but a different type, the `DataContractSerializer` imports a schema with an element of the type `xs:anyType` in both base type and derived type declarations.</span></span> <span data-ttu-id="ac174-421">Der ursprüngliche Typname wird in `xs:annotations/xs:appInfo/ser:ActualType/@Name`beibehalten.</span><span class="sxs-lookup"><span data-stu-id="ac174-421">The original type name is preserved in `xs:annotations/xs:appInfo/ser:ActualType/@Name`.</span></span>

<span data-ttu-id="ac174-422">Beide Variationen können zu einem Schema mit einem mehrdeutigen Inhaltsmodell führen, das von der Reihenfolge der jeweiligen Datenmember abhängt.</span><span class="sxs-lookup"><span data-stu-id="ac174-422">Both variations may lead to a schema with an ambiguous content model, which depends on the order of the respective data members.</span></span>

## <a name="typeprimitive-mapping"></a><span data-ttu-id="ac174-423">Zuordnung von Typen zu primitivem Typen</span><span class="sxs-lookup"><span data-stu-id="ac174-423">Type/primitive mapping</span></span>

<span data-ttu-id="ac174-424">Der `DataContractSerializer` verwendet die folgende Zuordnung für primitive Typen von XML-Schemas.</span><span class="sxs-lookup"><span data-stu-id="ac174-424">The `DataContractSerializer` uses the following mapping for XML Schema primitive types.</span></span>

|<span data-ttu-id="ac174-425">XSD-Typ</span><span class="sxs-lookup"><span data-stu-id="ac174-425">XSD type</span></span>|<span data-ttu-id="ac174-426">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="ac174-426">.NET type</span></span>|
|--------------|---------------|
|`anyType`|<span data-ttu-id="ac174-427"><xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="ac174-427"><xref:System.Object>.</span></span>|
|`anySimpleType`|<span data-ttu-id="ac174-428"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-428"><xref:System.String>.</span></span>|
|`duration`|<span data-ttu-id="ac174-429"><xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="ac174-429"><xref:System.TimeSpan>.</span></span>|
|`dateTime`|<span data-ttu-id="ac174-430"><xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="ac174-430"><xref:System.DateTime>.</span></span>|
|`dateTimeOffset`|<span data-ttu-id="ac174-431"><xref:System.DateTime> und <xref:System.TimeSpan> für den Offset.</span><span class="sxs-lookup"><span data-stu-id="ac174-431"><xref:System.DateTime> and <xref:System.TimeSpan> for the offset.</span></span> <span data-ttu-id="ac174-432">Siehe DateTimeOffset-Serialisierung (unten).</span><span class="sxs-lookup"><span data-stu-id="ac174-432">See DateTimeOffset Serialization below.</span></span>|
|`time`|<span data-ttu-id="ac174-433"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-433"><xref:System.String>.</span></span>|
|`date`|<span data-ttu-id="ac174-434"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-434"><xref:System.String>.</span></span>|
|`gYearMonth`|<span data-ttu-id="ac174-435"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-435"><xref:System.String>.</span></span>|
|`gYear`|<span data-ttu-id="ac174-436"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-436"><xref:System.String>.</span></span>|
|`gMonthDay`|<span data-ttu-id="ac174-437"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-437"><xref:System.String>.</span></span>|
|`gDay`|<span data-ttu-id="ac174-438"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-438"><xref:System.String>.</span></span>|
|`gMonth`|<span data-ttu-id="ac174-439"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-439"><xref:System.String>.</span></span>|
|`boolean`|<xref:System.Boolean>|
|`base64Binary`|<span data-ttu-id="ac174-440"><xref:System.Byte> -Array.</span><span class="sxs-lookup"><span data-stu-id="ac174-440"><xref:System.Byte> array.</span></span>|
|`hexBinary`|<span data-ttu-id="ac174-441"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-441"><xref:System.String>.</span></span>|
|`float`|<span data-ttu-id="ac174-442"><xref:System.Single>.</span><span class="sxs-lookup"><span data-stu-id="ac174-442"><xref:System.Single>.</span></span>|
|`double`|<span data-ttu-id="ac174-443"><xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="ac174-443"><xref:System.Double>.</span></span>|
|`anyURI`|<span data-ttu-id="ac174-444"><xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="ac174-444"><xref:System.Uri>.</span></span>|
|`QName`|<span data-ttu-id="ac174-445"><xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="ac174-445"><xref:System.Xml.XmlQualifiedName>.</span></span>|
|`string`|<span data-ttu-id="ac174-446"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-446"><xref:System.String>.</span></span>|
|`normalizedString`|<span data-ttu-id="ac174-447"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-447"><xref:System.String>.</span></span>|
|`token`|<span data-ttu-id="ac174-448"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-448"><xref:System.String>.</span></span>|
|`language`|<span data-ttu-id="ac174-449"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-449"><xref:System.String>.</span></span>|
|`Name`|<span data-ttu-id="ac174-450"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-450"><xref:System.String>.</span></span>|
|`NCName`|<span data-ttu-id="ac174-451"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-451"><xref:System.String>.</span></span>|
|`ID`|<span data-ttu-id="ac174-452"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-452"><xref:System.String>.</span></span>|
|`IDREF`|<span data-ttu-id="ac174-453"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-453"><xref:System.String>.</span></span>|
|`IDREFS`|<span data-ttu-id="ac174-454"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-454"><xref:System.String>.</span></span>|
|`ENTITY`|<span data-ttu-id="ac174-455"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-455"><xref:System.String>.</span></span>|
|`ENTITIES`|<span data-ttu-id="ac174-456"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-456"><xref:System.String>.</span></span>|
|`NMTOKEN`|<span data-ttu-id="ac174-457"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-457"><xref:System.String>.</span></span>|
|`NMTOKENS`|<span data-ttu-id="ac174-458"><xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ac174-458"><xref:System.String>.</span></span>|
|`decimal`|<span data-ttu-id="ac174-459"><xref:System.Decimal>.</span><span class="sxs-lookup"><span data-stu-id="ac174-459"><xref:System.Decimal>.</span></span>|
|`integer`|<span data-ttu-id="ac174-460"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-460"><xref:System.Int64>.</span></span>|
|`nonPositiveInteger`|<span data-ttu-id="ac174-461"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-461"><xref:System.Int64>.</span></span>|
|`negativeInteger`|<span data-ttu-id="ac174-462"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-462"><xref:System.Int64>.</span></span>|
|`long`|<span data-ttu-id="ac174-463"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-463"><xref:System.Int64>.</span></span>|
|`int`|<span data-ttu-id="ac174-464"><xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="ac174-464"><xref:System.Int32>.</span></span>|
|`short`|<span data-ttu-id="ac174-465"><xref:System.Int16>.</span><span class="sxs-lookup"><span data-stu-id="ac174-465"><xref:System.Int16>.</span></span>|
|`Byte`|<span data-ttu-id="ac174-466"><xref:System.SByte>.</span><span class="sxs-lookup"><span data-stu-id="ac174-466"><xref:System.SByte>.</span></span>|
|`nonNegativeInteger`|<span data-ttu-id="ac174-467"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-467"><xref:System.Int64>.</span></span>|
|`unsignedLong`|<span data-ttu-id="ac174-468"><xref:System.UInt64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-468"><xref:System.UInt64>.</span></span>|
|`unsignedInt`|<span data-ttu-id="ac174-469"><xref:System.UInt32>.</span><span class="sxs-lookup"><span data-stu-id="ac174-469"><xref:System.UInt32>.</span></span>|
|`unsignedShort`|<span data-ttu-id="ac174-470"><xref:System.UInt16>.</span><span class="sxs-lookup"><span data-stu-id="ac174-470"><xref:System.UInt16>.</span></span>|
|`unsignedByte`|<span data-ttu-id="ac174-471"><xref:System.Byte>.</span><span class="sxs-lookup"><span data-stu-id="ac174-471"><xref:System.Byte>.</span></span>|
|`positiveInteger`|<span data-ttu-id="ac174-472"><xref:System.Int64>.</span><span class="sxs-lookup"><span data-stu-id="ac174-472"><xref:System.Int64>.</span></span>|

## <a name="iserializable-types-mapping"></a><span data-ttu-id="ac174-473">Zuordnung von ISerializable-Typen</span><span class="sxs-lookup"><span data-stu-id="ac174-473">ISerializable types mapping</span></span>

<span data-ttu-id="ac174-474">In .NET Framework Version 1,0 <xref:System.Runtime.Serialization.ISerializable> wurde als allgemeiner Mechanismus zum Serialisieren von Objekten für Persistenz oder Datenübertragung eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ac174-474">In .NET Framework version 1.0, <xref:System.Runtime.Serialization.ISerializable> was introduced as a general mechanism to serialize objects for persistence or data transfer.</span></span> <span data-ttu-id="ac174-475">Es gibt viele .NET Framework Typen, die implementieren `ISerializable` und zwischen Anwendungen übermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="ac174-475">There are many .NET Framework types that implement `ISerializable` and that can be passed between applications.</span></span> <span data-ttu-id="ac174-476"><xref:System.Runtime.Serialization.DataContractSerializer> unterstützt von sich aus `ISerializable` -Klassen.</span><span class="sxs-lookup"><span data-stu-id="ac174-476"><xref:System.Runtime.Serialization.DataContractSerializer> naturally provides support for `ISerializable` classes.</span></span> <span data-ttu-id="ac174-477">Der `DataContractSerializer` ordnet `ISerializable` -Implementierungsschematypen zu, die sich nur durch den qualifizierten Namen (QName) des Typs unterscheiden und tatsächlich Eigenschaftenauflistungen sind.</span><span class="sxs-lookup"><span data-stu-id="ac174-477">The `DataContractSerializer` maps `ISerializable` implementation schema types that differ only by the QName (qualified name) of the type and are effectively property collections.</span></span> <span data-ttu-id="ac174-478">Beispielsweise wird der `DataContractSerializer` <xref:System.Exception> folgenden XSD-Typ im- `http://schemas.datacontract.org/2004/07/System` Namespace zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ac174-478">For example, the `DataContractSerializer` maps <xref:System.Exception> to the following XSD type in the `http://schemas.datacontract.org/2004/07/System` namespace.</span></span>

```xml
<xs:complexType name="Exception">
 <xs:sequence>
  <xs:any minOccurs="0" maxOccurs="unbounded"
      namespace="##local" processContents="skip"/>
 </xs:sequence>
 <xs:attribute ref="ser:FactoryType"/>
</xs:complexType>
```

<span data-ttu-id="ac174-479">Das optionale, im Serialisierungsschema des Datenvertrags deklarierte Attribut `ser:FactoryType` verweist auf eine Factoryklasse, die den Typ deserialisieren kann.</span><span class="sxs-lookup"><span data-stu-id="ac174-479">The optional attribute `ser:FactoryType` declared in the Data Contract Serialization schema references a factory class that can deserialize the type.</span></span> <span data-ttu-id="ac174-480">Die Factoryklasse muss Teil der Auflistung bekannter Typen der verwendeten `DataContractSerializer` -Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="ac174-480">The factory class must be part of the known types collection of the `DataContractSerializer` instance being used.</span></span> <span data-ttu-id="ac174-481">Weitere Informationen zu bekannten Typen finden Sie unter [Data Contract Known Types](data-contract-known-types.md).</span><span class="sxs-lookup"><span data-stu-id="ac174-481">For more information about known types, see [Data Contract Known Types](data-contract-known-types.md).</span></span>

## <a name="datacontract-serialization-schema"></a><span data-ttu-id="ac174-482">DataContract-Serialisierungsschema</span><span class="sxs-lookup"><span data-stu-id="ac174-482">DataContract Serialization Schema</span></span>

<span data-ttu-id="ac174-483">Eine Anzahl der vom `DataContractSerializer` exportierten Schemas verwendet Typen, Elemente und Attribute eines speziellen Datenvertrags-Serialisierungsnamespace:</span><span class="sxs-lookup"><span data-stu-id="ac174-483">A number of schemas exported by the `DataContractSerializer` use types, elements, and attributes from a special Data Contract Serialization namespace:</span></span>

`http://schemas.microsoft.com/2003/10/Serialization`

<span data-ttu-id="ac174-484">Das Folgende ist eine vollständige Schemadeklaration für die Datenvertragsserialisierung.</span><span class="sxs-lookup"><span data-stu-id="ac174-484">The following is a complete Data Contract Serialization schema declaration.</span></span>

```xml
<xs:schema attributeFormDefault="qualified"
   elementFormDefault="qualified"
   targetNamespace =
    "http://schemas.microsoft.com/2003/10/Serialization/"
   xmlns:xs="http://www.w3.org/2001/XMLSchema"
   xmlns:tns="http://schemas.microsoft.com/2003/10/Serialization/">

 <!-- Top-level elements for primitive types. -->
 <xs:element name="anyType" nillable="true" type="xs:anyType"/>
 <xs:element name="anyURI" nillable="true" type="xs:anyURI"/>
 <xs:element name="base64Binary"
       nillable="true" type="xs:base64Binary"/>
 <xs:element name="boolean" nillable="true" type="xs:boolean"/>
 <xs:element name="byte" nillable="true" type="xs:byte"/>
 <xs:element name="dateTime" nillable="true" type="xs:dateTime"/>
 <xs:element name="decimal" nillable="true" type="xs:decimal"/>
 <xs:element name="double" nillable="true" type="xs:double"/>
 <xs:element name="float" nillable="true" type="xs:float"/>
 <xs:element name="int" nillable="true" type="xs:int"/>
 <xs:element name="long" nillable="true" type="xs:long"/>
 <xs:element name="QName" nillable="true" type="xs:QName"/>
 <xs:element name="short" nillable="true" type="xs:short"/>
 <xs:element name="string" nillable="true" type="xs:string"/>
 <xs:element name="unsignedByte"
       nillable="true" type="xs:unsignedByte"/>
 <xs:element name="unsignedInt"
       nillable="true" type="xs:unsignedInt"/>
 <xs:element name="unsignedLong"
       nillable="true" type="xs:unsignedLong"/>
 <xs:element name="unsignedShort"
       nillable="true" type="xs:unsignedShort"/>

 <!-- Primitive types introduced for certain .NET simple types. -->
 <xs:element name="char" nillable="true" type="tns:char"/>
 <xs:simpleType name="char">
  <xs:restriction base="xs:int"/>
 </xs:simpleType>

 <!-- xs:duration is restricted to an ordered value space,
    to map to System.TimeSpan -->
 <xs:element name="duration" nillable="true" type="tns:duration"/>
 <xs:simpleType name="duration">
  <xs:restriction base="xs:duration">
   <xs:pattern
     value="\-?P(\d*D)?(T(\d*H)?(\d*M)?(\d*(\.\d*)?S)?)?"/>
   <xs:minInclusive value="-P10675199DT2H48M5.4775808S"/>
   <xs:maxInclusive value="P10675199DT2H48M5.4775807S"/>
  </xs:restriction>
 </xs:simpleType>

 <xs:element name="guid" nillable="true" type="tns:guid"/>
 <xs:simpleType name="guid">
  <xs:restriction base="xs:string">
   <xs:pattern value="[\da-fA-F]{8}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{4}-[\da-fA-F]{12}"/>
  </xs:restriction>
 </xs:simpleType>

 <!-- This is used for schemas exported from ISerializable type. -->
 <xs:attribute name="FactoryType" type="xs:QName"/>
</xs:schema>
```

<span data-ttu-id="ac174-485">Auf Folgendes sollte geachtet werden:</span><span class="sxs-lookup"><span data-stu-id="ac174-485">The following should be noted:</span></span>

- <span data-ttu-id="ac174-486">`ser:char` wurde eingeführt, um Unicode-Zeichen des Typs <xref:System.Char>darzustellen.</span><span class="sxs-lookup"><span data-stu-id="ac174-486">`ser:char` is introduced to represent Unicode characters of type <xref:System.Char>.</span></span>

- <span data-ttu-id="ac174-487">Der `valuespace` von `xs:duration` wurde zu einer geordneten Menge reduziert, damit diese einem <xref:System.TimeSpan>zugeordnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac174-487">The `valuespace` of `xs:duration` is reduced to an ordered set so that it can be mapped to a <xref:System.TimeSpan>.</span></span>

- <span data-ttu-id="ac174-488">`FactoryType` wird in Schemas verwendet, die von Typen exportiert werden, die von <xref:System.Runtime.Serialization.ISerializable>abgeleitet wurden.</span><span class="sxs-lookup"><span data-stu-id="ac174-488">`FactoryType` is used in schemas exported from types that are derived from <xref:System.Runtime.Serialization.ISerializable>.</span></span>

## <a name="importing-non-datacontract-schemas"></a><span data-ttu-id="ac174-489">Importieren von Nicht-DataContract-Schemas</span><span class="sxs-lookup"><span data-stu-id="ac174-489">Importing non-DataContract schemas</span></span>

<span data-ttu-id="ac174-490">`DataContractSerializer` verfügt über die `ImportXmlTypes` -Option, die den Import von Schemas erlaubt, die dem `DataContractSerializer` -XSD-Profil nicht entsprechen (siehe die <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> -Eigenschaft).</span><span class="sxs-lookup"><span data-stu-id="ac174-490">`DataContractSerializer` has the `ImportXmlTypes` option to allow import of schemas that do not conform to the `DataContractSerializer` XSD profile (see the <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> property).</span></span> <span data-ttu-id="ac174-491">Die Festlegung dieser Option auf `true` aktiviert die Akzeptanz nicht-konformer Schematypen und ihre Zuordnung zu der folgenden Implementierung, wobei <xref:System.Xml.Serialization.IXmlSerializable> ein Array von <xref:System.Xml.XmlNode> einschließt (nur der Klassenname unterscheidet sich).</span><span class="sxs-lookup"><span data-stu-id="ac174-491">Setting this option to `true` enables acceptance of non-conforming schema types and mapping them to the following implementation, <xref:System.Xml.Serialization.IXmlSerializable> wrapping an array of <xref:System.Xml.XmlNode> (only the class name differs).</span></span>

```csharp
[GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]
[System.Xml.Serialization.XmlSchemaProviderAttribute("ExportSchema")]
[System.Xml.Serialization.XmlRootAttribute(IsNullable=false)]
public partial class Person : object, IXmlSerializable
{
  private XmlNode[] nodesField;
  private static XmlQualifiedName typeName =
new XmlQualifiedName("Person","http://Microsoft.ServiceModel.Samples");
  public XmlNode[] Nodes
  {
    get {return this.nodesField;}
    set {this.nodesField = value;}
  }
  public void ReadXml(XmlReader reader)
  {
    this.nodesField = XmlSerializableServices.ReadNodes(reader);
  }
  public void WriteXml(XmlWriter writer)
  {
    XmlSerializableServices.WriteNodes(writer, this.Nodes);
  }
  public System.Xml.Schema.XmlSchema GetSchema()
  {
    return null;
  }
  public static XmlQualifiedName ExportSchema(XmlSchemaSet schemas)
  {
    XmlSerializableServices.AddDefaultSchema(schemas, typeName);
    return typeName;
  }
}
```

## <a name="datetimeoffset-serialization"></a><span data-ttu-id="ac174-492">DateTimeOffset-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ac174-492">DateTimeOffset Serialization</span></span>

<span data-ttu-id="ac174-493"><xref:System.DateTimeOffset> wird nicht als primitiver Typ behandelt.</span><span class="sxs-lookup"><span data-stu-id="ac174-493">The <xref:System.DateTimeOffset> is not treated as a primitive type.</span></span> <span data-ttu-id="ac174-494">Stattdessen wird dieser Typ als komplexes Element mit zwei Teilen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ac174-494">Instead, it is serialized as a complex element with two parts.</span></span> <span data-ttu-id="ac174-495">Der erste Teil stellt die Datums- und Uhrzeitangabe dar und der zweite Teil den Offset dieser Datums- und Uhrzeitangabe.</span><span class="sxs-lookup"><span data-stu-id="ac174-495">The first part represents the date time, and the second part represents the offset from the date time.</span></span> <span data-ttu-id="ac174-496">Ein Beispiel für einen serialisierten DateTimeOffset-Wert wird im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac174-496">An example of a serialized DateTimeOffset value is shown in the following code.</span></span>

```xml
<OffSet xmlns:a="http://schemas.datacontract.org/2004/07/System">
  <DateTime i:type="b:dateTime" xmlns=""
    xmlns:b="http://www.w3.org/2001/XMLSchema">2008-08-28T08:00:00
  </DateTime>
  <OffsetMinutes i:type="b:short" xmlns=""
   xmlns:b="http://www.w3.org/2001/XMLSchema">-480
   </OffsetMinutes>
</OffSet>
```

<span data-ttu-id="ac174-497">Das Schema lautet folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="ac174-497">The schema is as follows.</span></span>

```xml
<xs:schema targetNamespace="http://schemas.datacontract.org/2004/07/System">
   <xs:complexType name="DateTimeOffset">
      <xs:sequence minOccurs="1" maxOccurs="1">
         <xs:element name="DateTime" type="xs:dateTime"
         minOccurs="1" maxOccurs="1" />
         <xs:element name="OffsetMinutes" type="xs:short"
         minOccurs="1" maxOccurs="1" />
      </xs:sequence>
   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="ac174-498">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac174-498">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- [<span data-ttu-id="ac174-499">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="ac174-499">Using Data Contracts</span></span>](using-data-contracts.md)
