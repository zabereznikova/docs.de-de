---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8aed9830d613eeb7d49d2339a8ac1892c0e28e93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761167"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="3e88e-102">Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3e88e-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="3e88e-103">In einem Schema Definition Language (XSD) XML-Schema der **eindeutige** Element gibt die eindeutigkeitseinschränkung für ein Element oder Attribut an.</span><span class="sxs-lookup"><span data-stu-id="3e88e-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="3e88e-104">	Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3e88e-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="3e88e-105">Die folgende Tabelle enthält die **Msdata** Attribute, die Sie, in angeben können der **eindeutige** Element.</span><span class="sxs-lookup"><span data-stu-id="3e88e-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="3e88e-106">Attributname</span><span class="sxs-lookup"><span data-stu-id="3e88e-106">Attribute name</span></span>|<span data-ttu-id="3e88e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e88e-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="3e88e-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="3e88e-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="3e88e-109">Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.</span><span class="sxs-lookup"><span data-stu-id="3e88e-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="3e88e-110">Andernfalls die **Namen** Attribut den Wert des Einschränkungsnamen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3e88e-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="3e88e-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="3e88e-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="3e88e-112">Wenn `PrimaryKey="true"` ist vorhanden, in der **eindeutige** Element, eine unique-Einschränkung wird erstellt, mit der **IsPrimaryKey** -Eigenschaftensatz auf **"true"**.</span><span class="sxs-lookup"><span data-stu-id="3e88e-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="3e88e-113">Das folgende Beispiel zeigt eine XML-Schema, verwendet der **eindeutige** Element, um eine Unique-Einschränkung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3e88e-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="3e88e-114">Die **eindeutige** -Element im Schema gibt an, dass für alle **Kunden** Instanz Elemente in einem Dokument, die den Wert des der **CustomerID** untergeordnetes Element muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="3e88e-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="3e88e-115">Im Gebäude der **DataSet**, der Zuordnungsprozess dieses Schema liest und in der folgenden Tabelle generiert:</span><span class="sxs-lookup"><span data-stu-id="3e88e-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="3e88e-116">Der Zuordnungsprozess erstellt auch eine unique-Einschränkung für die **CustomerID** Spalte, wie im folgenden gezeigt **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="3e88e-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="3e88e-117">(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="3e88e-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="3e88e-118">In der **DataSet** , das generiert wird, die **IsPrimaryKey** -Eigenschaftensatz auf **"false"** für die unique-Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="3e88e-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="3e88e-119">Die **eindeutige** Eigenschaft für die Spalte gibt an, dass die **CustomerID** Spaltenwerte müssen eindeutig sein (kann ein null-Verweis, entsprechend den Angaben von werden jedoch die **AllowDBNull** -Eigenschaft der Spalte).</span><span class="sxs-lookup"><span data-stu-id="3e88e-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="3e88e-120">Wenn Sie das Schema ändern, und legen Sie den optionalen **msdata: PrimaryKey** -Attributwert **"true"**, die unique-Einschränkung für die Tabelle erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3e88e-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="3e88e-121">Die **AllowDBNull** -Spalteneigenschaft ist auf **"false"**, und die **IsPrimaryKey** Eigenschaft der Einschränkung auf **"true"** damit die **CustomerID** Spalte eine primäre Schlüsselspalte.</span><span class="sxs-lookup"><span data-stu-id="3e88e-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="3e88e-122">Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="3e88e-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="3e88e-123">Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass eine Kombination von **CustomerID** und **CompanyName** Werte müssen für alle eindeutig sein **Kunden** in einer beliebigen Instanz von Hinzufügen von einem anderen **xs: field** -Element im Schema.</span><span class="sxs-lookup"><span data-stu-id="3e88e-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="3e88e-124">Dies ist die Einschränkung, die in der resultierenden erstellt wird **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="3e88e-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e88e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e88e-125">See Also</span></span>  
 [<span data-ttu-id="3e88e-126">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="3e88e-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="3e88e-127">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="3e88e-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="3e88e-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3e88e-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
