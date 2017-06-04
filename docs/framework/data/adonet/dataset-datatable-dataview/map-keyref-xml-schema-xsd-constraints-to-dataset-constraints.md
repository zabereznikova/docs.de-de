---
title: "Zuordnen von XSD-&#39;keyref&#39;-Schl&#252;sseleinschr&#228;nkungen (XML-Schema) zu DataSet-Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen von XSD-&#39;keyref&#39;-Schl&#252;sseleinschr&#228;nkungen (XML-Schema) zu DataSet-Einschr&#228;nkungen
Mit dem **keyref**\-Element können Sie Links zwischen Elementen innerhalb eines Dokuments erstellen.  Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar.  Wenn ein Schema das **keyref**\-Element angibt, wird das Element während des Schemazuordnungsprozesses in eine entsprechende Fremdschlüsseleinschränkung für die Spalten in der Tabelle des <xref:System.Data.DataSet> konvertiert.  In der Standardeinstellung generiert das **keyref**\-Element außerdem eine Beziehung, wobei die Eigenschaften **ParentTable**, **ChildTable**, **ParentColumn** und **ChildColumn** der Beziehung angegeben werden.  
  
 In der folgenden Tabelle werden die **msdata**\-Attribute aufgelistet, die im **keyref**\-Element angegeben werden können.  
  
|Attributname|Beschreibung|  
|------------------|------------------|  
|**msdata:ConstraintOnly**|Wenn für das **keyref**\-Element im Schema **ConstraintOnly\="true"** angegeben wurde, wird eine Einschränkung, jedoch keine Beziehung erstellt.  Wenn dieses Attribut nicht angegeben wird \(oder auf **False** festgelegt ist\), werden im **DataSet** sowohl die Einschränkung als auch die Beziehung erstellt.|  
|**msdata:ConstraintName**|Wenn das **ConstraintName**\-Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.  Andernfalls stellt das **name**\-Attribut des **keyref**\-Elements im Schema den Einschränkungsnamen im **DataSet** bereit.|  
|**msdata:UpdateRule**|Wenn das **UpdateRule**\-Attribut im **keyref**\-Element im Schema angegeben wurde, wird dessen Wert der **UpdateRule**\-Einschränkungseigenschaft im **DataSet** zugeordnet.  Andernfalls wird die **UpdateRule**\-Eigenschaft auf **Cascade** festgelegt.|  
|**msdata:DeleteRule**|Wenn das **DeleteRule**\-Attribut im **keyref**\-Element im Schema angegeben wurde, wird dessen Wert der **DeleteRule**\-Einschränkungseigenschaft im **DataSet** zugeordnet.  Andernfalls wird die **DeleteRule**\-Eigenschaft auf **Cascade** festgelegt.|  
|**msdata:AcceptRejectRule**|Wenn das **AcceptRejectRule**\-Attribut im **keyref**\-Element im Schema angegeben wurde, wird dessen Wert der **AcceptRejectRule**\-Einschränkungseigenschaft im **DataSet** zugeordnet.  Andernfalls wird die **AcceptRejectRule**\-Eigenschaft auf **None** festgelegt.|  
  
 Das folgende Beispiel enthält ein Schema, das die **key**\-Beziehung und die **keyref**\-Beziehung zwischen dem untergeordneten **OrderNumber**\-Element des **Order**\-Elements dem untergeordneten **OrderNo**\-Element des **OrderDetail**\-Elements angibt.  
  
 Im Beispiel bezieht sich das untergeordnete **OrderNumber**\-Element des **OrderDetail**\-Elements auf das untergeordnete **OrderNo**\-Schlüsselelement des **Order**\-Elements.  
  
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
  
 Der Zuordnungsprozess des XSD\-Schemas \(XML Schema Definition Language\) erstellt das folgende **DataSet** mit zwei Tabellen:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Zusätzlich werden im **DataSet** die folgenden Einschränkungen definiert:  
  
-   Eine eindeutige Einschränkung für die **Order**\-Tabelle.  
  
    ```  
  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Eine Beziehung zwischen der **Order**\-Tabelle und der **OrderDetail**\-Tabelle.  Die **Nested**\-Eigenschaft ist auf **False** festgelegt, da die zwei Elemente im Schema nicht geschachtelt sind.  
  
    ```  
  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   Eine Fremdschlüsseleinschränkung für die **OrderDetail**\-Tabelle.  
  
    ```  
  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## Siehe auch  
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)