---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: b55b232faa01bf36788276caaf8bc2e97dddf697
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172787"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen

In einem Schema können Sie eine Schlüssel Einschränkung für ein Element oder Attribut mit dem **Schlüssel** Element angeben. Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL-Werte enthalten.  
  
 Die Schlüsseleinschränkung ist der unique-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL-Werte enthalten darf.  
  
 In der folgenden Tabelle werden die **msdata** -Attribute aufgelistet, die Sie im **Key** -Element angeben können.  
  
|Attributname|BESCHREIBUNG|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls stellt das **Name** -Attribut den Wert des Einschränkungs namens bereit.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` vorhanden ist, wird die **IsPrimaryKey** -Einschränkungs Eigenschaft auf **true**festgelegt und somit als Primärschlüssel festgelegt. Die **AllowDBNull** -Spalten Eigenschaft ist auf **false**festgelegt, da Primärschlüssel keine NULL-Werte aufweisen können.|  
  
 Beim Umrechnen eines Schemas, in dem eine Schlüssel Einschränkung angegeben ist, erstellt der Zustellungs Prozess eine Unique-Einschränkung für die Tabelle, bei der die **AllowDBNull** -Spalten Eigenschaft für jede Spalte in der Einschränkung auf **false** festgelegt ist. Die **IsPrimaryKey** -Eigenschaft der Unique-Einschränkung ist auch auf **false** festgelegt, es sei denn, Sie haben `msdata:PrimaryKey="true"` für das **Key** -Element angegeben. Dies ist mit einer unique-Einschränkung im Schema mit `PrimaryKey="true"` identisch.  
  
 Im folgenden Schema Beispiel gibt das **Key** -Element die Schlüssel Einschränkung für das **CustomerID-** Element an.  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>
```  
  
 Das **Key** -Element gibt an, dass die Werte des untergeordneten **CustomerID-** Elements des **Customers** -Elements eindeutige Werte aufweisen müssen und keine NULL-Werte aufweisen dürfen. Beim Übertragen des XSD-Schemas (XML Schema Definition Language) wird vom Zuordnungsprozess die folgende Tabelle erstellt:  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Die XML-Schema Zuordnung erstellt auch ein **UniqueConstraint** -Element für die **CustomerID-** Spalte, wie im folgenden gezeigt <xref:System.Data.DataSet> . (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID
      IsPrimaryKey: True  
```  
  
 Im generierten **DataSet** ist die **IsPrimaryKey** -Eigenschaft von **UniqueConstraint** auf **true** festgelegt, da das Schema `msdata:PrimaryKey="true"` im **Key** -Element angibt.  
  
 Der Wert der Eigenschaft " **Einschränkungs Name** " der **UniqueConstraint** im **DataSet** ist der Wert des Attributs " **msdata: Einschränkungs Name** ", das im **Key** -Element im Schema angegeben ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
