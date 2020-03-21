---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151129"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="1fce6-102">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1fce6-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="1fce6-103">In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="1fce6-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="1fce6-104">Es gibt drei Möglichkeiten, eine **DataSet-Beziehung** innerhalb eines XSD-Schemas (XML Schema Definition Language) darzustellen:</span><span class="sxs-lookup"><span data-stu-id="1fce6-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="1fce6-105">Geben Sie geschachtelte komplexe Typen an.</span><span class="sxs-lookup"><span data-stu-id="1fce6-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="1fce6-106">Verwenden Sie die **Msdata:Relationship-Anmerkung.**</span><span class="sxs-lookup"><span data-stu-id="1fce6-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="1fce6-107">Geben Sie eine **xs:keyref** ohne die **msdata:ConstraintOnly-Anmerkung** an.</span><span class="sxs-lookup"><span data-stu-id="1fce6-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="1fce6-108">Geschachtelte komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="1fce6-108">Nested Complex Types</span></span>  
 <span data-ttu-id="1fce6-109">Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an.</span><span class="sxs-lookup"><span data-stu-id="1fce6-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="1fce6-110">Das folgende XML-Schemafragment zeigt, dass **OrderDetail** ein untergeordnetes Element des **Order-Elements** ist.</span><span class="sxs-lookup"><span data-stu-id="1fce6-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="1fce6-111">Der XML-Schemazuordnungsprozess erstellt Tabellen im **DataSet,** die den geschachtelten komplexen Typen im Schema entsprechen.</span><span class="sxs-lookup"><span data-stu-id="1fce6-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="1fce6-112">Außerdem werden zusätzliche Spalten erstellt,**-** die als übergeordnete untergeordnete Spalten für die generierten Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fce6-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="1fce6-113">Beachten Sie,**-** dass diese übergeordneten untergeordneten Spalten Beziehungen angeben, die nicht mit der Angabe von Primärschlüssel-/Fremdschlüsseleinschränkungen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="1fce6-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="1fce6-114">Die "msdata:Relationship"-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="1fce6-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="1fce6-115">Mit der **msdata:Relationship-Anmerkung** können Sie explizit parent-child-Beziehungen zwischen Elementen im Schema angeben, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="1fce6-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="1fce6-116">Das folgende Beispiel zeigt **Relationship** die Struktur des Beziehungselements.</span><span class="sxs-lookup"><span data-stu-id="1fce6-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="1fce6-117">Die Attribute der **msdata:Relationship-Anmerkung** identifizieren die Elemente, die an der Eltern-Kind-Beziehung beteiligt sind, sowie die Elemente und Attribute des **übergeordneten Schlüssels** und des **untergeordneten Schlüssels** und attribute, die an der Beziehung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="1fce6-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="1fce6-118">Der Zuordnungsprozess verwendet diese Informationen, um Tabellen im **DataSet** zu generieren und die Primärschlüssel-/Fremdschlüsselbeziehung zwischen diesen Tabellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1fce6-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="1fce6-119">Das folgende Schemafragment gibt z. B. **Order-** und **OrderDetail-Elemente** auf derselben Ebene (nicht geschachtelt) an.</span><span class="sxs-lookup"><span data-stu-id="1fce6-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="1fce6-120">Das Schema gibt eine **msdata:Relationship-Anmerkung** an, die die Parent-Child-Beziehung zwischen diesen beiden Elementen angibt.</span><span class="sxs-lookup"><span data-stu-id="1fce6-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="1fce6-121">In diesem Fall muss eine explizite Beziehung mithilfe der **msdata:Relationship-Anmerkung** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1fce6-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="1fce6-122">Der Zuordnungsprozess verwendet das Relationship-Element, um eine Parent-Child-Beziehung zwischen der **OrderNumber-Spalte** in der **Tabelle Order** und der **OrderNo-Spalte** in der **Tabelle OrderDetail** im **DataSet**zu erstellen. **Relationship**</span><span class="sxs-lookup"><span data-stu-id="1fce6-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="1fce6-123">Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.</span><span class="sxs-lookup"><span data-stu-id="1fce6-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="1fce6-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1fce6-124">In This Section</span></span>  
 [<span data-ttu-id="1fce6-125">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="1fce6-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="1fce6-126">Beschreibt die Einschränkungen und Beziehungen, die implizit in einem **DataSet** erstellt werden, wenn verschachtelte Elemente im XML-Schema gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1fce6-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="1fce6-127">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="1fce6-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="1fce6-128">Beschreibt, wie Beziehungen in einem **DataSet** für geschachtelte Elemente im XML-Schema explizit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1fce6-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="1fce6-129">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="1fce6-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="1fce6-130">Beschreibt, wie Beziehungen in einem **DataSet** zwischen XML-Schemaelementen erstellt werden, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="1fce6-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="1fce6-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1fce6-131">Related Sections</span></span>  
 [<span data-ttu-id="1fce6-132">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1fce6-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="1fce6-133">Beschreibt die relationale Struktur oder das Schema eines **DataSets,** das aus dem Xml Schema der Schemadefinitionssprache (XSD) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1fce6-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="1fce6-134">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1fce6-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="1fce6-135">Beschreibt die XML-Schemaelemente, die zum Erstellen eindeutiger und Fremdschlüsseleinschränkungen in einem **DataSet**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1fce6-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fce6-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1fce6-136">See also</span></span>

- [<span data-ttu-id="1fce6-137">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1fce6-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
