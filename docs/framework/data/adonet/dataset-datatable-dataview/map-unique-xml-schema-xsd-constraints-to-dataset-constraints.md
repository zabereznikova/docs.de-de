---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150843"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
In einem XML-Schema für die Schemadefinitionssprache (XSD) gibt das **eindeutige** Element die Eindeutigkeitseinschränkung für ein Element oder Attribut an. 	Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.  
  
 In der folgenden Tabelle werden die **msdata-Attribute** beschrieben, die Sie im **eindeutigen** Element angeben können.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls stellt das **name-Attribut** den Wert des Einschränkungsnamens bereit.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` das **eindeutige** Element vorhanden ist, wird eine eindeutige Einschränkung erstellt, wobei die **IsPrimaryKey-Eigenschaft** auf **true**festgelegt ist.|  
  
 Das folgende Beispiel zeigt ein XML-Schema, das das **eindeutige** Element verwendet, um eine Eindeutigkeitseinschränkung anzugeben.  
  
```xml  
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
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 Das **eindeutige** Element im Schema gibt an, dass für alle **Customers-Elemente** in einer Dokumentinstanz der Wert des **untergeordneten CustomerID-Elements** eindeutig sein muss. Beim Erstellen des **DataSets**liest der Zuordnungsprozess dieses Schema und generiert die folgende Tabelle:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Der Zuordnungsprozess erstellt auch eine eindeutige Einschränkung für die **CustomerID-Spalte,** wie im folgenden **DataSet**gezeigt. (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 Im **generierten DataSet** wird die **IsPrimaryKey-Eigenschaft** für die eindeutige Einschränkung auf **False** festgelegt. Die **eindeutige** Eigenschaft in der Spalte gibt an, dass die **CustomerID-Spaltenwerte** eindeutig sein müssen (sie können jedoch ein Nullverweis sein, wie durch die **AllowDBNull-Eigenschaft** der Spalte angegeben).  
  
 Wenn Sie das Schema ändern und den optionalen **msdata:PrimaryKey-Attributwert** auf **True**festlegen, wird die eindeutige Einschränkung für die Tabelle erstellt. Die **AllowDBNull-Spalteneigenschaft** ist auf **False**festgelegt, und die **IsPrimaryKey-Eigenschaft** der Einschränkung wird auf **True**festgelegt, wodurch die **CustomerID-Spalte** zu einer Primärschlüsselspalte wird.  
  
 Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben. Im folgenden Beispiel wird veranschaulicht, wie Sie angeben, dass eine Kombination aus **CustomerID-** und **CompanyName-Werten** für alle **Kunden** in jedem Fall eindeutig sein muss, indem Sie ein weiteres **xs:field-Element** im Schema hinzufügen.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 Dies ist die Einschränkung, die im resultierenden **DataSet**erstellt wird.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
