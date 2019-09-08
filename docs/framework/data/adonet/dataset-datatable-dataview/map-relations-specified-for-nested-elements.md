---
title: Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e8cdf73b6277abdaab1256ca87e615a5e25e7336
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786084"
---
# <a name="map-relations-specified-for-nested-elements"></a>Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
Ein Schema kann eine **msdata: Relationship** -Anmerkung enthalten, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben. Die beiden in **msdata: Relationship** angegebenen Elemente können im Schema, jedoch nicht vorhanden sein. Der Mapping-Prozess verwendet **msdata: Relationship** im Schema, um die PRIMARY KEY/Foreign Key-Beziehung zwischen den beiden Spalten zu generieren.  
  
 Das folgende Beispiel zeigt ein XML-Schema, in dem das **OrderDetail** -Element ein untergeordnetes Element der **Order**-Datei ist. Die **msdata: Relationship** identifiziert diese Beziehung zwischen über-und untergeordneten Elementen und gibt an, dass die **OrderNumber** -Spalte der resultierenden **Order** -Tabelle mit der **OrderNo** -Spalte der resultierenden **OrderDetail** -Tabelle verknüpft ist.  
  
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
  
- Eine **Bestellung** und eine **Order Detail** -Tabelle.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle. Die Eigenschaft " **schsted** " für diese Beziehung wird auf " **true** " festgelegt, da die Elemente **Order** und **Order Detail** im Schema scht sind.  
  
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

- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
