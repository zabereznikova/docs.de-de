---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 1d178287150dfca4c379cf6e934370434c3cfc98
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="c34e8-102">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="c34e8-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="c34e8-103">Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="c34e8-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="c34e8-104">Sie können jedoch explizit festlegen, Beziehungen zwischen Elementen, die mit nicht geschachtelt sind die **msdata: Relationship** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="c34e8-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="c34e8-105">Das folgende Beispiel zeigt ein XML-Schema, in dem die **msdata: Relationship** -Anmerkung zwischen den **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="c34e8-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="c34e8-106">Die **msdata: Relationship** -Anmerkung wird als untergeordnetes Element von der **Schema** Element.</span><span class="sxs-lookup"><span data-stu-id="c34e8-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="c34e8-107">Die XML-Schema Definition Language (XSD)-Schemazuordnungsprozess erstellt eine <xref:System.Data.DataSet> mit **Reihenfolge** und **OrderDetail** Tabellen und eine Beziehung zwischen diesen beiden Tabellen angegeben werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c34e8-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="c34e8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c34e8-108">See Also</span></span>  
 [<span data-ttu-id="c34e8-109">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="c34e8-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="c34e8-110">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="c34e8-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="c34e8-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c34e8-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
