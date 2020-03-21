---
title: Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150895"
---
# <a name="map-relations-specified-for-nested-elements"></a>Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
Ein Schema kann eine **msdata:Relationship-Anmerkung** enthalten, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben. Die beiden in **msdata:Relationship** angegebenen Elemente können im Schema geschachtelt werden, müssen es aber nicht sein. Der Zuordnungsprozess verwendet **msdata:Relationship** im Schema, um die Primärschlüssel-/Fremdschlüsselbeziehung zwischen den beiden Spalten zu generieren.  
  
 Das folgende Beispiel zeigt ein XML-Schema, in dem das **OrderDetail-Element** ein untergeordnetes Element von **Order**ist. Die **msdata:Relationship** identifiziert diese Parent-Child-Beziehung und gibt an, dass die **OrderNumber-Spalte** der resultierenden **Order-Tabelle** mit der **Spalte OrderNo** der resultierenden **OrderDetail-Tabelle** verknüpft ist.  
  
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
  
- Eine **Order-** und **orderDetail-Tabelle.**  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- Eine Beziehung zwischen den Tabellen **Order** und **OrderDetail.** Die **Nested-Eigenschaft** für diese Beziehung wird auf **True** festgelegt, da **die** Order- und **OrderDetail-Elemente** im Schema verschachtelt sind.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 Der Zuordnungsprozess erstellt keine Einschränkungen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
