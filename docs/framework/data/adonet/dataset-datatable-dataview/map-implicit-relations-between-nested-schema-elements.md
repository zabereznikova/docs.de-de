---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 32f8bf67242143098717b47c3b7aa175317ba274
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201316"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen

Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind. In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:  
  
- Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).  
  
- Wenn für das übergeordnete Element keine UNIQUE-Einschränkung vorhanden ist, wird eine zusätzliche Primärschlüssel Spalte pro Tabellendefinition mit dem Namen *TableName*_id, wobei *TableName* der Name der übergeordneten Tabelle ist.  
  
- Eine PRIMARY KEY-Einschränkung für die übergeordnete Tabelle, die die zusätzliche Spalte als Primärschlüssel identifiziert (indem die **IsPrimaryKey** -Eigenschaft auf **true**festgelegt wird). Die Einschränkung wird mit "Constraint\#" benannt, wobei \# für 1, 2, 3 usw. steht. Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".  
  
- Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert. Die Einschränkung hat den Namen *ParentTable_ChildTable* , wobei " *centtable* " der Name der übergeordneten Tabelle und " *ChildTable* " der Name der untergeordneten Tabelle ist.  
  
- Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.  
  
 Das folgende Beispiel zeigt ein Schema, bei dem **OrderDetail** ein untergeordnetes Element der **Reihenfolge**ist.  
  
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
  
 Der Prozess für die XML-Schema Zuordnung erstellt Folgendes im **DataSet**:  
  
- Eine **Bestellung** und eine **Order Detail** -Tabelle.  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Eine Unique-Einschränkung für die **Order** -Tabelle. Beachten Sie, dass die **IsPrimaryKey** -Eigenschaft auf **true**festgelegt ist.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- Eine FOREIGN KEY-Einschränkung für die **Order Detail** -Tabelle.  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle. Die Eigenschaft " **schsted** " für diese Beziehung wird auf " **true** " festgelegt, da die Elemente **Order** und **Order Detail** im Schema scht sind.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
