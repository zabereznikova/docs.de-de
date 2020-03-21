---
title: Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150962"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Zuordnen von impliziten Beziehungen zwischen geschachtelten Schemaelementen
Ein XSD-Schema (XML Schema Definition Language) kann komplexe Typen aufweisen, die ineinander geschachtelt sind. In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:  
  
- Eine Tabelle für jeden der komplexen Typen (übergeordnet und untergeordnet).  
  
- Wenn keine eindeutige Einschränkung für das übergeordnete Element vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *TableName*_Id wobei *TableName* der Name der übergeordneten Tabelle ist.  
  
- Eine Primärschlüsseleinschränkung für die übergeordnete Tabelle, die die zusätzliche Spalte als Primärschlüssel identifiziert (durch Festlegen der **IsPrimaryKey-Eigenschaft** auf **True**). Die Einschränkung wird mit "Constraint\#" benannt, wobei \# für 1, 2, 3 usw. steht. Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".  
  
- Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert. Die Einschränkung wird *ParentTable_ChildTable* genannt, wobei *ParentTable* der Name der übergeordneten Tabelle und *ChildTable* der Name der untergeordneten Tabelle ist.  
  
- Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.  
  
 Das folgende Beispiel zeigt ein Schema, bei dem **OrderDetail** ein untergeordnetes Element von **Order**ist.  
  
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
  
 Der XML-Schemazuordnungsprozess erstellt Folgendes im **DataSet:**  
  
- Eine **Order-** und **orderDetail-Tabelle.**  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Eine eindeutige Einschränkung für die **Tabelle "Auftrag".** Beachten Sie, dass die **IsPrimaryKey-Eigenschaft** auf **True**festgelegt ist.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- Eine Fremdschlüsseleinschränkung für die **Tabelle OrderDetail.**  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- Eine Beziehung zwischen den Tabellen **Order** und **OrderDetail.** Die **Nested-Eigenschaft** für diese Beziehung wird auf **True** festgelegt, da **die** Order- und **OrderDetail-Elemente** im Schema verschachtelt sind.  
  
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
