---
title: "Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f888a682510dbf768e5eab2ffdd530e2ac7cf635
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von keyref-XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
Die **Keyref** Element können Sie Links zwischen Elementen in einem Dokument herstellen. Dies ist mit einer Fremdschlüsselbeziehung in einer relationalen Datenbank vergleichbar. Wenn ein Schema gibt die **Keyref** Element, das Element wird konvertiert, während die Schemazuordnungsprozesses in eine entsprechende foreign Key-Einschränkung für die Spalten in den Tabellen der der <xref:System.Data.DataSet>. Wird standardmäßig die **Keyref** Element generiert auch eine Beziehung mit der **ParentTable**, **untergeordneteTabelle**, **ParentColumn**, und  **ChildColumn** Eigenschaften der Beziehung angegeben.  
  
 Die folgende Tabelle enthält die **Msdata** Attribute Sie, in angeben können der **Keyref** Element.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata: ConstraintOnly**|Wenn **ConstraintOnly = "true"** angegeben ist, auf die **Keyref** -Element im Schema, eine Einschränkung erstellt wird, aber keine Beziehung erstellt. Wenn dieses Attribut nicht angegeben ist (oder **"false"**), werden sowohl die Einschränkung als auch die Beziehung erstellt, der **DataSet**.|  
|**ConstraintName**|Wenn die **ConstraintName** -Attribut angegeben ist, deren Wert als den Namen der Einschränkung verwendet. Andernfalls der **Namen** Attribut des der **Keyref** -Element im Schema enthält den Namen der Einschränkung in der **DataSet**.|  
|**msdata:UpdateRule**|Wenn die **UpdateRule** Attribut wird angegeben, der **Keyref** Element im Schema, dessen Wert zugeordnet ist die **UpdateRule** -Einschränkungseigenschaft im die  **DataSet**. Andernfalls die **UpdateRule** -Eigenschaftensatz auf **Cascade**.|  
|**msdata:DeleteRule**|Wenn die **DeleteRule** Attribut wird angegeben, der **Keyref** Element im Schema, dessen Wert zugeordnet ist die **DeleteRule** -Einschränkungseigenschaft im die  **DataSet**. Andernfalls die **DeleteRule** -Eigenschaftensatz auf **Cascade**.|  
|**msdata:AcceptRejectRule**|Wenn die **AcceptRejectRule** Attribut wird angegeben, der **Keyref** Element im Schema, dessen Wert zugeordnet ist die **AcceptRejectRule** -Einschränkungseigenschaft im die  **DataSet**. Andernfalls die **AcceptRejectRule** -Eigenschaftensatz auf **keine**.|  
  
 Das folgende Beispiel enthält ein Schema, der angibt, die **Schlüssel** und **Keyref** Beziehungen zwischen den **OrderNumber** untergeordnetes Element von der **Reihenfolge**  Element und die **OrderNo** untergeordnetes Element von der **OrderDetail** Element.  
  
 Im Beispiel die **OrderNumber** untergeordnetes Element von der **OrderDetail** Element bezieht sich auf die **OrderNo** Key untergeordnetes Element von der **Reihenfolge**Element.  
  
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
  
 Die XML Schema Definition Language (XSD)-Schemazuordnungsprozess generiert die folgende **DataSet** mit zwei Tabellen:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Darüber hinaus die **DataSet** definiert die folgenden Einschränkungen:  
  
-   Eine unique-Einschränkung für die **Reihenfolge** Tabelle.  
  
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
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
