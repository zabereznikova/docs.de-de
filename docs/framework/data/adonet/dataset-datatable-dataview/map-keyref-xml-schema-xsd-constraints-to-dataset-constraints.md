---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150882"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
Mit dem **keyref-Element** können Sie Verknüpfungen zwischen Elementen innerhalb eines Dokuments herstellen. Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar. Wenn ein Schema das **keyref-Element** angibt, wird das Element während des Schemazuordnungsprozesses in <xref:System.Data.DataSet>eine entsprechende Fremdschlüsseleinschränkung für die Spalten in den Tabellen der konvertiert. Standardmäßig generiert das **keyref-Element** auch eine Beziehung mit den Eigenschaften **ParentTable**, **ChildTable**, **ParentColumn**und **ChildColumn,** die für die Beziehung angegeben sind.  
  
 In der folgenden Tabelle werden die **msdata-Attribute** beschrieben, die Sie im **keyref-Element** angeben können.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Wenn **ConstraintOnly="true"** für das **keyref-Element** im Schema angegeben ist, wird eine Einschränkung erstellt, aber keine Beziehung wird erstellt. Wenn dieses Attribut nicht angegeben ist (oder auf **False**festgelegt ist), werden sowohl die Einschränkung als auch die Beziehung im **DataSet**erstellt.|  
|**msdata:ConstraintName**|Wenn das **ConstraintName-Attribut** angegeben wird, wird sein Wert als Name der Einschränkung verwendet. Andernfalls stellt das **name-Attribut** des **keyref-Elements** im Schema den Einschränkungsnamen im **DataSet bereit.**|  
|**msdata:UpdateRule**|Wenn das **UpdateRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **UpdateRule-Einschränkungseigenschaft** im **DataSet**zugewiesen. Andernfalls wird die **UpdateRule-Eigenschaft** auf **Cascade**festgelegt.|  
|**msdata:DeleteRule**|Wenn das **DeleteRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **DeleteRule-Einschränkungseigenschaft** im **DataSet**zugewiesen. Andernfalls wird die **DeleteRule-Eigenschaft** auf **Cascade**festgelegt.|  
|**msdata:AcceptRejectRule**|Wenn das **AcceptRejectRule-Attribut** im **keyref-Element** im Schema angegeben ist, wird sein Wert der **AcceptRejectRule-Einschränkungseigenschaft** im **DataSet**zugewiesen. Andernfalls wird die **AcceptRejectRule-Eigenschaft** auf **Keine**festgelegt.|  
  
 Das folgende Beispiel enthält ein Schema, das die **Schlüssel-** und **Keyref-Beziehungen** zwischen dem untergeordneten **OrderNumber-Element** des **Order-Elements** und dem **untergeordneten OrderNo-Element** des **OrderDetail-Elements** angibt.  
  
 Im Beispiel verweist das untergeordnete **OrderNumber-Element** des **OrderDetail-Elements** auf das untergeordnete **Schlüsselelement OrderNo** des **Order-Elements.**  
  
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
  
 Der Xml-Schema-Definitions-Schemazuordnungsprozess (XML Schema Definition Language, XSD) erzeugt das folgende **DataSet** mit zwei Tabellen:  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Darüber hinaus definiert das **DataSet** die folgenden Einschränkungen:  
  
- Eine eindeutige Einschränkung für die **Tabelle "Auftrag".**  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Eine Beziehung zwischen den Tabellen **Order** und **OrderDetail.** Die **Nested-Eigenschaft** ist auf **False** festgelegt, da die beiden Elemente nicht im Schema verschachtelt sind.  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- Eine Fremdschlüsseleinschränkung für die **Tabelle OrderDetail.**  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
