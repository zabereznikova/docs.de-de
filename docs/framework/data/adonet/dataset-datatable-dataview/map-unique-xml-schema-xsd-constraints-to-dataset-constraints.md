---
title: Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150843"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="1bc29-102">Zuordnen von eindeutigen XML Schema (XSD)-Einschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1bc29-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="1bc29-103">In einem XML-Schema für die Schemadefinitionssprache (XSD) gibt das **eindeutige** Element die Eindeutigkeitseinschränkung für ein Element oder Attribut an.</span><span class="sxs-lookup"><span data-stu-id="1bc29-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="1bc29-104">	Beim Übersetzen eines XML-Schemas in ein relationales Schema wird die im XML-Schema für ein Element oder Attribut angegebene eindeutige Einschränkung einer eindeutigen Einschränkung in der <xref:System.Data.DataTable> des entsprechenden <xref:System.Data.DataSet> zugeordnet, das erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1bc29-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="1bc29-105">In der folgenden Tabelle werden die **msdata-Attribute** beschrieben, die Sie im **eindeutigen** Element angeben können.</span><span class="sxs-lookup"><span data-stu-id="1bc29-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="1bc29-106">Attributname</span><span class="sxs-lookup"><span data-stu-id="1bc29-106">Attribute name</span></span>|<span data-ttu-id="1bc29-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bc29-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1bc29-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="1bc29-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="1bc29-109">Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bc29-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="1bc29-110">Andernfalls stellt das **name-Attribut** den Wert des Einschränkungsnamens bereit.</span><span class="sxs-lookup"><span data-stu-id="1bc29-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="1bc29-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="1bc29-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="1bc29-112">Wenn `PrimaryKey="true"` das **eindeutige** Element vorhanden ist, wird eine eindeutige Einschränkung erstellt, wobei die **IsPrimaryKey-Eigenschaft** auf **true**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1bc29-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="1bc29-113">Das folgende Beispiel zeigt ein XML-Schema, das das **eindeutige** Element verwendet, um eine Eindeutigkeitseinschränkung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1bc29-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="1bc29-114">Das **eindeutige** Element im Schema gibt an, dass für alle **Customers-Elemente** in einer Dokumentinstanz der Wert des **untergeordneten CustomerID-Elements** eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="1bc29-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="1bc29-115">Beim Erstellen des **DataSets**liest der Zuordnungsprozess dieses Schema und generiert die folgende Tabelle:</span><span class="sxs-lookup"><span data-stu-id="1bc29-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="1bc29-116">Der Zuordnungsprozess erstellt auch eine eindeutige Einschränkung für die **CustomerID-Spalte,** wie im folgenden **DataSet**gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1bc29-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="1bc29-117">(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="1bc29-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="1bc29-118">Im **generierten DataSet** wird die **IsPrimaryKey-Eigenschaft** für die eindeutige Einschränkung auf **False** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1bc29-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="1bc29-119">Die **eindeutige** Eigenschaft in der Spalte gibt an, dass die **CustomerID-Spaltenwerte** eindeutig sein müssen (sie können jedoch ein Nullverweis sein, wie durch die **AllowDBNull-Eigenschaft** der Spalte angegeben).</span><span class="sxs-lookup"><span data-stu-id="1bc29-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="1bc29-120">Wenn Sie das Schema ändern und den optionalen **msdata:PrimaryKey-Attributwert** auf **True**festlegen, wird die eindeutige Einschränkung für die Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="1bc29-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="1bc29-121">Die **AllowDBNull-Spalteneigenschaft** ist auf **False**festgelegt, und die **IsPrimaryKey-Eigenschaft** der Einschränkung wird auf **True**festgelegt, wodurch die **CustomerID-Spalte** zu einer Primärschlüsselspalte wird.</span><span class="sxs-lookup"><span data-stu-id="1bc29-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="1bc29-122">Sie können eine eindeutige Einschränkung für eine Kombination aus Elementen oder Attributen im XML-Schema angeben.</span><span class="sxs-lookup"><span data-stu-id="1bc29-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="1bc29-123">Im folgenden Beispiel wird veranschaulicht, wie Sie angeben, dass eine Kombination aus **CustomerID-** und **CompanyName-Werten** für alle **Kunden** in jedem Fall eindeutig sein muss, indem Sie ein weiteres **xs:field-Element** im Schema hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1bc29-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="1bc29-124">Dies ist die Einschränkung, die im resultierenden **DataSet**erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="1bc29-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bc29-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bc29-125">See also</span></span>

- [<span data-ttu-id="1bc29-126">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="1bc29-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="1bc29-127">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="1bc29-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="1bc29-128">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1bc29-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
