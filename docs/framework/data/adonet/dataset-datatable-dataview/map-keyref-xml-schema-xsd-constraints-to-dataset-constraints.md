---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: b5ffe69886b08903feab4373b1cd5c5244b3b3b9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784516"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
Das **keyref** -Element ermöglicht es Ihnen, Links zwischen Elementen innerhalb eines Dokuments zu erstellen. Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar. Wenn ein Schema das **keyref** -Element angibt, wird das-Element während des Schema Zuordnungsprozesses in eine entsprechende Foreign Key-Einschränkung für die Spalten in <xref:System.Data.DataSet>den-Tabellen konvertiert. Standardmäßig generiert das **keyref** -Element auch eine Beziehung, bei der **die Eigenschaften**"parametable", " **ChildTable**", " **para Column**" und " **childColumn** " in der Beziehung angegeben werden.  
  
 In der folgenden Tabelle werden die **msdata** -Attribute aufgelistet, die Sie im **keyref** -Element angeben können.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Wenn für das **keyref** -Element im Schema **"beschränintonly =" true "** angegeben wird, wird eine Einschränkung erstellt, aber es wird keine Beziehung erstellt. Wenn dieses Attribut nicht angegeben wird (oder auf **false**festgelegt ist), werden sowohl die-Einschränkung als auch die-Beziehung im **DataSet**erstellt.|  
|**msdata:ConstraintName**|Wenn das Attribut " **Einschränkungs Name** " angegeben wird, wird dessen Wert als Name der Einschränkung verwendet. Andernfalls stellt das Attribut " **Name** " des **keyref** -Elements im Schema den Einschränkungs Namen im **DataSet**bereit.|  
|**msdata:UpdateRule**|Wenn das **UpdateRule** -Attribut im **keyref** -Element im Schema angegeben wird, wird dessen Wert der **UpdateRule** -Einschränkungs Eigenschaft im **DataSet**zugewiesen. Andernfalls ist die **UpdateRule** -Eigenschaft auf **Cascade**festgelegt.|  
|**msdata:DeleteRule**|Wenn das **DeleteRule** -Attribut im **keyref** -Element im Schema angegeben wird, wird dessen Wert der **DeleteRule** -Einschränkungs Eigenschaft im **DataSet**zugewiesen. Andernfalls ist die **DeleteRule** -Eigenschaft auf **Cascade**festgelegt.|  
|**msdata:AcceptRejectRule**|Wenn das Attribut " **Accept trejectrule** " im **keyref** -Element im Schema angegeben wird, wird dessen Wert der Eigenschaft " **Accept trejectrule** " im **DataSet**zugewiesen. Andernfalls ist die Eigenschaft " **akzeptrejectrule** " auf " **None**" festgelegt.|  
  
 Das folgende Beispiel enthält ein Schema, das die **Key** -Beziehung und die **keyref** -Beziehung zwischen dem untergeordneten **OrderNumber** -Element des **Order** -Elements und dem untergeordneten **OrderNo** -Element des **Order Detail** -Elements angibt. gewisses.  
  
 Im Beispiel verweist das untergeordnete **OrderNumber** -Element des **Order Detail** -Elements auf das untergeordnete **OrderNo** -Schlüsselelement des **Order** -Elements.  
  
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
  
 Der XSD (XML Schema Definition Language)-Schema Mapping-Prozess erzeugt das folgende **DataSet** mit zwei Tabellen:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Außerdem definiert das **DataSet** die folgenden Einschränkungen:  
  
- Eine Unique-Einschränkung für die **Order** -Tabelle.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle. Die Eigenschaft " **schsted** " ist auf " **false** " festgelegt, da die beiden Elemente nicht im Schema enthalten sind.  
  
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
  
- Eine FOREIGN KEY-Einschränkung für die **Order Detail** -Tabelle.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
