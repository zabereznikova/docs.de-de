---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150882"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="6f8f2-102">Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6f8f2-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="6f8f2-103">Mit dem **keyref-Element** können Sie Verknüpfungen zwischen Elementen innerhalb eines Dokuments herstellen.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="6f8f2-104">Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="6f8f2-105">Wenn ein Schema das **keyref-Element** angibt, wird das Element während des Schemazuordnungsprozesses in <xref:System.Data.DataSet>eine entsprechende Fremdschlüsseleinschränkung für die Spalten in den Tabellen der konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6f8f2-106">Standardmäßig generiert das **keyref-Element** auch eine Beziehung mit den Eigenschaften **ParentTable**, **ChildTable**, **ParentColumn**und **ChildColumn,** die für die Beziehung angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="6f8f2-107">In der folgenden Tabelle werden die **msdata-Attribute** beschrieben, die Sie im **keyref-Element** angeben können.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="6f8f2-108">Attributname</span><span class="sxs-lookup"><span data-stu-id="6f8f2-108">Attribute name</span></span>|<span data-ttu-id="6f8f2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f8f2-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6f8f2-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="6f8f2-111">Wenn **ConstraintOnly="true"** für das **keyref-Element** im Schema angegeben ist, wird eine Einschränkung erstellt, aber keine Beziehung wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="6f8f2-112">Wenn dieses Attribut nicht angegeben ist (oder auf **False**festgelegt ist), werden sowohl die Einschränkung als auch die Beziehung im **DataSet**erstellt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="6f8f2-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="6f8f2-114">Wenn das **ConstraintName-Attribut** angegeben wird, wird sein Wert als Name der Einschränkung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="6f8f2-115">Andernfalls stellt das **name-Attribut** des **keyref-Elements** im Schema den Einschränkungsnamen im **DataSet bereit.**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="6f8f2-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="6f8f2-117">Wenn das **UpdateRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **UpdateRule-Einschränkungseigenschaft** im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="6f8f2-118">Andernfalls wird die **UpdateRule-Eigenschaft** auf **Cascade**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="6f8f2-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="6f8f2-120">Wenn das **DeleteRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **DeleteRule-Einschränkungseigenschaft** im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="6f8f2-121">Andernfalls wird die **DeleteRule-Eigenschaft** auf **Cascade**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="6f8f2-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="6f8f2-123">Wenn das **AcceptRejectRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **AcceptRejectRule-Einschränkungseigenschaft** im **DataSet**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="6f8f2-124">Andernfalls wird die **AcceptRejectRule-Eigenschaft** auf **Keine**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="6f8f2-125">Das folgende Beispiel enthält ein Schema, das die **Schlüssel-** und **Keyref-Beziehungen** zwischen dem untergeordneten **OrderNumber-Element** des **Order-Elements** und dem **untergeordneten OrderNo-Element** des **OrderDetail-Elements** angibt.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="6f8f2-126">Im Beispiel verweist das untergeordnete **OrderNumber-Element** des **OrderDetail-Elements** auf das untergeordnete **Schlüsselelement OrderNo** des **Order-Elements.**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="6f8f2-127">Der Xml-Schema-Definitions-Schemazuordnungsprozess (XML Schema Definition Language, XSD) erzeugt das folgende **DataSet** mit zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="6f8f2-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="6f8f2-128">Darüber hinaus definiert das **DataSet** die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="6f8f2-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="6f8f2-129">Eine eindeutige Einschränkung für die **Tabelle "Auftrag".**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="6f8f2-130">Eine Beziehung zwischen den Tabellen **Order** und **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="6f8f2-131">Die **Nested-Eigenschaft** ist auf **False** festgelegt, da die beiden Elemente nicht im Schema verschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="6f8f2-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="6f8f2-132">Eine Fremdschlüsseleinschränkung für die **Tabelle OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="6f8f2-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6f8f2-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f8f2-133">See also</span></span>

- [<span data-ttu-id="6f8f2-134">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="6f8f2-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="6f8f2-135">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="6f8f2-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="6f8f2-136">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6f8f2-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
