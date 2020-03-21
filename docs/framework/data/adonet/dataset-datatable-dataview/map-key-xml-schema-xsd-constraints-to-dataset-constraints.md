---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150934"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
In einem Schema können Sie mithilfe des **Schlüsselelements** eine Schlüsseleinschränkung für ein Element oder Attribut angeben. Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL-Werte enthalten.  
  
 Die Schlüsseleinschränkung ist der unique-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL-Werte enthalten darf.  
  
 In der folgenden Tabelle werden die **msdata-Attribute** beschrieben, die Sie im **Schlüsselelement** angeben können.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet. Andernfalls stellt das **name-Attribut** den Wert des Einschränkungsnamens bereit.|  
|**msdata:PrimaryKey**|Wenn `PrimaryKey="true"` vorhanden, wird die **IsPrimaryKey-Einschränkungseigenschaft** auf **true**festgelegt, wodurch sie zu einem Primärschlüssel wird. Die **Spalteneigenschaft AllowDBNull** ist auf **false**festgelegt, da Primärschlüssel keine NULL-Werte haben können.|  
  
 Beim Konvertieren des Schemas, in dem eine Schlüsseleinschränkung angegeben wird, erstellt der Zuordnungsprozess eine eindeutige Einschränkung für die Tabelle, wobei die **AllowDBNull-Spalteneigenschaft** für jede Spalte in der Einschränkung **auf false** festgelegt ist. Die **IsPrimaryKey-Eigenschaft** der eindeutigen Einschränkung wird ebenfalls `msdata:PrimaryKey="true"` auf **false** festgelegt, es sei denn, Sie haben für das **Schlüsselelement** angegeben. Dies ist mit einer unique-Einschränkung im Schema mit `PrimaryKey="true"` identisch.  
  
 Im folgenden Schemabeispiel gibt das **Schlüsselelement** die Schlüsseleinschränkung für das **CustomerID-Element** an.  
  
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
  
 Das **Schlüsselelement** gibt an, dass die Werte des **untergeordneten CustomerID-Elements** des **Customers-Elements** eindeutige Werte aufweisen müssen und keine NULL-Werte haben können. Beim Übertragen des XSD-Schemas (XML Schema Definition Language) wird vom Zuordnungsprozess die folgende Tabelle erstellt:  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 Die XML-Schemazuordnung erstellt auch eine **UniqueConstraint** für die <xref:System.Data.DataSet> **CustomerID-Spalte,** wie in der folgenden dargestellt. (Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)  
  
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
  
 Im `msdata:PrimaryKey="true"` generierten **DataSet** wird die **IsPrimaryKey-Eigenschaft** der **UniqueConstraint** auf **true** festgelegt, da das Schema im **Schlüsselelement** angibt.  
  
 Der Wert der **ConstraintName-Eigenschaft** der **UniqueConstraint** im **DataSet** ist der Wert des **msdata:ConstraintName-Attributs,** das im **Schlüsselelement** im Schema angegeben ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
