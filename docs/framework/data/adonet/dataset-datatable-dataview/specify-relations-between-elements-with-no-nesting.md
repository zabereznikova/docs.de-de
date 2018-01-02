---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 51d2248094ecf66eedbf8cd187cf6c8270ca5116
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="1d458-102">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="1d458-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="1d458-103">Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="1d458-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="1d458-104">Sie können jedoch explizit festlegen, Beziehungen zwischen Elementen, die mit nicht geschachtelt sind die **msdata: Relationship** Anmerkung.</span><span class="sxs-lookup"><span data-stu-id="1d458-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="1d458-105">Das folgende Beispiel zeigt ein XML-Schema, in dem die **msdata: Relationship** -Anmerkung zwischen den **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="1d458-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="1d458-106">Die **msdata: Relationship** -Anmerkung wird als untergeordnetes Element von der **Schema** Element.</span><span class="sxs-lookup"><span data-stu-id="1d458-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="1d458-107">Die XML-Schema Definition Language (XSD)-Schemazuordnungsprozess erstellt eine <xref:System.Data.DataSet> mit **Reihenfolge** und **OrderDetail** Tabellen und eine Beziehung zwischen diesen beiden Tabellen angegeben werden, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1d458-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d458-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d458-108">See Also</span></span>  
 [<span data-ttu-id="1d458-109">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1d458-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="1d458-110">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1d458-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="1d458-111">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1d458-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
