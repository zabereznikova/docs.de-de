---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 740d45c47f46c311ed703fa11ec86a9739930944
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="43760-102">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="43760-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="43760-103">Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="43760-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="43760-104">In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="43760-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="43760-105">Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).</span><span class="sxs-lookup"><span data-stu-id="43760-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="43760-106">Wenn keine unique-Einschränkung auf das übergeordnete Element vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *TableName*_Id, in denen *TableName* ist der Name der übergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43760-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="43760-107">Eine primary Key-Einschränkung für die übergeordnete Tabelle, die zusätzliche Spalte als Primärschlüssel identifiziert (durch Festlegen der **IsPrimaryKey** Eigenschaft **"true"**).</span><span class="sxs-lookup"><span data-stu-id="43760-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="43760-108">Die Einschränkung wird die Einschränkung benannt *#*  , in denen  *#*  ist 1, 2, 3 und So weiter.</span><span class="sxs-lookup"><span data-stu-id="43760-108">The constraint is named Constraint*#* where *#* is 1, 2, 3, and so on.</span></span> <span data-ttu-id="43760-109">Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".</span><span class="sxs-lookup"><span data-stu-id="43760-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="43760-110">Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert.</span><span class="sxs-lookup"><span data-stu-id="43760-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="43760-111">Die Einschränkung wird mit dem Namen *Übergeordnetetabelle_untergeordnetetabelle* , in denen *ParentTable* ist der Name der übergeordneten Tabelle und *untergeordneteTabelle* ist der Name der untergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43760-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="43760-112">Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="43760-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="43760-113">Das folgende Beispiel zeigt ein Schema, in dem **OrderDetail** ist ein untergeordnetes Element des **Reihenfolge**.</span><span class="sxs-lookup"><span data-stu-id="43760-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="43760-114">Die XML-Schemazuordnungsprozess erstellt folgende Elemente in der **DataSet**:</span><span class="sxs-lookup"><span data-stu-id="43760-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="43760-115">Ein **Reihenfolge** und ein **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43760-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="43760-116">Eine unique-Einschränkung für die **Reihenfolge** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43760-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="43760-117">Beachten Sie, dass die **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="43760-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="43760-118">Eine foreign Key-Einschränkung für die **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="43760-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="43760-119">Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="43760-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="43760-120">Die **geschachtelte** -Eigenschaft für diese Beziehung wird festgelegt, um **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .</span><span class="sxs-lookup"><span data-stu-id="43760-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43760-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43760-121">See Also</span></span>  
 [<span data-ttu-id="43760-122">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="43760-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="43760-123">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="43760-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="43760-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="43760-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
