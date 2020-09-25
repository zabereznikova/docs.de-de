---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: fe53232b6818b5bb28b433c4a473b6381b8e9083
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198560"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="1f957-102">Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1f957-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="1f957-103">Das **keyref** -Element ermöglicht es Ihnen, Links zwischen Elementen innerhalb eines Dokuments zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f957-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="1f957-104">Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="1f957-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="1f957-105">Wenn ein Schema das **keyref** -Element angibt, wird das-Element während des Schema Zuordnungsprozesses in eine entsprechende Foreign Key-Einschränkung für die Spalten in den-Tabellen konvertiert <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="1f957-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1f957-106">Standardmäßig generiert das **keyref** -Element auch eine Beziehung, bei der **die Eigenschaften**"parametable", " **ChildTable**", " **para Column**" und " **childColumn** " in der Beziehung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1f957-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="1f957-107">In der folgenden Tabelle werden die **msdata** -Attribute aufgelistet, die Sie im **keyref** -Element angeben können.</span><span class="sxs-lookup"><span data-stu-id="1f957-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="1f957-108">Attributname</span><span class="sxs-lookup"><span data-stu-id="1f957-108">Attribute name</span></span>|<span data-ttu-id="1f957-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1f957-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1f957-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="1f957-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="1f957-111">Wenn für das **keyref** -Element im Schema **"beschränintonly =" true "** angegeben wird, wird eine Einschränkung erstellt, aber es wird keine Beziehung erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f957-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="1f957-112">Wenn dieses Attribut nicht angegeben wird (oder auf **false**festgelegt ist), werden sowohl die-Einschränkung als auch die-Beziehung im **DataSet**erstellt.</span><span class="sxs-lookup"><span data-stu-id="1f957-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="1f957-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="1f957-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="1f957-114">Wenn das Attribut " **Einschränkungs Name** " angegeben wird, wird dessen Wert als Name der Einschränkung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f957-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="1f957-115">Andernfalls stellt das Attribut " **Name** " des **keyref** -Elements im Schema den Einschränkungs Namen im **DataSet**bereit.</span><span class="sxs-lookup"><span data-stu-id="1f957-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="1f957-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="1f957-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="1f957-117">Wenn das **UpdateRule** -Attribut im **keyref** -Element im Schema angegeben wird, wird dessen Wert der **UpdateRule** -Einschränkungs Eigenschaft im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1f957-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="1f957-118">Andernfalls ist die **UpdateRule** -Eigenschaft auf **Cascade**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f957-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="1f957-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="1f957-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="1f957-120">Wenn das **DeleteRule** -Attribut im **keyref** -Element im Schema angegeben wird, wird dessen Wert der **DeleteRule** -Einschränkungs Eigenschaft im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1f957-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="1f957-121">Andernfalls ist die **DeleteRule** -Eigenschaft auf **Cascade**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f957-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="1f957-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="1f957-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="1f957-123">Wenn das Attribut " **Accept trejectrule** " im **keyref** -Element im Schema angegeben wird, wird dessen Wert der Eigenschaft " **Accept trejectrule** " im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1f957-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="1f957-124">Andernfalls ist die Eigenschaft " **akzeptrejectrule** " auf " **None**" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1f957-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="1f957-125">Das folgende Beispiel enthält ein Schema, das die **Key** -Beziehung und die **keyref** -Beziehung zwischen dem untergeordneten **OrderNumber** -Element des **Order** -Elements und dem untergeordneten **OrderNo** -Element des **Order Detail** -Elements angibt.</span><span class="sxs-lookup"><span data-stu-id="1f957-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="1f957-126">Im Beispiel verweist das untergeordnete **OrderNumber** -Element des **Order Detail** -Elements auf das untergeordnete **OrderNo** -Schlüsselelement des **Order** -Elements.</span><span class="sxs-lookup"><span data-stu-id="1f957-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="1f957-127">Der XSD (XML Schema Definition Language)-Schema Mapping-Prozess erzeugt das folgende **DataSet** mit zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="1f957-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="1f957-128">Außerdem definiert das **DataSet** die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="1f957-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="1f957-129">Eine Unique-Einschränkung für die **Order** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1f957-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="1f957-130">Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1f957-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="1f957-131">Die Eigenschaft " **schsted** " ist auf " **false** " festgelegt, da die beiden Elemente nicht im Schema enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1f957-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="1f957-132">Eine FOREIGN KEY-Einschränkung für die **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1f957-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1f957-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1f957-133">See also</span></span>

- [<span data-ttu-id="1f957-134">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1f957-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="1f957-135">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1f957-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="1f957-136">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1f957-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
