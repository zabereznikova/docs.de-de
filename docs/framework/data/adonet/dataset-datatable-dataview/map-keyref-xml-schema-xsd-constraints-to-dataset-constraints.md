---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: dcb295aef6d93222e682ef7f720c83963036e795
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607489"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="7cf53-102">Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7cf53-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="7cf53-103">Die **Keyref** -Element können Sie zum Herstellen von Links zwischen Elementen in einem Dokument.</span><span class="sxs-lookup"><span data-stu-id="7cf53-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="7cf53-104">Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="7cf53-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="7cf53-105">Wenn ein Schema gibt an, die **Keyref** Element und das Element wird konvertiert, während die Schemazuordnungsprozesses in eine entsprechende fremdschlüsseleinschränkung für die Spalten in den Tabellen der der <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="7cf53-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7cf53-106">In der Standardeinstellung die **Keyref** Element generiert, sondern eine Relation auch mit der **ParentTable**, **untergeordneteTabelle**, **ParentColumn**, und  **ChildColumn** Eigenschaften der Beziehung angegeben.</span><span class="sxs-lookup"><span data-stu-id="7cf53-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="7cf53-107">Der folgenden Tabelle werden die **Msdata** Attribute Sie, in angeben können der **Keyref** Element.</span><span class="sxs-lookup"><span data-stu-id="7cf53-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="7cf53-108">Attributname</span><span class="sxs-lookup"><span data-stu-id="7cf53-108">Attribute name</span></span>|<span data-ttu-id="7cf53-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7cf53-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7cf53-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="7cf53-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="7cf53-111">Wenn **ConstraintOnly = "true"** angegeben ist, auf die **Keyref** Elements im Schema, eine Einschränkung wird erstellt, aber keine Beziehung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7cf53-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="7cf53-112">Wenn dieses Attribut nicht angegeben ist (oder **"false"**), werden sowohl die Einschränkung und die Beziehung erstellt, der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="7cf53-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="7cf53-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="7cf53-114">Wenn die **ConstraintName** -Attribut angegeben ist, deren Wert als den Namen der Einschränkung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7cf53-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="7cf53-115">Andernfalls die **Name** Attribut des der **Keyref** Elements im Schema enthält den Namen der Einschränkung in der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="7cf53-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="7cf53-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="7cf53-117">Wenn die **UpdateRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **UpdateRule** -Einschränkungseigenschaft im der  **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7cf53-118">Andernfalls die **UpdateRule** -Eigenschaftensatz auf **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7cf53-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="7cf53-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="7cf53-120">Wenn die **DeleteRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **DeleteRule** -Einschränkungseigenschaft im der  **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7cf53-121">Andernfalls die **DeleteRule** -Eigenschaftensatz auf **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7cf53-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="7cf53-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="7cf53-123">Wenn die **AcceptRejectRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **AcceptRejectRule** -Einschränkungseigenschaft im der  **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7cf53-124">Andernfalls die **AcceptRejectRule** -Eigenschaftensatz auf **keine**.</span><span class="sxs-lookup"><span data-stu-id="7cf53-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="7cf53-125">Das folgende Beispiel enthält ein Schema, der angibt, die **Schlüssel** und **Keyref** Beziehungen zwischen den **OrderNumber** untergeordnetes Element von der **Reihenfolge**  Element und die **OrderNo** untergeordnetes Element von der **OrderDetail** Element.</span><span class="sxs-lookup"><span data-stu-id="7cf53-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="7cf53-126">Im Beispiel die **OrderNumber** untergeordnetes Element von der **OrderDetail** Element bezieht sich auf die **OrderNo** untergeordnete Element des der **Reihenfolge**Element.</span><span class="sxs-lookup"><span data-stu-id="7cf53-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="7cf53-127">Der XML-Schema Definition Language (XSD)-Schemazuordnungsprozess werden die folgenden **DataSet** mit zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="7cf53-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="7cf53-128">Darüber hinaus die **DataSet** definiert die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="7cf53-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="7cf53-129">Eine eindeutige Einschränkung für die **Reihenfolge** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf53-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="7cf53-130">Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="7cf53-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="7cf53-131">Die **geschachtelte** -Eigenschaftensatz auf **"false"** , da die zwei Elemente im Schema nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="7cf53-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="7cf53-132">Eine foreign Key-Einschränkung für die **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7cf53-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7cf53-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7cf53-133">See also</span></span>

- [<span data-ttu-id="7cf53-134">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7cf53-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="7cf53-135">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="7cf53-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="7cf53-136">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7cf53-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
