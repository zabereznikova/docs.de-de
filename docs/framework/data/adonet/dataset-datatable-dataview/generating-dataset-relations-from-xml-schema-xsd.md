---
title: Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: b74c992c4569512a8692b70663002fd609d3501e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546138"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="b4d1e-102">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="b4d1e-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="b4d1e-103">In einem <xref:System.Data.DataSet> können Sie eine Verknüpfung zwischen zwei oder mehreren Spalten erstellen, indem Sie eine Beziehung zwischen übergeordneten und untergeordneten Elementen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="b4d1e-104">Es gibt drei Möglichkeiten zur Darstellung einer **DataSet** Beziehung in ein Schema für XML Schema Definition Language (XSD):</span><span class="sxs-lookup"><span data-stu-id="b4d1e-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
-   <span data-ttu-id="b4d1e-105">Geben Sie geschachtelte komplexe Typen an.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-105">Specify nested complex types.</span></span>  
  
-   <span data-ttu-id="b4d1e-106">Verwenden der **msdata: Relationship** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-106">Use the **msdata:Relationship** annotation.</span></span>  
  
-   <span data-ttu-id="b4d1e-107">Geben Sie eine **xs: keyref** ohne die **msdata: ConstraintOnly** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="b4d1e-108">Geschachtelte komplexe Typen</span><span class="sxs-lookup"><span data-stu-id="b4d1e-108">Nested Complex Types</span></span>  
 <span data-ttu-id="b4d1e-109">Geschachtelte komplexe Typdefinitionen in einem Schema geben die Beziehungen zwischen übergeordneten und untergeordneten Elementen an.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="b4d1e-110">Das folgende XML-Schema-Fragment zeigt, dass **OrderDetail** ist ein untergeordnetes Element von der **Reihenfolge** Element.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="b4d1e-111">Die XML-Schemazuordnungsprozess erstellt Tabellen in der **DataSet** , die den geschachtelten komplexen Typen im Schema entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="b4d1e-112">Er erstellt ebenfalls zusätzliche Spalten, die als übergeordnetes Element verwendet werden**-** untergeordnete Spalten für die generierten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="b4d1e-113">Beachten Sie, die diese übergeordneten**-** untergeordneten Spalten Beziehungen, das ist nicht derselbe, als wenn primary Key/foreign Key-Einschränkungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="b4d1e-114">Die "msdata:Relationship"-Anmerkung</span><span class="sxs-lookup"><span data-stu-id="b4d1e-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="b4d1e-115">Die **msdata: Relationship** -Anmerkung können Sie explizit die über-/ unterordnungsbeziehung zwischen den Elementen im Schema angeben, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="b4d1e-116">Das folgende Beispiel zeigt die Struktur der **Beziehung** Element.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="b4d1e-117">Die Attribute der **msdata: Relationship** Anmerkung zu identifizieren, die Elemente für die über-/ unterordnungsbeziehung ist, werden auch als die **Parentkey** und **Childkey** Elemente und Attribute der Beziehung beteiligt.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="b4d1e-118">Der Zuordnungsprozess verwendet diese Informationen zum Generieren von Tabellen in der **DataSet** und die primary Key/Fremdschlüssel-Beziehung zwischen diesen Tabellen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="b4d1e-119">Das folgende Schemafragment gibt z. B. **Reihenfolge** und **OrderDetail** Elemente auf derselben Ebene (nicht geschachtelt).</span><span class="sxs-lookup"><span data-stu-id="b4d1e-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="b4d1e-120">Das Schema gibt ein **msdata: Relationship** Anmerkung, die angibt, die über-/ unterordnungsbeziehung zwischen diesen beiden Elementen.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="b4d1e-121">In diesem Fall eine explizite Beziehung angegeben werden mithilfe der **msdata: Relationship** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="b4d1e-122">Der Zuordnungsprozess verwendet die **Beziehung** Element zum Erstellen einer über-/ unterordnungsbeziehung zwischen den **OrderNumber** -Spalte in der **Reihenfolge** Tabelle und die **OrderNo** -Spalte in der **OrderDetail** -Tabelle in der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="b4d1e-123">Der Zuordnungsprozess gibt nur die Beziehung an. Einschränkungen für die Werte in diesen Spalten werden nicht wie bei den Primärschlüssel- und Fremdschlüsseleinschränkungen in relationalen Datenbanken automatisch angegeben.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="b4d1e-124">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b4d1e-124">In This Section</span></span>  
 [<span data-ttu-id="b4d1e-125">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="b4d1e-125">Map Implicit Relations Between Nested Schema Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="b4d1e-126">Beschreibt die Einschränkungen und Beziehungen, die implizit in erstellt werden ein **DataSet** Wenn geschachtelte Elemente im XML-Schema gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="b4d1e-127">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="b4d1e-127">Map Relations Specified for Nested Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="b4d1e-128">Beschreibt, wie Sie das explizite Festlegen von Beziehungen einem **DataSet** für geschachtelte Elemente im XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="b4d1e-129">Angeben von Beziehungen zwischen Elementen ohne Schachtelung</span><span class="sxs-lookup"><span data-stu-id="b4d1e-129">Specify Relations Between Elements with No Nesting</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="b4d1e-130">Beschreibt das Erstellen von Beziehungen in einem **DataSet** zwischen XML-Schema-Elemente, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="b4d1e-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b4d1e-131">Related Sections</span></span>  
 [<span data-ttu-id="b4d1e-132">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="b4d1e-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="b4d1e-133">Beschreibt die relationale Struktur bzw. das Schema, der eine **DataSet** , die vom Schema der XML Schema Definition Language (XSD) erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="b4d1e-134">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="b4d1e-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="b4d1e-135">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Unique- und foreign Key-Einschränkungen in einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="b4d1e-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d1e-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4d1e-136">See also</span></span>
- [<span data-ttu-id="b4d1e-137">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="b4d1e-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
