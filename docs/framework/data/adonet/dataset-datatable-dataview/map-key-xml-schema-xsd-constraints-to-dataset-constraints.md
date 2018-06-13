---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757865"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
In einem Schema können Sie geben eine schlüsseleinschränkung für ein Element oder-Attribut mit dem **Schlüssel** Element. Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL-Werte enthalten.  
  
 Die Schlüsseleinschränkung ist der unique-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL-Werte enthalten darf.  
  
 Die folgende Tabelle enthält die **Msdata** Attribute, die Sie, in angeben können der **Schlüssel** Element.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls die **Namen** Attribut den Wert des Einschränkungsnamen bereitstellt.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` vorhanden ist, die **IsPrimaryKey** -Einschränkungseigenschaft auf festgelegt ist **"true"**, wodurch sie zu einen Primärschlüssel. Die **AllowDBNull** -Spalteneigenschaft ist auf **"false"**, da der Primärschlüssel null-Werte enthalten darf.|  
  
 Beim Konvertieren eines Schemas, in denen eine Key-Einschränkung angegeben wird, erstellt der Zuordnungsprozess eine unique-Einschränkung für die Tabelle mit den **AllowDBNull** Spalteneigenschaft auf festgelegt **"false"** für jede Spalte in der Einschränkung. Die **IsPrimaryKey** gegen die unique-Einschränkung ist auch-Eigenschaftensatz auf **"false"** , sofern Sie angegeben haben `msdata:PrimaryKey="true"` auf die **Schlüssel** Element. Dies ist mit einer unique-Einschränkung im Schema mit `PrimaryKey="true"` identisch.  
  
 Im folgenden Schemabeispiel der **Schlüssel** Element gibt die Key-Einschränkung für die **CustomerID** Element.  
  
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
  
 Die **Schlüssel** Element gibt an, dass die Werte der **CustomerID** untergeordnetes Element von der **Kunden** Element muss eindeutige Werte und keine null-Werte. Beim Übertragen des XSD-Schemas (XML Schema Definition Language) wird vom Zuordnungsprozess die folgende Tabelle erstellt:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Die XML-schemazuordnung erstellt außerdem eine **UniqueConstraint** auf die **CustomerID** Spalte, wie im folgenden gezeigt <xref:System.Data.DataSet>. (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
```  
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
  
 In der **DataSet** , das generiert wird, die **IsPrimaryKey** Eigenschaft von der **UniqueConstraint** auf festgelegt ist **"true"** da das Schema Gibt an, `msdata:PrimaryKey="true"` in der **Schlüssel** Element.  
  
 Der Wert des der **ConstraintName** Eigenschaft der **UniqueConstraint** in der **DataSet** ist der Wert des der **ConstraintName** angegebene Attribut der **Schlüssel** -Element im Schema.  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
