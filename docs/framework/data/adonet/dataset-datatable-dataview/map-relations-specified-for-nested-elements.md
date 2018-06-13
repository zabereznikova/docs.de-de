---
title: Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e1fde0ef585621a6821838613a7e77dedf7042b1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756695"
---
# <a name="map-relations-specified-for-nested-elements"></a>Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
Es kann ein Schema enthalten eine **msdata: Relationship** Anmerkung, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben. Die zwei Elemente im angegebenen **msdata: Relationship** können im Schema geschachtelt sein, aber nicht unbedingt sein. Der Zuordnungsprozess verwendet **msdata: Relationship** im Schema für den primären Schlüssel/Fremdschlüssel-Beziehung zwischen den beiden Spalten zu generieren.  
  
 Das folgende Beispiel zeigt ein XML-Schema, in dem die **OrderDetail** Element ist ein untergeordnetes Element des **Reihenfolge**. Die **msdata: Relationship** identifiziert diese über-/ unterordnungsbeziehung und gibt an, dass die **OrderNumber** Spalte des resultierenden **Reihenfolge** Tabelle bezieht sich auf die **OrderNo** Spalte des resultierenden **OrderDetail** Tabelle.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
 <xs:complexType>  
  <xs:choice maxOccurs="unbounded">  
   <xs:element name="Order">  
    <xs:complexType>  
     <xs:sequence>  
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 Durch den XML-Schemazuordnungsprozess werden im <xref:System.Data.DataSet> folgende Elemente erstellt:  
  
-   Ein **Reihenfolge** und ein **OrderDetail** Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen. Die **geschachtelte** -Eigenschaft für diese Beziehung wird festgelegt, um **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Der Zuordnungsprozess erstellt keine Einschränkungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
