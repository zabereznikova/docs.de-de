---
title: Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 86bc1961fb23b0b2f98a2849eaabd4eecd65cd64
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43533056"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
Die **Keyref** -Element können Sie zum Herstellen von Links zwischen Elementen in einem Dokument. Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar. Wenn ein Schema gibt an, die **Keyref** Element und das Element wird konvertiert, während die Schemazuordnungsprozesses in eine entsprechende fremdschlüsseleinschränkung für die Spalten in den Tabellen der der <xref:System.Data.DataSet>. In der Standardeinstellung die **Keyref** Element generiert, sondern eine Relation auch mit der **ParentTable**, **untergeordneteTabelle**, **ParentColumn**, und  **ChildColumn** Eigenschaften der Beziehung angegeben.  
  
 Der folgenden Tabelle werden die **Msdata** Attribute Sie, in angeben können der **Keyref** Element.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Wenn **ConstraintOnly = "true"** angegeben ist, auf die **Keyref** Elements im Schema, eine Einschränkung wird erstellt, aber keine Beziehung erstellt. Wenn dieses Attribut nicht angegeben ist (oder **"false"**), werden sowohl die Einschränkung und die Beziehung erstellt, der **DataSet**.|  
|**msdata:ConstraintName**|Wenn die **ConstraintName** -Attribut angegeben ist, deren Wert als den Namen der Einschränkung verwendet. Andernfalls die **Name** Attribut des der **Keyref** Elements im Schema enthält den Namen der Einschränkung in der **DataSet**.|  
|**msdata:UpdateRule**|Wenn die **UpdateRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **UpdateRule** -Einschränkungseigenschaft im der  **DataSet**. Andernfalls die **UpdateRule** -Eigenschaftensatz auf **Cascade**.|  
|**msdata:DeleteRule**|Wenn die **DeleteRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **DeleteRule** -Einschränkungseigenschaft im der  **DataSet**. Andernfalls die **DeleteRule** -Eigenschaftensatz auf **Cascade**.|  
|**msdata:AcceptRejectRule**|Wenn die **AcceptRejectRule** Attribut wird angegeben, der **Keyref** Elements im Schema, dessen Wert zugewiesen wird die **AcceptRejectRule** -Einschränkungseigenschaft im der  **DataSet**. Andernfalls die **AcceptRejectRule** -Eigenschaftensatz auf **keine**.|  
  
 Das folgende Beispiel enthält ein Schema, der angibt, die **Schlüssel** und **Keyref** Beziehungen zwischen den **OrderNumber** untergeordnetes Element von der **Reihenfolge**  Element und die **OrderNo** untergeordnetes Element von der **OrderDetail** Element.  
  
 Im Beispiel die **OrderNumber** untergeordnetes Element von der **OrderDetail** Element bezieht sich auf die **OrderNo** untergeordnete Element des der **Reihenfolge**Element.  
  
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
  
 Der XML-Schema Definition Language (XSD)-Schemazuordnungsprozess werden die folgenden **DataSet** mit zwei Tabellen:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Darüber hinaus die **DataSet** definiert die folgenden Einschränkungen:  
  
-   Eine eindeutige Einschränkung für die **Reihenfolge** Tabelle.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen. Die **geschachtelte** -Eigenschaftensatz auf **"false"** , da die zwei Elemente im Schema nicht geschachtelt sind.  
  
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
  
-   Eine foreign Key-Einschränkung für die **OrderDetail** Tabelle.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
