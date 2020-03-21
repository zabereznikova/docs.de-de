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
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="88916-102">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="88916-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="88916-103">Ein Schema kann eine **msdata:Relationship-Anmerkung** enthalten, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="88916-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="88916-104">Die beiden in **msdata:Relationship** angegebenen Elemente können im Schema geschachtelt werden, müssen es aber nicht sein.</span><span class="sxs-lookup"><span data-stu-id="88916-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="88916-105">Der Zuordnungsprozess verwendet **msdata:Relationship** im Schema, um die Primärschlüssel-/Fremdschlüsselbeziehung zwischen den beiden Spalten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="88916-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="88916-106">Das folgende Beispiel zeigt ein XML-Schema, in dem das **OrderDetail-Element** ein untergeordnetes Element von **Order**ist.</span><span class="sxs-lookup"><span data-stu-id="88916-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="88916-107">Die **msdata:Relationship** identifiziert diese Parent-Child-Beziehung und gibt an, dass die **OrderNumber-Spalte** der resultierenden **Order-Tabelle** mit der **Spalte OrderNo** der resultierenden **OrderDetail-Tabelle** verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="88916-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="88916-108">Durch den XML-Schemazuordnungsprozess werden im <xref:System.Data.DataSet> folgende Elemente erstellt:</span><span class="sxs-lookup"><span data-stu-id="88916-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="88916-109">Eine **Order-** und **orderDetail-Tabelle.**</span><span class="sxs-lookup"><span data-stu-id="88916-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="88916-110">Eine Beziehung zwischen den Tabellen **Order** und **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="88916-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="88916-111">Die **Nested-Eigenschaft** für diese Beziehung wird auf **True** festgelegt, da **die** Order- und **OrderDetail-Elemente** im Schema verschachtelt sind.</span><span class="sxs-lookup"><span data-stu-id="88916-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="88916-112">Der Zuordnungsprozess erstellt keine Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="88916-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88916-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="88916-113">See also</span></span>

- [<span data-ttu-id="88916-114">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="88916-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="88916-115">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="88916-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="88916-116">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="88916-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
