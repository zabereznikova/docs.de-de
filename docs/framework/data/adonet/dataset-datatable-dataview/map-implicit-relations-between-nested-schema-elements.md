---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 076e3ec6e5a00fd294fa3c6d7998cfab3a136240
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182070"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind. In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:  
  
-   Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).  
  
-   Wenn keine unique-Einschränkung für das übergeordnete Element vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *TableName*_Id, in denen *TableName* ist der Name der übergeordneten Tabelle.  
  
-   Eine primary Key-Einschränkung für die übergeordnete Tabelle, die zusätzliche Spalte als Primärschlüssel identifiziert (durch Festlegen der **IsPrimaryKey** Eigenschaft **"true"**). Die Einschränkung wird mit "Constraint\#" benannt, wobei \# für 1, 2, 3 usw. steht. Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".  
  
-   Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert. Die Einschränkung wird mit dem Namen *Übergeordnetetabelle_untergeordnetetabelle* , in denen *ParentTable* ist der Name der übergeordneten Tabelle und *untergeordneteTabelle* ist der Name der untergeordneten Tabelle.  
  
-   Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.  
  
 Das folgende Beispiel zeigt ein Schema, in denen **OrderDetail** ist ein untergeordnetes Element des **Reihenfolge**.  
  
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
  
 Die XML-Schemazuordnungsprozess erstellt die folgenden in das **DataSet**:  
  
-   Ein **Reihenfolge** und **OrderDetail** Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Eine eindeutige Einschränkung für die **Reihenfolge** Tabelle. Beachten Sie, dass die **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.  
  
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
  
-   Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen. Die **geschachtelte** für diese Beziehung-Eigenschaftensatz auf **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .  
  
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

- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
