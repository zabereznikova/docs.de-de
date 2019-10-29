---
title: Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 138fbbc3ccaa90096a15fa87544e5c29f66beb08
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040064"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="3f7e1-102">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="3f7e1-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="3f7e1-103">Ein Schema kann eine **msdata: Relationship** -Anmerkung enthalten, um die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="3f7e1-104">Die beiden in **msdata: Relationship** angegebenen Elemente können im Schema, jedoch nicht vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="3f7e1-105">Der Mapping-Prozess verwendet **msdata: Relationship** im Schema, um die PRIMARY KEY/Foreign Key-Beziehung zwischen den beiden Spalten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="3f7e1-106">Das folgende Beispiel zeigt ein XML-Schema, in dem das **OrderDetail** -Element ein untergeordnetes Element der **Order**-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="3f7e1-107">Die **msdata: Relationship** identifiziert diese Beziehung zwischen über-und untergeordneten Elementen und gibt an, dass die **OrderNumber** -Spalte der resultierenden **Order** -Tabelle mit der **OrderNo** -Spalte der resultierenden **OrderDetail** -Tabelle verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="3f7e1-108">Durch den XML-Schemazuordnungsprozess werden im <xref:System.Data.DataSet> folgende Elemente erstellt:</span><span class="sxs-lookup"><span data-stu-id="3f7e1-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="3f7e1-109">Eine **Bestellung** und eine **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="3f7e1-110">Eine Beziehung zwischen der **Order** -Tabelle und der **Order Detail** -Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="3f7e1-111">Die Eigenschaft " **schsted** " für diese Beziehung wird auf " **true** " festgelegt, da die Elemente **Order** und **Order Detail** im Schema scht sind.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="3f7e1-112">Der Zuordnungsprozess erstellt keine Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="3f7e1-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f7e1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f7e1-113">See also</span></span>

- [<span data-ttu-id="3f7e1-114">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3f7e1-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="3f7e1-115">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3f7e1-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="3f7e1-116">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3f7e1-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
