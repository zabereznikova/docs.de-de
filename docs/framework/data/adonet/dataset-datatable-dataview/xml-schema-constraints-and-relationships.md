---
title: XML-Schemaeinschränkungen und -beziehungen
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150713"
---
# <a name="xml-schema-constraints-and-relationships"></a>XML-Schemaeinschränkungen und -beziehungen
In einem XML-Schema für die Schemadefinitionssprache (XSD) können Sie Einschränkungen (eindeutige, Schlüssel- und Keyref-Einschränkungen) und Beziehungen (mit der **msdata:Relationship-Anmerkung)** angeben. In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.  
  
 Im Allgemeinen geben Sie in einem XML-Schema die **msdata:Relationship-Anmerkung** an, wenn Sie nur Beziehungen im **DataSet**generieren möchten. Weitere Informationen finden Sie unter [Generieren von DataSet-Beziehungen aus XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Sie geben Einschränkungen (eindeutig, Schlüssel und Keyref) an, wenn Sie Einschränkungen im **DataSet**generieren möchten. Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen  
 Anstatt die **msdata:Relationship-Anmerkung** anzugeben, können Sie Schlüssel- und Keyref-Einschränkungen angeben, die während des XML-Schemazuordnungsprozesses verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung im **DataSet**zu generieren. Wenn Sie jedoch `msdata:ConstraintOnly="true"` im **keyref-Element** angeben, enthält das **DataSet** nur die Einschränkungen und die Beziehung nicht.  
  
 Das folgende Beispiel zeigt ein XML-Schema, das **Order-** und **OrderDetail-Elemente** enthält, die nicht verschachtelt sind. In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Das **DataSet,** das während des XML-Schemazuordnungsprozesses generiert wird, enthält die Tabellen **Order** und **OrderDetail.** Darüber hinaus enthält das **DataSet** Beziehungen und Einschränkungen. Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt. Beachten Sie, dass das Schema nicht die **msdata:Relationship-Anmerkung** angibt. Stattdessen werden die Schlüssel- und Keyref-Einschränkungen verwendet, um die Beziehung zu generieren.  
  
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
  
 Im vorherigen Schemabeispiel sind die Elemente **Order** und **OrderDetail** nicht geschachtelt. Im folgenden Schemabeispiel sind diese Elemente geschachtelt. Es wird jedoch keine **msdata:Relationship-Anmerkung** angegeben. daher wird eine implizite Beziehung angenommen. Weitere Informationen finden Sie unter [Zuordnen impliziter Beziehungen zwischen verschachtelten Schemaelementen](map-implicit-relations-between-nested-schema-elements.md). In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Das **DataSet,** das sich aus dem XML-Schemazuordnungsprozess ergibt, enthält zwei Tabellen:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Das **DataSet** enthält auch die beiden Beziehungen (eine basierend auf der **msdata:relationship-Anmerkung** und die andere basierend auf den Schlüssel- und Keyref-Einschränkungen) und verschiedene Einschränkungen. Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.  
  
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
  
 Wenn eine keyref-Einschränkung, die sich auf eine geschachtelte Tabelle bezieht, die Anmerkung **msdata:IsNested="true"** enthält, erstellt das **DataSet** eine einzelne geschachtelte Beziehung, die auf der keyref-Einschränkung und der zugehörigen Eindeutigkeits-/Schlüsseleinschränkung basiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
