---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 3aa9976ccde426eeda1d869164409c5235a629fe
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040054"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a>Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt. Mithilfe der msdata: Relationship-Anmerkung können Sie jedoch explizit Beziehungen zwischen Elementen angeben, die nicht mit der **msdata: Relationship** -Anmerkung versehen sind.  
  
 Im folgenden Beispiel wird ein XML-Schema gezeigt, in dem die **msdata: Relationship** -Anmerkung zwischen den Elementen **Order** und **Order Detail** angegeben ist, die nicht schziert sind. Die **msdata: Relationship** -Anmerkung wird als untergeordnetes Element des **Schema** -Elements angegeben.  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 Der XSD-Schema Mapping-Prozess (XML Schema Definition Language) erstellt eine <xref:System.Data.DataSet> mit den Tabellen **Order** und **OrderDetail** und eine Beziehung, die zwischen diesen beiden Tabellen angegeben ist, wie unten gezeigt.  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a>Siehe auch

- [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
