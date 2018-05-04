---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8aed9830d613eeb7d49d2339a8ac1892c0e28e93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
In einem Schema Definition Language (XSD) XML-Schema der **eindeutige** Element gibt die eindeutigkeitseinschränkung für ein Element oder Attribut an. 	Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.  
  
 Die folgende Tabelle enthält die **Msdata** Attribute, die Sie, in angeben können der **eindeutige** Element.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls die **Namen** Attribut den Wert des Einschränkungsnamen bereitstellt.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` ist vorhanden, in der **eindeutige** Element, eine unique-Einschränkung wird erstellt, mit der **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.|  
  
 Das folgende Beispiel zeigt eine XML-Schema, verwendet der **eindeutige** Element, um eine Unique-Einschränkung anzugeben.  
  
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
  
 Die **eindeutige** -Element im Schema gibt an, dass für alle **Kunden** Instanz Elemente in einem Dokument, die den Wert des der **CustomerID** untergeordnetes Element muss eindeutig sein. Im Gebäude der **DataSet**, der Zuordnungsprozess dieses Schema liest und in der folgenden Tabelle generiert:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 Der Zuordnungsprozess erstellt auch eine unique-Einschränkung für die **CustomerID** Spalte, wie im folgenden gezeigt **DataSet**. (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
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
  
 In der **DataSet** , das generiert wird, die **IsPrimaryKey** -Eigenschaftensatz auf **"false"** für die unique-Einschränkung. Die **eindeutige** Eigenschaft für die Spalte gibt an, dass die **CustomerID** Spaltenwerte müssen eindeutig sein (kann ein null-Verweis, entsprechend den Angaben von werden jedoch die **AllowDBNull** -Eigenschaft der Spalte).  
  
 Wenn Sie das Schema ändern, und legen Sie den optionalen **msdata: PrimaryKey** -Attributwert **"true"**, die unique-Einschränkung für die Tabelle erstellt wird. Die **AllowDBNull** -Spalteneigenschaft ist auf **"false"**, und die **IsPrimaryKey** Eigenschaft der Einschränkung auf **"true"** damit die **CustomerID** Spalte eine primäre Schlüsselspalte.  
  
 Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben. Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass eine Kombination von **CustomerID** und **CompanyName** Werte müssen für alle eindeutig sein **Kunden** in einer beliebigen Instanz von Hinzufügen von einem anderen **xs: field** -Element im Schema.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Dies ist die Einschränkung, die in der resultierenden erstellt wird **DataSet**.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
