---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: e9ea85db98a577991e06e0239a0738a2ca5bada6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203484"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="fba0c-102">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="fba0c-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="fba0c-103">Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="fba0c-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="fba0c-104">In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="fba0c-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="fba0c-105">Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).</span><span class="sxs-lookup"><span data-stu-id="fba0c-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="fba0c-106">Wenn für das übergeordnete Element keine UNIQUE-Einschränkung vorhanden ist, eine zusätzliche Primärschlüssel Spalte pro Tabellendefinition mit dem Namen *TableName*_id, wobei *TableName* der Name der übergeordneten Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="fba0c-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="fba0c-107">Eine PRIMARY KEY-Einschränkung für die übergeordnete Tabelle, die die zusätzliche Spalte als Primärschlüssel identifiziert (indem die **IsPrimaryKey** -Eigenschaft auf **true**festgelegt wird).</span><span class="sxs-lookup"><span data-stu-id="fba0c-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="fba0c-108">Die Einschränkung wird mit "Constraint\#" benannt, wobei \# für 1, 2, 3 usw. steht.</span><span class="sxs-lookup"><span data-stu-id="fba0c-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="fba0c-109">Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".</span><span class="sxs-lookup"><span data-stu-id="fba0c-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="fba0c-110">Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fba0c-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="fba0c-111">Die Einschränkung hat den Namen *ParentTable_ChildTable* , wobei " *centtable* " der Name der übergeordneten Tabelle und " *ChildTable* " der Name der untergeordneten Tabelle ist.</span><span class="sxs-lookup"><span data-stu-id="fba0c-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="fba0c-112">Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="fba0c-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="fba0c-113">Das folgende Beispiel zeigt ein Schema, bei dem **OrderDetail** ein untergeordnetes Element der **Reihenfolge**ist.</span><span class="sxs-lookup"><span data-stu-id="fba0c-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="fba0c-114">Der Prozess für die XML-Schema Zuordnung erstellt Folgendes im **DataSet**:</span><span class="sxs-lookup"><span data-stu-id="fba0c-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="fba0c-115">Eine **Bestellung** und eine **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fba0c-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="fba0c-116">Eine Unique-Einschränkung für die **Order** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fba0c-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="fba0c-117">Beachten Sie, dass die **IsPrimaryKey** -Eigenschaft auf **true**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fba0c-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="fba0c-118">Eine FOREIGN KEY-Einschränkung für die **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fba0c-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- <span data-ttu-id="fba0c-119">Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fba0c-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="fba0c-120">Die Eigenschaft "schsted" für diese Beziehung wird auf " **true** " festgelegt, da die Elemente **Order** und **Order Detail** im Schema scht sind.</span><span class="sxs-lookup"><span data-stu-id="fba0c-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fba0c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fba0c-121">See also</span></span>

- [<span data-ttu-id="fba0c-122">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="fba0c-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="fba0c-123">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="fba0c-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="fba0c-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fba0c-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
