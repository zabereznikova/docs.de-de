---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: d04a3d946b87c7203497313c6e21a75ef69f50eb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43724307"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="2706e-102">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="2706e-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="2706e-103">Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="2706e-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="2706e-104">Sie können jedoch explizit angeben von Beziehungen zwischen Elementen, die mit nicht geschachtelt sind die **msdata: Relationship** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="2706e-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="2706e-105">Das folgende Beispiel zeigt ein XML-Schema, in dem die **msdata: Relationship** -Anmerkung zwischen den **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="2706e-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="2706e-106">Die **msdata: Relationship** -Anmerkung als untergeordnetes Element von der **Schema** Element.</span><span class="sxs-lookup"><span data-stu-id="2706e-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="2706e-107">Die XML-Schema Definition Language (XSD)-Schemazuordnungsprozess erstellt eine <xref:System.Data.DataSet> mit **Reihenfolge** und **OrderDetail** Tabellen und eine Beziehung zwischen diesen beiden Tabellen angegeben werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2706e-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="2706e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2706e-108">See Also</span></span>  
 [<span data-ttu-id="2706e-109">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="2706e-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="2706e-110">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="2706e-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="2706e-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="2706e-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
