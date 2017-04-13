---
title: "Zuordnen eindeutiger XSD-Einschr&#228;nkungen (XML-Schema) zu &#39;DataSet&#39;-Einschr&#228;nkungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen eindeutiger XSD-Einschr&#228;nkungen (XML-Schema) zu &#39;DataSet&#39;-Einschr&#228;nkungen
In einem XSD\-Schema \(XML Schema Definition Language\) gibt das **unique**\-Element die eindeutige Einschränkung für ein Element oder Attribut an.  	Beim Übersetzen eines XML\-Schemas in ein relationales Schema wird die im XML\-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.  
  
 In der folgenden Tabelle werden die **msdata**\-Attribute aufgelistet, die im **unique**\-Element angegeben werden können.  
  
|Attributname|Beschreibung|  
|------------------|------------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.  Andernfalls wird der Wert des Einschränkungsnamen vom **name**\-Attribut bereitgestellt.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` im **unique**\-Element vorhanden ist, wird eine eindeutige Einschränkung erstellt, deren **IsPrimaryKey**\-Eigenschaft auf **true** festgelegt ist.|  
  
 Im folgenden Beispiel wird ein XML\-Schema dargestellt, das mit dem **unique**\-Element eine eindeutige Einschränkung angibt.  
  
```  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique      
msdata:ConstraintName="UCustID"      
name="UniqueCustIDConstr" >        
<xs:selector xpath=".//Customers" />        
<xs:field xpath="CustomerID" />      
</xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 Das **unique**\-Element im Schema gibt an, dass der Wert des untergeordneten **CustomerID**\-Elements für alle **Customers**\-Elemente in einer Dokumentinstanz eindeutig sein muss.  Wenn das **DataSet** erstellt wird, liest der Zuordnungsprozess dieses Schema und generiert folgende Tabelle:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Beim Zuordnungsprozess wird auch eine eindeutige Einschränkung für die **CustomerID**\-Spalte erstellt. Dies wird im folgenden **DataSet** dargestellt.  \(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.\)  
  
```  
  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID  
      Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 Im erstellten **DataSet** ist die **IsPrimaryKey**\-Eigenschaft für die eindeutige Einschränkung auf **False** festgelegt.  Die **unique**\-Eigenschaft für die Spalte gibt an, dass die Werte der **CustomerID**\-Spalte eindeutig sein müssen. \(Entsprechend der **AllowDBNull**\-Eigenschaft der Spalte können die Werte jedoch ein NULL\-Verweis sein.\)  
  
 Wenn Sie das Schema ändern und den optionalen **msdata:PrimaryKey**\-Attributwert auf **True** festlegen, wird die eindeutige Einschränkung für die Tabelle erstellt.  Die **AllowDBNull**\-Spalteneigenschaft ist auf **False** festgelegt, und die **IsPrimaryKey**\-Eigenschaft der Einschränkung ist auf **True** festgelegt. Damit wird die **CustomerID**\-Spalte zu einer Primärschlüsselspalte.  
  
 Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML\-Schema angeben.  Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass eine Kombination von **CustomerID**\-Werten und **CompanyName**\-Werten für alle **Customers** in jeder Instanz eindeutig sein müssen. Hierzu wird dem Schema ein weiteres **xs:field**\-Element hinzugefügt.  
  
```  
  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Dies ist die im resultierenden **DataSet** erstellte Einschränkung.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## Siehe auch  
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)