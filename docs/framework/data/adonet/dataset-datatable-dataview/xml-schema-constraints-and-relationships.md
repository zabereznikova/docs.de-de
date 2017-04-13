---
title: "Einschr&#228;nkungen und Beziehungen in einem XML-Schema | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Einschr&#228;nkungen und Beziehungen in einem XML-Schema
In einem XSD\-Schema \(XML Schema Definition Language\) können Einschränkungen \(eindeutige, Schlüssel\- und keyref\-Einschränkungen\) und Beziehungen \(mithilfe der **msdata:Relationship**\-Anmerkung\) angegeben werden.  In diesem Thema wird erklärt, wie die in einem XML\-Schema angegebenen Einschränkungen und Beziehungen zum Generieren des <xref:System.Data.DataSet> interpretiert werden.  
  
 Im Allgemeinen geben Sie in einem XML\-Schema die **msdata:Relationship**\-Anmerkung an, wenn Sie nur Beziehungen im **DataSet** generieren möchten.  Weitere Informationen finden Sie unter [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).  Geben Sie Einschränkungen \(unique\-, Schlüssel\- und keyref\-Einschränkungen\) an, wenn Sie Einschränkungen im **DataSet** generieren möchten.  Beachten Sie, dass die Schlüsseleinschränkung und die keyref\-Einschränkung auch zum Generieren von Beziehungen verwendet werden. Informationen hierzu erhalten Sie weiter unten in diesem Thema.  
  
## Generieren einer Beziehung aus Schlüsseleinschränkungen und "keyref"\-Einschränkungen  
 Anstelle der **msdata:Relationship**\-Anmerkung können Sie die Schlüsseleinschränkung und die keyref\-Einschränkung angeben. Mithilfe dieser Einschränkungen werden während des XML\-Schemazuordnungsprozesses nicht nur die Einschränkungen, sondern auch die Beziehung im **DataSet** generiert.  Wenn Sie im **keyref**\-Element jedoch `msdata:ConstraintOnly="true"` angeben, schließt das **DataSet** nur die Einschränkungen ein, jedoch nicht die Beziehung.  
  
 Im folgenden Beispiel wird ein XML\-Schema dargestellt, das das **Order**\-Element und das **OrderDetail**\-Element enthält, wobei die Elemente nicht geschachtelt sind.  In dem Schema sind auch die Schlüsseleinschränkung und die keyref\-Einschränkung angegeben.  
  
```  
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
  
 Das während des XML\-Schemazuordnungsprozesses generierte **DataSet** enthält die **Order**\-Tabelle und die **OrderDetail**\-Tabelle.  Außerdem enthält das **DataSet** Beziehungen und Einschränkungen.  Im folgenden Beispiel werden diese Beziehungen und Einschränkungen dargestellt.  Beachten Sie, dass die **msdata:Relationship**\-Anmerkung nicht vom Schema angegeben wird. Stattdessen werden die Schlüsseleinschränkung und die keyref\-Einschränkung zum Generieren der Beziehung verwendet.  
  
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
  
 Im vorherigen Schemabeispiel sind das **Order**\-Element und das **OrderDetail**\-Element nicht geschachtelt.  Im folgenden Schemabeispiel sind diese Elemente geschachtelt.  Die  **msdata:Relationship**\-Anmerkung ist jedoch nicht angegeben. Aus diesem Grund wird von einer impliziten Beziehung ausgegangen.  Weitere Informationen finden Sie unter [Zuordnen von impliziten Beziehungen zwischen im Schema geschachtelten Elementen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).  In dem Schema sind auch die Schlüsseleinschränkung und die keyref\-Einschränkung angegeben.  
  
```  
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
  
 Das aus dem XML\-Schemazuordnungsprozess resultierende **DataSet** enthält die folgenden zwei Tabellen:  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 Das **DataSet** enthält auch die zwei Beziehungen \(eine beruht auf der **msdata:relationship**\-Anmerkung und die andere auf der Schlüsseleinschränkung und der keyref\-Einschränkung\) sowie verschiedene Einschränkungen.  Im folgenden Beispiel werden die Beziehungen und Einschränkungen dargestellt.  
  
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
  
 Wenn eine keyref\-Einschränkung, die auf eine geschachtelte Tabelle verweist, als Anmerkung **msdata:IsNested\="true"** enthält, erstellt das **DataSet** eine einzelne geschachtelte Beziehung, die auf der keyref\-Einschränkung und der entsprechenden unique\-Einschränkung bzw. der Schlüsseleinschränkung beruht.  
  
## Siehe auch  
 [Ableiten einer relationalen 'DataSet'\-Struktur aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)