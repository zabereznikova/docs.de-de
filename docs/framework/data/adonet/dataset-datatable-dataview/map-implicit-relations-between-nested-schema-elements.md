---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 1bce0c2815ac94787055794942807777232df295
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind. In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:  
  
-   Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).  
  
-   Wenn keine unique-Einschränkung auf das übergeordnete Element vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *TableName*_Id, in denen *TableName* ist der Name der übergeordneten Tabelle.  
  
-   Eine primary Key-Einschränkung für die übergeordnete Tabelle, die zusätzliche Spalte als Primärschlüssel identifiziert (durch Festlegen der **IsPrimaryKey** Eigenschaft **"true"**). Die Einschränkung wird die Einschränkung benannt*#* , in denen *#* ist 1, 2, 3 und So weiter. Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".  
  
-   Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert. Die Einschränkung wird mit dem Namen *Übergeordnetetabelle_untergeordnetetabelle* , in denen *ParentTable* ist der Name der übergeordneten Tabelle und *untergeordneteTabelle* ist der Name der untergeordneten Tabelle.  
  
-   Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.  
  
 Das folgende Beispiel zeigt ein Schema, in dem **OrderDetail** ist ein untergeordnetes Element des **Reihenfolge**.  
  
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
  
 Die XML-Schemazuordnungsprozess erstellt folgende Elemente in der **DataSet**:  
  
-   Ein **Reihenfolge** und ein **OrderDetail** Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Eine unique-Einschränkung für die **Reihenfolge** Tabelle. Beachten Sie, dass die **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Eine foreign Key-Einschränkung für die **OrderDetail** Tabelle.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen. Die **geschachtelte** -Eigenschaft für diese Beziehung wird festgelegt, um **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
