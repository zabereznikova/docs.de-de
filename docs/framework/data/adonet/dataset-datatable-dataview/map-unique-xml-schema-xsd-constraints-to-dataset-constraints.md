---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 4aa94dfaf088a2a934c8901e2720f166d3a38dae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784409"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
In einem XSD-Schema (XML Schema Definition Language) gibt das **Unique** -Element die Eindeutigkeits Einschränkung für ein Element oder Attribut an. Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.  
  
 In der folgenden Tabelle werden die **msdata** -Attribute aufgelistet, die Sie im **Unique** -Element angeben können.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls stellt das **Name** -Attribut den Wert des Einschränkungs namens bereit.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` im **Unique** -Element vorhanden ist, wird eine Unique-Einschränkung erstellt, bei der die **IsPrimaryKey** -Eigenschaft auf **true**festgelegt ist.|  
  
 Das folgende Beispiel zeigt ein XML-Schema, das das **Unique** -Element verwendet, um eine Eindeutigkeits Einschränkung anzugeben.  
  
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
  
 Das **Unique** -Element im Schema gibt an, dass der Wert des untergeordneten **CustomerID-** Elements für alle **Kunden** Elemente in einer Dokument Instanz eindeutig sein muss. Beim Aufbau des **DataSets**liest der Mapping-Prozess dieses Schema und generiert die folgende Tabelle:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Der Mapping-Prozess erstellt auch eine Unique-Einschränkung für die **CustomerID-** Spalte, wie im folgenden **DataSet**gezeigt. (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
```  
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
  
 Im generierten **DataSet** ist die **IsPrimaryKey** -Eigenschaft für die Unique-Einschränkung auf **false** festgelegt. Die **Unique** -Eigenschaft für die Spalte gibt an, dass die Werte der **CustomerID-** Spalte eindeutig sein müssen (Sie können jedoch ein NULL-Verweis sein, wie durch die **AllowDBNull** -Eigenschaft der Spalte angegeben).  
  
 Wenn Sie das Schema ändern und den optionalen Attribut Wert **msdata: PrimaryKey** auf **true**festlegen, wird die Unique-Einschränkung für die Tabelle erstellt. Die **AllowDBNull** -Spalten Eigenschaft ist auf **false**festgelegt, und die **IsPrimaryKey** -Eigenschaft der Einschränkung ist auf **true**festgelegt, sodass die **CustomerID-** Spalte eine Primärschlüssel Spalte ist.  
  
 Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben. Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass eine Kombination der Werte **CustomerID** und **CompanyName** für alle **Kunden** in jeder Instanz eindeutig sein muss, indem ein weiteres **xs: Field** -Element im Schema hinzugefügt wird.  
  
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
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Siehe auch

- [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
