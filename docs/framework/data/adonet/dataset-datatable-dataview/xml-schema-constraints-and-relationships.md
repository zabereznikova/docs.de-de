---
title: "XML-Schemaeinschränkungen und -beziehungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e450954e4b0e51057e98dd329fe26c38f0ebbb05
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="xml-schema-constraints-and-relationships"></a>XML-Schemaeinschränkungen und -beziehungen
In einem Schema Definition Language (XSD) XML-Schema können Sie Einschränkungen festlegen (eindeutig, Schlüssel und der Keyref-Einschränkungen) und Beziehungen (mithilfe der **msdata: Relationship** Anmerkung). In diesem Thema wird erklärt, wie die in einem XML-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.  
  
 Im Allgemeinen in ein XML-Schema, geben Sie die **msdata: Relationship** Anmerkung, wenn Sie nur die Beziehungen in generieren möchten die **DataSet**. Weitere Informationen finden Sie unter [Generieren von DataSet-Beziehungen aus XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md). Angeben von Einschränkungen (eindeutige, Schlüssel- und Keyref) Wenn Sie Einschränkungen in generieren möchten die **DataSet**. Beachten Sie, dass die Schlüsseleinschränkung und die keyref-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"-Einschränkungen  
 Angeben, statt die **msdata: Relationship** Anmerkung, können Sie angeben, Schlüssel- und Keyref-Einschränkungen, die während der XML-Schemazuordnungsprozess verwendet werden, um nicht nur die Einschränkungen, sondern auch die Beziehung in der zugenerieren **DataSet**. Jedoch bei Angabe `msdata:ConstraintOnly="true"` in der **Keyref** Element, das **DataSet** enthält nur die Einschränkungen und beziehen keine Beziehung.  
  
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
  
 Die **DataSet** wird, während der Zuordnungsprozess enthält XML-Schema generiert die **Reihenfolge** und **OrderDetail** Tabellen. Darüber hinaus die **DataSet** enthält Beziehungen und Einschränkungen. Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt. Hinweis, der das Schema nicht der **msdata: Relationship** Anmerkung; stattdessen die Schlüssel- und Keyref-Einschränkungen zum Generieren der Beziehung verwendet werden.  
  
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
  
 Im vorherigen Schemabeispiel sind das **Reihenfolge** und **OrderDetail** Elemente nicht geschachtelt sind. Im folgenden Schemabeispiel sind diese Elemente geschachtelt. Allerdings keine **msdata: Relationship** -Anmerkung wird; daher wird eine implizite Beziehung ausgegangen. Weitere Informationen finden Sie unter [Zuordnung impliziten Beziehungen zwischen geschachtelten Schemaelementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md). In dem Schema sind auch die Schlüsseleinschränkung und die keyref-Einschränkung angegeben.  
  
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
  
 Die **DataSet** enthält auch die zwei Beziehungen (eine beruht auf dem **msdata: Relationship** -Anmerkung und die andere basierend auf der Schlüssel- und Keyref-Einschränkung) sowie verschiedene Einschränkungen. Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.  
  
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
  
 Wenn eine Keyref-Einschränkung verweist auf die geschachtelte Tabelle enthält die **msdata: IsNested = "true"** Anmerkung, die **DataSet** erstellt eine einzelne geschachtelte Beziehung, die basierend auf der Keyref-Einschränkung und die im Zusammenhang mit eindeutigen/Key-Einschränkung.  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
