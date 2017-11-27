---
title: "Hinzufügen einer \"DataTable\" zu einem \"DataSet\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f70292794866530de5b7abf7dac1edd09d300c94
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="ce7d9-102">Hinzufügen einer "DataTable" zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="ce7d9-102">Adding a DataTable to a DataSet</span></span>
<span data-ttu-id="ce7d9-103">Mit ADO.NET können Sie <xref:System.Data.DataTable>-Objekte erstellen und diese zu einem vorhandenen <xref:System.Data.DataSet> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-103">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ce7d9-104">Mit der <xref:System.Data.DataTable>-Eigenschaft und der <xref:System.Data.DataTable.PrimaryKey%2A>-Eigenschaft können Sie Einschränkungsinformationen für eine <xref:System.Data.DataColumn.Unique%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-104">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce7d9-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce7d9-105">Example</span></span>  
 <span data-ttu-id="ce7d9-106">Im folgenden Beispiel wird ein <xref:System.Data.DataSet> erstellt und dem <xref:System.Data.DataTable> ein neues <xref:System.Data.DataSet>-Objekt hinzugefügt. Anschließend werden der Tabelle drei <xref:System.Data.DataColumn>-Objekte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-106">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="ce7d9-107">Zum Schluss wird durch den Code eine Spalte als Primärschlüsselspalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-107">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="ce7d9-108">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="ce7d9-108">Case Sensitivity</span></span>  
 <span data-ttu-id="ce7d9-109">Ein <xref:System.Data.DataSet> kann zwei oder mehr Tabellen oder Beziehungen mit demselben Namen, aber unterschiedlicher Schreibweise enthalten.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-109">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ce7d9-110">In solchen Fällen muss in Verweisen auf Namen von Tabellen oder Beziehungen die Groß- und Kleinschreibung berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-110">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="ce7d9-111">Beispielsweise, wenn die <xref:System.Data.DataSet> **DataSet** enthält Tabellen **Table1** und **table1**, würden Sie verweisen **Table1** anhand des Namens **dataSet.Tables["Table1"]**, und **table1** als **dataSet.Tables["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-111">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="ce7d9-112">Versuch, auf eine der Tabellen als verweisen **dataSet.Tables["TABLE1"]** würde eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-112">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="ce7d9-113">Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn nur eine Tabelle oder Beziehung einen bestimmten Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-113">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="ce7d9-114">Z. B. wenn die <xref:System.Data.DataSet> hat nur **Table1**, Sie können darauf verweisen **dataSet.Tables["TABLE1"]**.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-114">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce7d9-115">Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft des <xref:System.Data.DataSet> hat keine Auswirkungen auf dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-115">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="ce7d9-116">Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft gilt für die Daten im <xref:System.Data.DataSet> und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen, usw.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="ce7d9-117">Unterstützte Namespaces</span><span class="sxs-lookup"><span data-stu-id="ce7d9-117">Namespace Support</span></span>  
 <span data-ttu-id="ce7d9-118">Vor ADO.NET 2.0 konnten zwei Tabellen nicht den gleichen Namen haben, selbst wenn sie sich in unterschiedlichen Namespaces befanden.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-118">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="ce7d9-119">Diese Einschränkung wurde in ADO.NET 2.0 aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-119">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="ce7d9-120">Ein <xref:System.Data.DataSet> kann zwei Tabellen enthalten, die den gleichen <xref:System.Data.DataTable.TableName%2A>-Eigenschaftswert, aber unterschiedliche <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ce7d9-120">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7d9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce7d9-121">See Also</span></span>  
 [<span data-ttu-id="ce7d9-122">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="ce7d9-122">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="ce7d9-123">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ce7d9-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
