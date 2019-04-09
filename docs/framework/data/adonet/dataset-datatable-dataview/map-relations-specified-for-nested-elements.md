---
title: Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: 9772f077991c758be65bbb44b9474f1ad341371f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203144"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="1e9b1-102">Zuordnen von Beziehungen, die für geschachtelte Elemente angegeben sind</span><span class="sxs-lookup"><span data-stu-id="1e9b1-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="1e9b1-103">Es kann ein Schema enthalten eine **msdata: Relationship** Anmerkung, die die Zuordnung zwischen zwei beliebigen Elementen im Schema explizit anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="1e9b1-104">Die zwei Elemente im angegebenen **msdata: Relationship** können im Schema geschachtelt werden, aber nicht unbedingt sein.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="1e9b1-105">Der Zuordnungsprozess verwendet **msdata: Relationship** im Schema für die primäre/Fremdschlüssel-Beziehung zwischen den beiden Spalten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="1e9b1-106">Das folgende Beispiel zeigt ein XML-Schema, in dem die **OrderDetail** Element ist ein untergeordnetes Element des **Reihenfolge**.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="1e9b1-107">Die **msdata: Relationship** identifiziert diese über-/ unterordnungsbeziehung und gibt an, dass die **OrderNumber** Spalte des resultierenden **Reihenfolge** Tabelle bezieht sich auf die **OrderNo** Spalte des resultierenden **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="1e9b1-108">Durch den XML-Schemazuordnungsprozess werden im <xref:System.Data.DataSet> folgende Elemente erstellt:</span><span class="sxs-lookup"><span data-stu-id="1e9b1-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
-   <span data-ttu-id="1e9b1-109">Ein **Reihenfolge** und **OrderDetail** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   <span data-ttu-id="1e9b1-110">Eine Beziehung zwischen der **Reihenfolge** und **OrderDetail** Tabellen.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="1e9b1-111">Die **geschachtelte** für diese Beziehung-Eigenschaftensatz auf **"true"** da die **Reihenfolge** und **OrderDetail** Elemente im Schema geschachtelt sind .</span><span class="sxs-lookup"><span data-stu-id="1e9b1-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="1e9b1-112">Der Zuordnungsprozess erstellt keine Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="1e9b1-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e9b1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e9b1-113">See also</span></span>

- [<span data-ttu-id="1e9b1-114">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1e9b1-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="1e9b1-115">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1e9b1-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="1e9b1-116">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1e9b1-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
