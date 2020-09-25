---
title: XML-Schemaeinschränkungen und -beziehungen
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 5861386e42defa189aaa50a3af0bd95d7e9257fd
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173704"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="76040-102">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="76040-102">XML Schema Constraints and Relationships</span></span>

<span data-ttu-id="76040-103">In einem XSD-Schema (XML Schema Definition Language) können Sie Einschränkungen (Unique-, Key-und keyref-Einschränkungen) und Beziehungen (mithilfe der **msdata: Relationship** -Anmerkung) angeben.</span><span class="sxs-lookup"><span data-stu-id="76040-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="76040-104">In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="76040-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="76040-105">Im Allgemeinen geben Sie in einem XML-Schema die **msdata: Relationship** -Anmerkung an, wenn Sie nur Beziehungen im **DataSet**generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76040-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="76040-106">Weitere Informationen finden Sie unter [Erstellen von DataSet-Beziehungen aus dem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="76040-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="76040-107">Sie geben Einschränkungen (Unique, Key und keyref) an, wenn Sie Einschränkungen im **DataSet**generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="76040-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="76040-108">Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="76040-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="76040-109">Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="76040-109">Generating a Relationship from key and keyref Constraints</span></span>  

 <span data-ttu-id="76040-110">Anstatt die **msdata: Relationship** -Anmerkung anzugeben, können Sie Schlüssel-und keyref-Einschränkungen angeben, die während der XML-Schema Zuordnung verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung im **DataSet**zu generieren.</span><span class="sxs-lookup"><span data-stu-id="76040-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="76040-111">Wenn Sie jedoch `msdata:ConstraintOnly="true"` im **keyref** -Element angeben, enthält das **DataSet** nur die Einschränkungen und schließt die Beziehung nicht ein.</span><span class="sxs-lookup"><span data-stu-id="76040-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="76040-112">Im folgenden Beispiel wird ein XML-Schema dargestellt, das die Elemente **Order** und **OrderDetail** enthält, die nicht in einem scht sind.</span><span class="sxs-lookup"><span data-stu-id="76040-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="76040-113">In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="76040-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="76040-114">Das **DataSet** , das während der XML-Schema Zuordnung generiert wird, umfasst die Tabellen **Order** und **Order Detail** .</span><span class="sxs-lookup"><span data-stu-id="76040-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="76040-115">Außerdem enthält das **DataSet** Beziehungen und Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="76040-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="76040-116">Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76040-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="76040-117">Beachten Sie, dass das Schema die **msdata: Relationship** -Anmerkung nicht angibt. Stattdessen werden die Schlüssel-und keyref-Einschränkungen verwendet, um die Beziehung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="76040-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
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
  
 <span data-ttu-id="76040-118">Im vorherigen Schema Beispiel sind das **Order** -Element und das **Order Detail** -Element nicht scht.</span><span class="sxs-lookup"><span data-stu-id="76040-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="76040-119">Im folgenden Schemabeispiel sind diese Elemente geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="76040-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="76040-120">Es ist jedoch keine **msdata: Relationship** -Anmerkung angegeben. Daher wird von einer impliziten Beziehung ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="76040-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="76040-121">Weitere Informationen finden Sie unterzuordnen [von impliziten Beziehungen zwischen schsted Schema-Elementen](map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="76040-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="76040-122">In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.</span><span class="sxs-lookup"><span data-stu-id="76040-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="76040-123">Das **DataSet** , das sich aus dem XML-Schema Mapping-Prozess ergibt, umfasst zwei Tabellen:</span><span class="sxs-lookup"><span data-stu-id="76040-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="76040-124">Das **DataSet** enthält auch die beiden Beziehungen (eines basierend auf der **msdata: Relationship** -Anmerkung und das andere auf der Grundlage der Schlüssel-und keyref-Einschränkungen) und verschiedene Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="76040-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="76040-125">Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="76040-125">The following example shows the relations and constraints.</span></span>  
  
```text
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
  
 <span data-ttu-id="76040-126">Wenn eine Keyref-Einschränkung, die auf eine in einer Tabelle basierende Tabelle verweist, die Anmerkung **msdata: isnetsted = "true"** enthält, erstellt das **DataSet** eine einzelne, auf der Keyref-Einschränkung basierende Beziehung, die auf der Keyref-Einschränkung und der zugehörigen Unique/Key-Einschränkung basiert.</span><span class="sxs-lookup"><span data-stu-id="76040-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76040-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76040-127">See also</span></span>

- [<span data-ttu-id="76040-128">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="76040-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="76040-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="76040-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
