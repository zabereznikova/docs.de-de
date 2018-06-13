---
title: Rückschlusseinschränkungen
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: b3ad1e66a6a1a4cb2a2aab7b2f86f38e5c784876
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32760049"
---
# <a name="inference-limitations"></a><span data-ttu-id="f1e26-102">Rückschlusseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="f1e26-102">Inference Limitations</span></span>
<span data-ttu-id="f1e26-103">Beim Herleiten eines <xref:System.Data.DataSet>-Schemas aus XML können sich in Abhängigkeit von den XML-Elementen jedes Dokuments verschiedene Schemata ergeben.</span><span class="sxs-lookup"><span data-stu-id="f1e26-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="f1e26-104">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="f1e26-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="f1e26-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="f1e26-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f1e26-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="f1e26-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f1e26-107">Für "Document1" die Herleitung ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.</span><span class="sxs-lookup"><span data-stu-id="f1e26-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="f1e26-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f1e26-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f1e26-109">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="f1e26-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f1e26-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f1e26-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="f1e26-111">Text1</span><span class="sxs-lookup"><span data-stu-id="f1e26-111">Text1</span></span>|  
|<span data-ttu-id="f1e26-112">Text2</span><span class="sxs-lookup"><span data-stu-id="f1e26-112">Text2</span></span>|  
  
 <span data-ttu-id="f1e26-113">Allerdings für "" document2"," die Herleitung ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="f1e26-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="f1e26-114">"Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.</span><span class="sxs-lookup"><span data-stu-id="f1e26-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="f1e26-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="f1e26-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="f1e26-116">**Table:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f1e26-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="f1e26-117">Element1</span><span class="sxs-lookup"><span data-stu-id="f1e26-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="f1e26-118">Text1</span><span class="sxs-lookup"><span data-stu-id="f1e26-118">Text1</span></span>|  
  
 <span data-ttu-id="f1e26-119">Es war möglicherweise beabsichtigt, dass sich für beide XML-Dokumente dasselbe XML-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="f1e26-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="f1e26-120">Zur Vermeidung von abweichungen, die auftreten können, wenn das Schema aus einem XML-Dokument generieren, wird empfohlen, dass Sie explizit ein Schema, das beim Laden von XML-Schemadefinitionssprache (XSD) oder XML-Data Reduced (XDR) verwenden eine **DataSet** aus XML-DATEI.</span><span class="sxs-lookup"><span data-stu-id="f1e26-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="f1e26-121">Weitere Informationen zum expliziten Angeben einer **DataSet** Schemas mit XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="f1e26-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e26-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e26-122">See Also</span></span>  
 [<span data-ttu-id="f1e26-123">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="f1e26-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="f1e26-124">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="f1e26-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="f1e26-125">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="f1e26-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="f1e26-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="f1e26-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="f1e26-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="f1e26-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="f1e26-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f1e26-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
