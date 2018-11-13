---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 73cd8a83021934de3b8e3bf494a4f59dd32e183c
ms.sourcegitcommit: 5fd80619c760fa8c25d33a6f5661247cb65da465
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2018
ms.locfileid: "50744335"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="4ffe5-102">Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen</span><span class="sxs-lookup"><span data-stu-id="4ffe5-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="4ffe5-103">Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="4ffe5-104">In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:</span><span class="sxs-lookup"><span data-stu-id="4ffe5-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="4ffe5-105">Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).</span><span class="sxs-lookup"><span data-stu-id="4ffe5-105">One table for each of the complex types (parent and child).</span></span>  
  
-   <span data-ttu-id="4ffe5-106">Wenn keine unique-Einschränkung für das übergeordnete Element vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *TableName*_Id, in denen *TableName* ist der Name der übergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
-   <span data-ttu-id="4ffe5-107">Eine primary Key-Einschränkung für die übergeordnete Tabelle, die zusätzliche Spalte als Primärschlüssel identifiziert (durch Festlegen der **IsPrimaryKey** Eigenschaft **"true"**).</span><span class="sxs-lookup"><span data-stu-id="4ffe5-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="4ffe5-108">Die Einschränkung wird mit "Constraint\#" benannt, wobei \# für 1, 2, 3 usw. steht.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="4ffe5-109">Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".</span><span class="sxs-lookup"><span data-stu-id="4ffe5-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
-   <span data-ttu-id="4ffe5-110">Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="4ffe5-111">Die Einschränkung wird mit dem Namen *Übergeordnetetabelle_untergeordnetetabelle* , in denen *ParentTable* ist der Name der übergeordneten Tabelle und *untergeordneteTabelle* ist der Name der untergeordneten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
-   <span data-ttu-id="4ffe5-112">Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="4ffe5-113">Das folgende Beispiel zeigt ein Schema, in denen **OrderDetail** ist ein untergeordnetes Element des **Reihenfolge**.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="4ffe5-114">Die XML-Schemazuordnungsprozess erstellt die folgenden in das **DataSet**:</span><span class="sxs-lookup"><span data-stu-id="4ffe5-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
-   <span data-ttu-id="4ffe5-115">Ein **Reihenfolge** und **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   <span data-ttu-id="4ffe5-116">Eine eindeutige Einschränkung für die **Reihenfolge** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="4ffe5-117">Beachten Sie, dass die **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   <span data-ttu-id="4ffe5-118">Eine foreign Key-Einschränkung für die **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   <span data-ttu-id="4ffe5-119">Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="4ffe5-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="4ffe5-120">Die **geschachtelte** für diese Beziehung-Eigenschaftensatz auf **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .</span><span class="sxs-lookup"><span data-stu-id="4ffe5-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ffe5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ffe5-121">See Also</span></span>  
 [<span data-ttu-id="4ffe5-122">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="4ffe5-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="4ffe5-123">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="4ffe5-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="4ffe5-124">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="4ffe5-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
