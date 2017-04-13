---
title: "Zuordnen von f&#252;r geschachtelte Elemente angegebenen Beziehungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen von f&#252;r geschachtelte Elemente angegebenen Beziehungen
Ein Schema kann eine **msdata:Relationship**\-Anmerkung enthalten, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben.  Die beiden in **msdata:Relationship** angegebenen Elemente können im Schema geschachtelt sein. Sie müssen aber nicht geschachtelt sein.  Der Zuordnungsprozess verwendet **msdata:Relationship** im Schema, um die Primärschlüssel\-Fremdschlüssel\-Beziehung zwischen den beiden Spalten zu generieren.  
  
 Im folgenden Beispiel wird ein XML\-Schema dargestellt, in dem das **OrderDetail**\-Element ein untergeordnetes Element des **Order**\-Elements ist.  **msdata:Relationship** legt die Beziehung zwischen übergeordneten und untergeordneten Elementen für diese Elemente fest und gibt an, dass sich die **OrderNumber**\-Spalte der daraus resultierenden **Order**\-Tabelle auf die **OrderNo**\-Spalte der daraus resultierenden **OrderDetail**\-Tabelle bezieht.  
  
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
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 Durch den XML\-Schemazuordnungsprozess werden im <xref:System.Data.DataSet> folgende Elemente erstellt:  
  
-   Eine **Order**\-Tabelle und eine **OrderDetail**\-Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Eine Beziehung zwischen der **Order**\-Tabelle und der **OrderDetail**\-Tabelle.  Die **Nested**\-Eigenschaft für diese Beziehung ist auf **True** festgelegt, da das **Order**\-Element und das **OrderDetail**\-Element im Schema geschachtelt sind.  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Der Zuordnungsprozess erstellt keine Einschränkungen.  
  
## Siehe auch  
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)