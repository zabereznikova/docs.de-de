---
title: XML-Schemaeinschränkungen und -beziehungen
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 990ae2eef8d9fbd28472494c989ae9ecca34251d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119781"
---
# <a name="xml-schema-constraints-and-relationships"></a>XML-Schemaeinschränkungen und -beziehungen
In eine XML-Schema (XSD Schema Definition Language), können Sie Einschränkungen festlegen (eindeutig, Schlüssel und die Keyref-Einschränkungen) und Beziehungen (mithilfe der **msdata: Relationship** Anmerkung). In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.  
  
 Im Allgemeinen in eine XML-Schema, geben Sie die **msdata: Relationship** Anmerkung, wenn Sie nur Beziehungen im generieren möchten die **DataSet**. Weitere Informationen finden Sie unter [Generieren von DataSet-Beziehungen aus XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md). Angeben von Einschränkungen (eindeutige, Schlüssel- und Keyref), wenn Sie Einschränkungen in generieren möchten die **DataSet**. Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen  
 Anstatt die **msdata: Relationship** Anmerkung, können Sie angeben, Schlüssel- und Keyref-Einschränkungen, die während des XML-Schemazuordnungsprozesses verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung in der zugenerieren. **DataSet**. Allerdings bei Angabe von `msdata:ConstraintOnly="true"` in die **Keyref** -Element, die **DataSet** enthält nur die Einschränkungen und nicht die Beziehung enthält.  
  
 Das folgende Beispiel zeigt ein XML-Schema, das enthält **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt sind. In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Die **DataSet** generiert, die während des XML-Schemazuordnungsprozess enthält die **Reihenfolge** und **OrderDetail** Tabellen. Darüber hinaus die **DataSet** enthält Beziehungen und Einschränkungen. Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt. Beachten Sie, die nicht vom Schema angegeben ist die **msdata: Relationship** Anmerkung; stattdessen werden die schlüsseleinschränkung und die Keyref-Einschränkungen zum Generieren der Beziehung verwendet.  
  
```  
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
  
 In der vorherigen Schemabeispiel sind das **Reihenfolge** und **OrderDetail** Elemente nicht geschachtelt sind. Im folgenden Schemabeispiel sind diese Elemente geschachtelt. Allerdings keine **msdata: Relationship** -Anmerkung; aus diesem Grund wird eine implizite Beziehung ausgegangen. Weitere Informationen finden Sie unter [Zuordnung impliziten Beziehungen zwischen geschachtelten Schemaelementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md). In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Die **DataSet** aus der XML-Schemazuordnungsprozess resultierende enthält zwei Tabellen:  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Die **DataSet** enthält auch die beiden Beziehungen (einer basierend auf den **msdata: Relationship** -Anmerkung und die andere basierend auf den Schlüssel und die Keyref-Einschränkungen) sowie verschiedene Einschränkungen. Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.  
  
```  
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
  
 Wenn eine Keyref-Einschränkung verweist auf eine geschachtelte Tabelle enthält die **msdata: IsNested = "true"** Anmerkung, die **DataSet** erstellt eine einzelne geschachtelte Beziehung, die basierend auf der Keyref-Einschränkung und die im Zusammenhang mit eindeutigen/Key-Einschränkung.  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
