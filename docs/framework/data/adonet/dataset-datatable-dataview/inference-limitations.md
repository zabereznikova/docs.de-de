---
title: Rückschlusseinschränkungen
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: d113df98cdd339300b3e75ceda49a56d4f346d3c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44190677"
---
# <a name="inference-limitations"></a><span data-ttu-id="9aaa4-102">Rückschlusseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="9aaa4-102">Inference Limitations</span></span>
<span data-ttu-id="9aaa4-103">Beim Herleiten eines <xref:System.Data.DataSet>-Schemas aus XML können sich in Abhängigkeit von den XML-Elementen jedes Dokuments verschiedene Schemata ergeben.</span><span class="sxs-lookup"><span data-stu-id="9aaa4-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="9aaa4-104">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="9aaa4-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="9aaa4-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="9aaa4-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="9aaa4-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="9aaa4-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="9aaa4-107">Für "Document1" die Herleitung ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.</span><span class="sxs-lookup"><span data-stu-id="9aaa4-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="9aaa4-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="9aaa4-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="9aaa4-109">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="9aaa4-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="9aaa4-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="9aaa4-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="9aaa4-111">Text1</span><span class="sxs-lookup"><span data-stu-id="9aaa4-111">Text1</span></span>|  
|<span data-ttu-id="9aaa4-112">Text2</span><span class="sxs-lookup"><span data-stu-id="9aaa4-112">Text2</span></span>|  
  
 <span data-ttu-id="9aaa4-113">Allerdings für "Document2" die Herleitung ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="9aaa4-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="9aaa4-114">"Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.</span><span class="sxs-lookup"><span data-stu-id="9aaa4-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="9aaa4-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="9aaa4-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="9aaa4-116">**Tabelle:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="9aaa4-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="9aaa4-117">Element1</span><span class="sxs-lookup"><span data-stu-id="9aaa4-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="9aaa4-118">Text1</span><span class="sxs-lookup"><span data-stu-id="9aaa4-118">Text1</span></span>|  
  
 <span data-ttu-id="9aaa4-119">Es war möglicherweise beabsichtigt, dass sich für beide XML-Dokumente dasselbe XML-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="9aaa4-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="9aaa4-120">Zur Vermeidung von abweichungen, die beim Generieren von Schemas aus einem XML-Dokument auftreten können, wird empfohlen, dass Sie explizit, ein Schema angeben (XSD) XML Schema Definition Language oder XML-Data Reduced (XDR) verwenden, beim Laden einer **DataSet** aus XML-CODE.</span><span class="sxs-lookup"><span data-stu-id="9aaa4-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="9aaa4-121">Weitere Informationen zum expliziten Angeben einer **DataSet** Schemas mit XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="9aaa4-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aaa4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9aaa4-122">See Also</span></span>  
 [<span data-ttu-id="9aaa4-123">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="9aaa4-123">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="9aaa4-124">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="9aaa4-124">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="9aaa4-125">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="9aaa4-125">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="9aaa4-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="9aaa4-126">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="9aaa4-127">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="9aaa4-127">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="9aaa4-128">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="9aaa4-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
