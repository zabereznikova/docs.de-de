---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: eb4f6e3a63c901ec69ca5572a6f79d2f0ac4adfc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="11ceb-102">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="11ceb-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="11ceb-103">Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="11ceb-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="11ceb-104">Im Allgemeinen wird für jede `complexType` untergeordnetes Element eines Schemaelements eine Tabelle wird generiert, der `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="11ceb-105">Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="11ceb-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="11ceb-106">Tabellen werden erstellt, der `DataSet` für Elemente der obersten Ebene im Schema.</span><span class="sxs-lookup"><span data-stu-id="11ceb-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="11ceb-107">Allerdings wird eine Tabelle nur für ein auf oberster Ebene erstellt `complexType` Element bei der `complexType` in einem anderen Element geschachtelt ist `complexType` Element, in dem Fall wird das geschachtelte `complexType` Element zugeordnet ist ein `DataTable` innerhalb der `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="11ceb-108">Weitere Informationen zu XSD finden Sie unter der World Wide Web Consortium (W3C) XML Schema Part 0: Primer Empfehlung, die XML Schema Part 1: Strukturempfehlung und die XML Schema Part 2: Datatypes Recommendation, am [http:// www.w3.org/](http://www.w3.org/TR/).</span><span class="sxs-lookup"><span data-stu-id="11ceb-108">For more information about the XSD, see the World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, the XML Schema Part 1: Structures Recommendation, and the XML Schema Part 2: Datatypes Recommendation, located at [http://www.w3.org/](http://www.w3.org/TR/).</span></span>  
  
 <span data-ttu-id="11ceb-109">Das folgende Beispiel zeigt ein XML-Schema, in dem `customers` ist das untergeordnete Element von der `MyDataSet` Elements, d. h. eine **DataSet** Element.</span><span class="sxs-lookup"><span data-stu-id="11ceb-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="11ceb-110">Im vorherigen Beispiel ist das `customers`-Element ein Element mit komplexem Typ.</span><span class="sxs-lookup"><span data-stu-id="11ceb-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="11ceb-111">Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="11ceb-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="11ceb-112">Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="11ceb-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11ceb-113">Wenn das Element `customers` eines einfachen Datentyps von XML-Schema handelt, z. B. **Ganzzahl**, keine Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="11ceb-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="11ceb-114">Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="11ceb-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="11ceb-115">Im folgenden XML-Schema das **Schema** Element verfügt über zwei untergeordneten Elemente auf: `InStateCustomers` und `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="11ceb-116">Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="11ceb-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="11ceb-117">Der Zuordnungsvorgang generiert daher die folgenden zwei identischen Tabellen in der `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="11ceb-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="11ceb-118">In This Section</span></span>  
 [<span data-ttu-id="11ceb-119">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="11ceb-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="11ceb-120">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Unique- und foreign Key-Einschränkungen in einer `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="11ceb-121">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="11ceb-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="11ceb-122">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Beziehungen zwischen Tabellenspalten in einer `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="11ceb-123">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="11ceb-123">XML Schema Constraints and Relationships</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="11ceb-124">Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schemaelementen Einschränkungen in einer `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="11ceb-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11ceb-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="11ceb-125">Related Sections</span></span>  
 [<span data-ttu-id="11ceb-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="11ceb-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 <span data-ttu-id="11ceb-127">Beschreibt, wie geladen und beibehalten, die relationale Struktur und die Daten in einem `DataSet` als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="11ceb-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ceb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11ceb-128">See Also</span></span>  
 [<span data-ttu-id="11ceb-129">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="11ceb-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
