---
title: "Zuordnen von impliziten Beziehungen zwischen im Schema geschachtelten Elementen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Zuordnen von impliziten Beziehungen zwischen im Schema geschachtelten Elementen
Ein XSD\-Schema \(XML Schema Definition Language\) kann komplexe Typen aufweisen, die ineinander geschachtelt sind.  In diesem Fall wendet der Zuordnungsprozess die Standardzuordnung an und erstellt folgende Elemente im <xref:System.Data.DataSet>:  
  
-   Eine Tabelle für jeden der komplexen Typen \(übergeordnet und untergeordnet\).  
  
-   Wenn für den übergeordneten Typ keine eindeutige Einschränkung vorhanden ist, eine zusätzliche Primärschlüsselspalte pro Tabellendefinition mit dem Namen *Tabellenname*\_Id, wobei *Tabellenname* der Name der übergeordneten Tabelle ist.  
  
-   Eine Primärschlüsseleinschränkung für die übergeordnete Tabelle, die die zusätzliche Spalte als Primärschlüssel identifiziert \(indem die **IsPrimaryKey**\-Eigenschaft auf **True** festgelegt wird\).  Die Einschränkung wird mit Constraint *\#* benannt, wobei *\#* für 1, 2, 3 usw. steht.  Beispielsweise lautet der Standardname für die erste Einschränkung "Constraint1".  
  
-   Eine Fremdschlüsseleinschränkung für die untergeordnete Tabelle, die die zusätzliche Spalte als den auf den Primärschlüssel der übergeordneten Tabelle verweisenden Fremdschlüssel identifiziert.  Die Einschränkung wird mit *übergeordneteTabelle\_untergeordneteTabelle* benannt, wobei *übergeordneteTabelle* der Name der übergeordneten Tabelle und *untergeordneteTabelle* der Name der untergeordneten Tabelle ist.  
  
-   Eine Datenbeziehung zwischen übergeordneten und untergeordneten Tabellen.  
  
 Im folgenden Beispiel wird ein Schema dargestellt, in dem **OrderDetail** ein untergeordnetes Element von **Order** ist.  
  
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
  
 Durch den XML\-Schemazuordnungsprozess werden im **DataSet** folgende Elemente erstellt:  
  
-   Eine **Order**\-Tabelle und eine **OrderDetail**\-Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Eine eindeutige Einschränkung für die **Order**\-Tabelle.  Beachten Sie, dass die **IsPrimaryKey**\-Eigenschaft auf **True** festgelegt wurde.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Eine Fremdschlüsseleinschränkung für die **OrderDetail**\-Tabelle.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Eine Beziehung zwischen der **Order**\-Tabelle und der **OrderDetail**\-Tabelle.  Die **Nested**\-Eigenschaft für diese Beziehung ist auf **True** festgelegt, da das **Order**\-Element und das **OrderDetail**\-Element im Schema geschachtelt sind.  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## Siehe auch  
 [Generieren von DataSet\-Beziehungen aus einem XML\-Schema \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Zuordnen von XSD\-Einschränkungen \(XML\-Schema\) zu DataSet\-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)