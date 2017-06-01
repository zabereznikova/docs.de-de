---
title: "Zuordnen von XSD-Schl&#252;sseleinschr&#228;nkungen (XML-Schema) zu &#39;DataSet&#39;-Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen von XSD-Schl&#252;sseleinschr&#228;nkungen (XML-Schema) zu &#39;DataSet&#39;-Einschr&#228;nkungen
In einem Schema können Sie mit dem **key**\-Element eine Schlüsseleinschränkung für ein Element oder ein Attribut angeben.  Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL\-Werte enthalten.  
  
 Die Schlüsseleinschränkung ist der unique\-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL\-Werte enthalten darf.  
  
 In der folgenden Tabelle werden die **msdata**\-Attribute aufgelistet, die im **key**\-Element angegeben werden können.  
  
|Attributname|Beschreibung|  
|------------------|------------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.  Andernfalls wird der Wert des Einschränkungsnamen vom **name**\-Attribut bereitgestellt.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` vorhanden ist, wird die **IsPrimaryKey**\-Einschränkungseigenschaft auf **true** festgelegt, wodurch sie zu einem Primärschlüssel wird.  Die **AllowDBNull**\-Spalteneigenschaft ist auf **false** festgelegt, da Primärschlüssel keine NULL\-Werte enthalten dürfen.|  
  
 Beim Konvertieren eines Schemas, in dem eine Schlüsseleinschränkung angegeben ist, erstellt der Zuordnungsprozess eine unique\-Einschränkung für die Tabelle, in der die **AllowDBNull**\-Spalteneigenschaft für jede Spalte in der Einschränkung auf **false** festgelegt ist.  Die **IsPrimaryKey**\-Eigenschaft der unique\-Einschränkung ist ebenfalls auf **false** festgelegt, wenn Sie für das **key**\-Element nicht `msdata:PrimaryKey="true"` angegeben haben.  Dies ist mit einer unique\-Einschränkung im Schema mit `PrimaryKey="true"` identisch.  
  
 Im folgenden Schemabeispiel gibt das **key**\-Element die Schlüsseleinschränkung für das **CustomerID**\-Element an.  
  
```  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 Das **key**\-Element gibt an, dass es sich bei den Werten für das untergeordnete **CustomerID**\-Element des **Customers**\-Elements um eindeutige Werte handeln muss und dass keine NULL\-Werte vorhanden sein dürfen.  Beim Übertragen des XSD\-Schemas \(XML Schema Definition Language\) wird vom Zuordnungsprozess die folgende Tabelle erstellt:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Die XML\-Schemazuordnung erstellt außerdem eine **UniqueConstraint** für die **CustomerID**\-Spalte. Dies wird im folgenden <xref:System.Data.DataSet> dargestellt.  \(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.\)  
  
```  
  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 Im generierten **DataSet** ist die **IsPrimaryKey**\-Eigenschaft der **UniqueConstraint** auf **true** festgelegt, da das Schema im **key**\-Element `msdata:PrimaryKey="true"` angibt.  
  
 Der Wert der **ConstraintName**\-Eigenschaft der **UniqueConstraint** im **DataSet** ist der Wert des **msdata:ConstraintName**\-Attributs, das im **key**\-Element des Schemas angegeben wurde.  
  
## Siehe auch  
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)