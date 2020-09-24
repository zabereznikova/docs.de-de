---
title: Hinzufügen einer "DataTable" zu einem "DataSet"
description: In diesem Beispielcode erfahren Sie, wie Sie Datentabelle erstellen und Sie einem vorhandenen DataSet in ADO.NET hinzufügen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
ms.openlocfilehash: 6a5e3a89870b3959a6ac042b93414694e8a6cc1c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164895"
---
# <a name="adding-a-datatable-to-a-dataset"></a><span data-ttu-id="ea83a-103">Hinzufügen einer "DataTable" zu einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="ea83a-103">Adding a DataTable to a DataSet</span></span>

<span data-ttu-id="ea83a-104">Mit ADO.NET können Sie <xref:System.Data.DataTable>-Objekte erstellen und diese zu einem vorhandenen <xref:System.Data.DataSet> hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea83a-104">ADO.NET enables you to create <xref:System.Data.DataTable> objects and add them to an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ea83a-105">Mit der <xref:System.Data.DataTable>-Eigenschaft und der <xref:System.Data.DataTable.PrimaryKey%2A>-Eigenschaft können Sie Einschränkungsinformationen für eine <xref:System.Data.DataColumn.Unique%2A> festlegen.</span><span class="sxs-lookup"><span data-stu-id="ea83a-105">You can set constraint information for a <xref:System.Data.DataTable> by using the <xref:System.Data.DataTable.PrimaryKey%2A> and <xref:System.Data.DataColumn.Unique%2A> properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea83a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea83a-106">Example</span></span>  

 <span data-ttu-id="ea83a-107">Im folgenden Beispiel wird ein <xref:System.Data.DataSet> erstellt und dem <xref:System.Data.DataTable> ein neues <xref:System.Data.DataSet>-Objekt hinzugefügt. Anschließend werden der Tabelle drei <xref:System.Data.DataColumn>-Objekte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ea83a-107">The following example constructs a <xref:System.Data.DataSet>, adds a new <xref:System.Data.DataTable> object to the <xref:System.Data.DataSet>, and then adds three <xref:System.Data.DataColumn> objects to the table.</span></span> <span data-ttu-id="ea83a-108">Zum Schluss wird durch den Code eine Spalte als Primärschlüsselspalte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ea83a-108">Finally, the code sets one column as the primary key column.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## <a name="case-sensitivity"></a><span data-ttu-id="ea83a-109">Groß- und Kleinschreibung</span><span class="sxs-lookup"><span data-stu-id="ea83a-109">Case Sensitivity</span></span>  

 <span data-ttu-id="ea83a-110">Ein <xref:System.Data.DataSet> kann zwei oder mehr Tabellen oder Beziehungen mit demselben Namen, aber unterschiedlicher Schreibweise enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea83a-110">Two or more tables or relations with the same name, but different casing, can exist in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ea83a-111">In solchen Fällen muss in Verweisen auf Namen von Tabellen oder Beziehungen die Groß- und Kleinschreibung berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea83a-111">In such cases, references by name to tables and relations are case sensitive.</span></span> <span data-ttu-id="ea83a-112">Wenn das Dataset z. b. die <xref:System.Data.DataSet> **dataSet** Tabellen **Table1** und **Table1**enthält, verweisen Sie auf **Table1** by Name als **DataSet. Tables ["table1"]** und **Table1** as **DataSet. Tables ["table1"]**.</span><span class="sxs-lookup"><span data-stu-id="ea83a-112">For example, if the <xref:System.Data.DataSet> **dataSet** contains tables **Table1** and **table1**, you would reference **Table1** by name as **dataSet.Tables["Table1"]**, and **table1** as **dataSet.Tables["table1"]**.</span></span> <span data-ttu-id="ea83a-113">Wenn Sie versuchen, auf eine der Tabellen als **DataSet. Tables ["table1"]** zu verweisen, wird eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="ea83a-113">Attempting to reference either of the tables as **dataSet.Tables["TABLE1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="ea83a-114">Die Groß- und Kleinschreibung muss nicht berücksichtigt werden, wenn nur eine Tabelle oder Beziehung einen bestimmten Namen aufweist.</span><span class="sxs-lookup"><span data-stu-id="ea83a-114">The case-sensitivity behavior does not apply if only one table or relation has a particular name.</span></span> <span data-ttu-id="ea83a-115">Wenn beispielsweise nur über <xref:System.Data.DataSet> **Table1**verfügt, können Sie mithilfe von **DataSet. Tables ["table1"]** darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="ea83a-115">For example, if the <xref:System.Data.DataSet> has only **Table1**, you can reference it using **dataSet.Tables["TABLE1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ea83a-116">Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft des <xref:System.Data.DataSet> hat keine Auswirkungen auf dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="ea83a-116">The <xref:System.Data.DataSet.CaseSensitive%2A> property of the <xref:System.Data.DataSet> does not affect this behavior.</span></span> <span data-ttu-id="ea83a-117">Die <xref:System.Data.DataSet.CaseSensitive%2A>-Eigenschaft gilt für die Daten im <xref:System.Data.DataSet> und hat Auswirkungen auf das Sortieren, Suchen, Filtern, Erzwingen von Einschränkungen, usw.</span><span class="sxs-lookup"><span data-stu-id="ea83a-117">The <xref:System.Data.DataSet.CaseSensitive%2A> property applies to the data in the <xref:System.Data.DataSet> and affects sorting, searching, filtering, enforcing constraints, and so on.</span></span>  
  
## <a name="namespace-support"></a><span data-ttu-id="ea83a-118">Unterstützte Namespaces</span><span class="sxs-lookup"><span data-stu-id="ea83a-118">Namespace Support</span></span>  

 <span data-ttu-id="ea83a-119">Vor ADO.NET 2.0 konnten zwei Tabellen nicht den gleichen Namen haben, selbst wenn sie sich in unterschiedlichen Namespaces befanden.</span><span class="sxs-lookup"><span data-stu-id="ea83a-119">In versions of ADO.NET earlier than 2.0, two tables could not have the same name, even if they were in different namespaces.</span></span> <span data-ttu-id="ea83a-120">Diese Einschränkung wurde in ADO.NET 2.0 aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="ea83a-120">This limitation was removed in ADO.NET 2.0.</span></span> <span data-ttu-id="ea83a-121">Ein <xref:System.Data.DataSet> kann zwei Tabellen enthalten, die den gleichen <xref:System.Data.DataTable.TableName%2A>-Eigenschaftswert, aber unterschiedliche <xref:System.Data.DataTable.Namespace%2A>-Eigenschaftswerte aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ea83a-121">A <xref:System.Data.DataSet> can contain two tables that have the same <xref:System.Data.DataTable.TableName%2A> property value but different <xref:System.Data.DataTable.Namespace%2A> property values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea83a-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea83a-122">See also</span></span>

- [<span data-ttu-id="ea83a-123">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="ea83a-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="ea83a-124">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ea83a-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
