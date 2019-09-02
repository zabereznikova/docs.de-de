---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 83dce7173c016a7d7d2d626bb7a3606de29d54ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204467"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="3459b-102">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="3459b-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="3459b-103">Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="3459b-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="3459b-104">Mithilfe der msdata: Relationship-Anmerkung können Sie jedoch explizit Beziehungen zwischen Elementen angeben, die nicht mit der **msdata: Relationship** -Anmerkung versehen sind.</span><span class="sxs-lookup"><span data-stu-id="3459b-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="3459b-105">Im folgenden Beispiel wird ein XML-Schema gezeigt, in dem die **msdata: Relationship** -Anmerkung zwischen den Elementen **Order** und **Order Detail** angegeben ist, die nicht schziert sind.</span><span class="sxs-lookup"><span data-stu-id="3459b-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="3459b-106">Die **msdata: Relationship** -Anmerkung wird als untergeordnetes Element des **Schema** -Elements angegeben.</span><span class="sxs-lookup"><span data-stu-id="3459b-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="3459b-107">Der XSD (XML Schema Definition Language)-Schema Mapping-Prozess <xref:System.Data.DataSet> erstellt eine mit den Tabellen **Order** und **OrderDetail** und eine Beziehung, die zwischen diesen beiden Tabellen angegeben ist, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3459b-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="3459b-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3459b-108">See also</span></span>

- [<span data-ttu-id="3459b-109">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3459b-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="3459b-110">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3459b-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="3459b-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3459b-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
