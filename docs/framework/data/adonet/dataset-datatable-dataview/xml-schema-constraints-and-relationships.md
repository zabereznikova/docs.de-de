---
title: "XML-Schemaeinschränkungen und -beziehungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e450954e4b0e51057e98dd329fe26c38f0ebbb05
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="11db5-102">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="11db5-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="11db5-103">In einem Schema Definition Language (XSD) XML-Schema können Sie Einschränkungen festlegen (eindeutig, Schlüssel und der Keyref-Einschränkungen) und Beziehungen (mithilfe der **msdata: Relationship** Anmerkung).</span><span class="sxs-lookup"><span data-stu-id="11db5-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="11db5-104">In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="11db5-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="11db5-105">Im Allgemeinen in ein XML-Schema, geben Sie die **msdata: Relationship** Anmerkung, wenn Sie nur die Beziehungen in generieren möchten die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="11db5-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="11db5-106">Weitere Informationen finden Sie unter [Generieren von DataSet-Beziehungen aus XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="11db5-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="11db5-107">Angeben von Einschränkungen (eindeutige, Schlüssel- und Keyref) Wenn Sie Einschränkungen in generieren möchten die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="11db5-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="11db5-108">Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="11db5-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="11db5-109">Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11db5-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="11db5-110">Angeben, statt die **msdata: Relationship** Anmerkung, können Sie angeben, Schlüssel- und Keyref-Einschränkungen, die während der XML-Schemazuordnungsprozess verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung in der zugenerieren **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="11db5-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="11db5-111">Jedoch bei Angabe `msdata:ConstraintOnly="true"` in der **Keyref** Element, das **DataSet** enthält nur die Einschränkungen und beziehen keine Beziehung.</span><span class="sxs-lookup"><span data-stu-id="11db5-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="11db5-112">Das folgende Beispiel zeigt ein XML-Schema, das enthält **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="11db5-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="11db5-113">In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="11db5-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="11db5-114">Die **DataSet** wird, während der Zuordnungsprozess enthält XML-Schema generiert die **Reihenfolge** und **OrderDetail** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="11db5-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="11db5-115">Darüber hinaus die **DataSet** enthält Beziehungen und Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="11db5-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="11db5-116">Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="11db5-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="11db5-117">Hinweis, der das Schema nicht der **msdata: Relationship** Anmerkung; stattdessen die Schlüssel- und Keyref-Einschränkungen zum Generieren der Beziehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="11db5-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="11db5-118">Im vorherigen Schemabeispiel sind das **Reihenfolge** und **OrderDetail** Elemente nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="11db5-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="11db5-119">Im folgenden Schemabeispiel sind diese Elemente geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="11db5-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="11db5-120">Allerdings keine **msdata: Relationship** -Anmerkung wird; daher wird eine implizite Beziehung ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="11db5-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="11db5-121">Weitere Informationen finden Sie unter [Zuordnung impliziten Beziehungen zwischen geschachtelten Schemaelementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="11db5-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="11db5-122">In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="11db5-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="11db5-123">Die **DataSet** aus der XML-Schemazuordnungsprozess resultierende enthält zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="11db5-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="11db5-124">Die **DataSet** enthält auch die zwei Beziehungen (eine beruht auf dem **msdata: Relationship** -Anmerkung und die andere basierend auf der Schlüssel- und Keyref-Einschränkung) sowie verschiedene Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="11db5-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="11db5-125">Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="11db5-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="11db5-126">Wenn eine Keyref-Einschränkung verweist auf die geschachtelte Tabelle enthält die **msdata: IsNested = "true"** Anmerkung, die **DataSet** erstellt eine einzelne geschachtelte Beziehung, die basierend auf der Keyref-Einschränkung und die im Zusammenhang mit eindeutigen/Key-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="11db5-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11db5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11db5-127">See Also</span></span>  
 [<span data-ttu-id="11db5-128">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="11db5-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="11db5-129">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="11db5-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
