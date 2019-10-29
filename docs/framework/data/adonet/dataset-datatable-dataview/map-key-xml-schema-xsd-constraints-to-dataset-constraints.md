---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 670c07dd83e880b79c1ccf0c5af00d253b83f827
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040080"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="50a9b-102">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50a9b-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="50a9b-103">In einem Schema können Sie eine Schlüssel Einschränkung für ein Element oder Attribut mit dem **Schlüssel** Element angeben.</span><span class="sxs-lookup"><span data-stu-id="50a9b-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="50a9b-104">Das Element oder Attribut, für das Sie eine Schlüsseleinschränkung angeben, muss eindeutige Werte in jeder Schemainstanz aufweisen und darf keine NULL-Werte enthalten.</span><span class="sxs-lookup"><span data-stu-id="50a9b-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="50a9b-105">Die Schlüsseleinschränkung ist der unique-Einschränkung ähnlich, außer dass die Spalte, für die eine Schlüsseleinschränkung definiert wird, keine NULL-Werte enthalten darf.</span><span class="sxs-lookup"><span data-stu-id="50a9b-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="50a9b-106">In der folgenden Tabelle werden die **msdata** -Attribute aufgelistet, die Sie im **Key** -Element angeben können.</span><span class="sxs-lookup"><span data-stu-id="50a9b-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="50a9b-107">Attributname</span><span class="sxs-lookup"><span data-stu-id="50a9b-107">Attribute name</span></span>|<span data-ttu-id="50a9b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50a9b-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="50a9b-109">**msdata: einschränintname**</span><span class="sxs-lookup"><span data-stu-id="50a9b-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="50a9b-110">Wenn dieses Attribut angegeben ist, wird dessen Wert als Einschränkungsname verwendet.</span><span class="sxs-lookup"><span data-stu-id="50a9b-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="50a9b-111">Andernfalls stellt das **Name** -Attribut den Wert des Einschränkungs namens bereit.</span><span class="sxs-lookup"><span data-stu-id="50a9b-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="50a9b-112">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="50a9b-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="50a9b-113">Wenn `PrimaryKey="true"` vorhanden ist, wird die **IsPrimaryKey** -Einschränkungs Eigenschaft auf **true**festgelegt und somit als Primärschlüssel festgelegt.</span><span class="sxs-lookup"><span data-stu-id="50a9b-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="50a9b-114">Die **AllowDBNull** -Spalten Eigenschaft ist auf **false**festgelegt, da Primärschlüssel keine NULL-Werte aufweisen können.</span><span class="sxs-lookup"><span data-stu-id="50a9b-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="50a9b-115">Beim Umrechnen eines Schemas, in dem eine Schlüssel Einschränkung angegeben ist, erstellt der Zustellungs Prozess eine Unique-Einschränkung für die Tabelle, bei der die **AllowDBNull** -Spalten Eigenschaft für jede Spalte in der Einschränkung auf **false** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="50a9b-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="50a9b-116">Die **IsPrimaryKey** -Eigenschaft der Unique-Einschränkung ist auch auf **false** festgelegt, es sei denn, Sie haben `msdata:PrimaryKey="true"` für das **Key** -Element angegeben.</span><span class="sxs-lookup"><span data-stu-id="50a9b-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="50a9b-117">Dies ist mit einer unique-Einschränkung im Schema mit `PrimaryKey="true"` identisch.</span><span class="sxs-lookup"><span data-stu-id="50a9b-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="50a9b-118">Im folgenden Schema Beispiel gibt das **Key** -Element die Schlüssel Einschränkung für das **CustomerID-** Element an.</span><span class="sxs-lookup"><span data-stu-id="50a9b-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="50a9b-119">Das **Key** -Element gibt an, dass die Werte des untergeordneten **CustomerID-** Elements des **Customers** -Elements eindeutige Werte aufweisen müssen und keine NULL-Werte aufweisen dürfen.</span><span class="sxs-lookup"><span data-stu-id="50a9b-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="50a9b-120">Beim Übertragen des XSD-Schemas (XML Schema Definition Language) wird vom Zuordnungsprozess die folgende Tabelle erstellt:</span><span class="sxs-lookup"><span data-stu-id="50a9b-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="50a9b-121">Die XML-Schema Zuordnung erstellt auch ein **UniqueConstraint** -Element für die **CustomerID-** Spalte, wie im folgenden <xref:System.Data.DataSet>gezeigt.</span><span class="sxs-lookup"><span data-stu-id="50a9b-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="50a9b-122">(Zur Vereinfachung werden nur relevante Eigenschaften gezeigt.)</span><span class="sxs-lookup"><span data-stu-id="50a9b-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="50a9b-123">Im generierten **DataSet** ist die **IsPrimaryKey** -Eigenschaft von **UniqueConstraint** auf **true** festgelegt, da das Schema `msdata:PrimaryKey="true"` im **Key** -Element angibt.</span><span class="sxs-lookup"><span data-stu-id="50a9b-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="50a9b-124">Der Wert der Eigenschaft " **Einschränkungs Name** " der **UniqueConstraint** im **DataSet** ist der Wert des Attributs " **msdata: Einschränkungs Name** ", das im **Key** -Element im Schema angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="50a9b-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50a9b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50a9b-125">See also</span></span>

- [<span data-ttu-id="50a9b-126">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="50a9b-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="50a9b-127">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="50a9b-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="50a9b-128">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="50a9b-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
