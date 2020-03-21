---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: bee427c6cdf76792773ea827c8772b276ff29c31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150817"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="20175-102">Angeben von Beziehungen zwischen Elementen ohne Verschachtelung</span><span class="sxs-lookup"><span data-stu-id="20175-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="20175-103">Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt.</span><span class="sxs-lookup"><span data-stu-id="20175-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="20175-104">Sie können jedoch explizit Beziehungen zwischen Elementen angeben, die nicht geschachtelt sind, indem Sie die Anmerkung **msdata:Relationship** verwenden.</span><span class="sxs-lookup"><span data-stu-id="20175-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="20175-105">Das folgende Beispiel zeigt ein XML-Schema, in dem die **msdata:Relationship-Anmerkung** zwischen den Elementen **Order** und **OrderDetail** angegeben wird, die nicht geschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="20175-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="20175-106">Die **msdata:Relationship-Anmerkung** wird als untergeordnetes Element des **Schemaelements** angegeben.</span><span class="sxs-lookup"><span data-stu-id="20175-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="20175-107">Der Schemazuordnungsprozess der XML-Schemadefinitionssprache <xref:System.Data.DataSet> (XSD) erstellt eine **Mit-Order-** und **OrderDetail-Tabellen** und eine Beziehung, die zwischen diesen beiden Tabellen angegeben ist, wie unten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="20175-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="20175-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20175-108">See also</span></span>

- [<span data-ttu-id="20175-109">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="20175-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="20175-110">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="20175-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="20175-111">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="20175-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
