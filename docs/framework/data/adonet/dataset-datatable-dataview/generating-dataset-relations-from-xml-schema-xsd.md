---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784647"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="3f46e-102">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3f46e-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="3f46e-103">In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f46e-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="3f46e-104">Es gibt drei Möglichkeiten, eine **datasetbeziehung** innerhalb eines XSD-Schemas (XML Schema Definition Language) darzustellen:</span><span class="sxs-lookup"><span data-stu-id="3f46e-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="3f46e-105">Geben Sie geschachtelte komplexe Typen an.</span><span class="sxs-lookup"><span data-stu-id="3f46e-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="3f46e-106">Verwenden Sie die **msdata: Relationship** -Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="3f46e-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="3f46e-107">Geben Sie einen **xs: keyref** ohne die " **msdata: einschränintonly** "-Anmerkung an.</span><span class="sxs-lookup"><span data-stu-id="3f46e-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="3f46e-108">Geschachtelte komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="3f46e-108">Nested Complex Types</span></span>  
 <span data-ttu-id="3f46e-109">Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an.</span><span class="sxs-lookup"><span data-stu-id="3f46e-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="3f46e-110">Das folgende XML-Schema Fragment zeigt, dass **OrderDetail** ein untergeordnetes Element des **Order** -Elements ist.</span><span class="sxs-lookup"><span data-stu-id="3f46e-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="3f46e-111">Der Prozess für die XML-Schema Zuordnung erstellt Tabellen im **DataSet** , die den im Schema erstellten komplexen Typen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="3f46e-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="3f46e-112">Außerdem werden zusätzliche Spalten erstellt, die als übergeordnete **-** untergeordnete Spalten für die generierten Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f46e-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="3f46e-113">Beachten Sie, dass **-** diese übergeordneten untergeordneten Spalten Beziehungen angeben. Dies entspricht nicht der Angabe von PRIMARY KEY/FOREIGN KEY-Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="3f46e-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="3f46e-114">Die "msdata:Relationship"-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="3f46e-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="3f46e-115">Mithilfe der **msdata: Relationship** -Anmerkung können Sie explizit Beziehungen zwischen übergeordneten und untergeordneten Elementen zwischen Elementen im Schema angeben, die nicht schzistet sind.</span><span class="sxs-lookup"><span data-stu-id="3f46e-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="3f46e-116">Das folgende Beispiel zeigt die Struktur des **Relationship** -Elements.</span><span class="sxs-lookup"><span data-stu-id="3f46e-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="3f46e-117">Die Attribute der **msdata: Relationship** -Anmerkung identifizieren die Elemente, die an der Beziehung zwischen übergeordneten **und untergeordneten** Elementen beteiligt sind, sowie die Elemente und Attribute von "arkey" und " **childkey** ", die an der Beziehung beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="3f46e-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="3f46e-118">Der Mapping-Prozess verwendet diese Informationen zum Generieren von Tabellen im **DataSet** und zum Erstellen der Primärschlüssel-/Fremdschlüssel Beziehung zwischen diesen Tabellen.</span><span class="sxs-lookup"><span data-stu-id="3f46e-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="3f46e-119">Das folgende Schema Fragment gibt z. b. **Order** -und **Order Detail** -Elemente auf derselben Ebene an (nicht schsted).</span><span class="sxs-lookup"><span data-stu-id="3f46e-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="3f46e-120">Das Schema gibt eine **msdata: Relationship** -Anmerkung an, die die über-/Unterordnungsbeziehung zwischen diesen beiden Elementen angibt.</span><span class="sxs-lookup"><span data-stu-id="3f46e-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="3f46e-121">In diesem Fall muss mithilfe der **msdata: Relationship** -Anmerkung eine explizite Beziehung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f46e-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="3f46e-122">Der Mapping-Prozess verwendet das **Relationship** -Element, um eine über-/Unterordnungsbeziehung zwischen der **OrderNumber** -Spalte in der **Order** -Tabelle und der **OrderNo** -Spalte in der **Order Detail** -Tabelle des **DataSets**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3f46e-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="3f46e-123">Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.</span><span class="sxs-lookup"><span data-stu-id="3f46e-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="3f46e-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3f46e-124">In This Section</span></span>  
 [<span data-ttu-id="3f46e-125">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="3f46e-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="3f46e-126">Beschreibt die Einschränkungen und Beziehungen, die implizit in einem **DataSet** erstellt werden, wenn in einem XML-Schema schsted Elemente gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="3f46e-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="3f46e-127">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="3f46e-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="3f46e-128">Beschreibt, wie Beziehungen in einem **DataSet** für in einem XML-Schema eingested Elemente explizit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3f46e-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="3f46e-129">Angeben von Beziehungen zwischen Elementen ohne Schachtelung</span><span class="sxs-lookup"><span data-stu-id="3f46e-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="3f46e-130">Beschreibt, wie Beziehungen in einem **DataSet** zwischen XML-Schema Elementen erstellt werden, die nicht scht sind.</span><span class="sxs-lookup"><span data-stu-id="3f46e-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="3f46e-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="3f46e-131">Related Sections</span></span>  
 [<span data-ttu-id="3f46e-132">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3f46e-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="3f46e-133">Beschreibt die relationale Struktur bzw. das Schema eines **DataSets** , das aus einem XSD-Schema (XML Schema Definition Language) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3f46e-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="3f46e-134">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3f46e-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="3f46e-135">Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und FOREIGN KEY-Einschränkungen in einem **DataSet**verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3f46e-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f46e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f46e-136">See also</span></span>

- [<span data-ttu-id="3f46e-137">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3f46e-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
