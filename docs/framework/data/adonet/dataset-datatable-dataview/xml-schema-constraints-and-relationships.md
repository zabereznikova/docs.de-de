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
# <a name="xml-schema-constraints-and-relationships"></a>XML-Schemaeinschränkungen und -beziehungen

In einem XSD-Schema (XML Schema Definition Language) können Sie Einschränkungen (Unique-, Key-und keyref-Einschränkungen) und Beziehungen (mithilfe der **msdata: Relationship** -Anmerkung) angeben. In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.  
  
 Im Allgemeinen geben Sie in einem XML-Schema die **msdata: Relationship** -Anmerkung an, wenn Sie nur Beziehungen im **DataSet**generieren möchten. Weitere Informationen finden Sie unter [Erstellen von DataSet-Beziehungen aus dem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Sie geben Einschränkungen (Unique, Key und keyref) an, wenn Sie Einschränkungen im **DataSet**generieren möchten. Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen  

 Anstatt die **msdata: Relationship** -Anmerkung anzugeben, können Sie Schlüssel-und keyref-Einschränkungen angeben, die während der XML-Schema Zuordnung verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung im **DataSet**zu generieren. Wenn Sie jedoch `msdata:ConstraintOnly="true"` im **keyref** -Element angeben, enthält das **DataSet** nur die Einschränkungen und schließt die Beziehung nicht ein.  
  
 Im folgenden Beispiel wird ein XML-Schema dargestellt, das die Elemente **Order** und **OrderDetail** enthält, die nicht in einem scht sind. In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Das **DataSet** , das während der XML-Schema Zuordnung generiert wird, umfasst die Tabellen **Order** und **Order Detail** . Außerdem enthält das **DataSet** Beziehungen und Einschränkungen. Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt. Beachten Sie, dass das Schema die **msdata: Relationship** -Anmerkung nicht angibt. Stattdessen werden die Schlüssel-und keyref-Einschränkungen verwendet, um die Beziehung zu generieren.  
  
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
  
 Im vorherigen Schema Beispiel sind das **Order** -Element und das **Order Detail** -Element nicht scht. Im folgenden Schemabeispiel sind diese Elemente geschachtelt. Es ist jedoch keine **msdata: Relationship** -Anmerkung angegeben. Daher wird von einer impliziten Beziehung ausgegangen. Weitere Informationen finden Sie unterzuordnen [von impliziten Beziehungen zwischen schsted Schema-Elementen](map-implicit-relations-between-nested-schema-elements.md). In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Das **DataSet** , das sich aus dem XML-Schema Mapping-Prozess ergibt, umfasst zwei Tabellen:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Das **DataSet** enthält auch die beiden Beziehungen (eines basierend auf der **msdata: Relationship** -Anmerkung und das andere auf der Grundlage der Schlüssel-und keyref-Einschränkungen) und verschiedene Einschränkungen. Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.  
  
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
  
 Wenn eine Keyref-Einschränkung, die auf eine in einer Tabelle basierende Tabelle verweist, die Anmerkung **msdata: isnetsted = "true"** enthält, erstellt das **DataSet** eine einzelne, auf der Keyref-Einschränkung basierende Beziehung, die auf der Keyref-Einschränkung und der zugehörigen Unique/Key-Einschränkung basiert.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
