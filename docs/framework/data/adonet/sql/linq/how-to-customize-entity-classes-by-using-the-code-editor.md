---
title: "Gewusst wie: Anpassen von Entitätsklassen mit dem Code-Editor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0bb8f0e7116c1a2e0856ca72b618eb6607a654be
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="2cc18-102">Gewusst wie: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="2cc18-102">How to: Customize Entity Classes by Using the Code Editor</span></span>
<span data-ttu-id="2cc18-103">Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, können den [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] verwenden, um Entitätsklassen zu erstellen oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2cc18-103">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="2cc18-104">Sie können auch den [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)]-Code-Editor verwenden, um eigenen Zuordnungscode zu schreiben oder bereits erzeugten Code anzupassen.</span><span class="sxs-lookup"><span data-stu-id="2cc18-104">You can also use the [!INCLUDE[vsprvs](../../../../../../includes/vsprvs-md.md)] code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="2cc18-105">Weitere Informationen finden Sie unter [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2cc18-105">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="2cc18-106">Die Themen in diesem Abschnitt beschreiben das Anpassen des Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="2cc18-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="2cc18-107">Vorgehensweise: Angeben von Datenbanknamen</span><span class="sxs-lookup"><span data-stu-id="2cc18-107">How to: Specify Database Names</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-names.md)  
 <span data-ttu-id="2cc18-108">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-109">Vorgehensweise: Darstellen von Tabellen als Klassen</span><span class="sxs-lookup"><span data-stu-id="2cc18-109">How to: Represent Tables as Classes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="2cc18-110">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="2cc18-111">: Darstellen von Spalten als Klassenmember</span><span class="sxs-lookup"><span data-stu-id="2cc18-111">How to: Represent Columns as Class Members</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="2cc18-112">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="2cc18-113">Vorgehensweise: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="2cc18-113">How to: Represent Primary Keys</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-primary-keys.md)  
 <span data-ttu-id="2cc18-114">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-115">Vorgehensweise: Zuordnen von Datenbankbeziehungen</span><span class="sxs-lookup"><span data-stu-id="2cc18-115">How to: Map Database Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md)  
 <span data-ttu-id="2cc18-116">Bietet Beispiele zur Verwendung des <xref:System.Data.Linq.Mapping.AssociationAttribute>-Attributs.</span><span class="sxs-lookup"><span data-stu-id="2cc18-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="2cc18-117">Vorgehensweise: Darstellen von Spalten als datenbankgeneriert</span><span class="sxs-lookup"><span data-stu-id="2cc18-117">How to: Represent Columns as Database-Generated</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="2cc18-118">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-119">Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="2cc18-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="2cc18-120">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-121">Vorgehensweise: Angeben von Datenbankdatentypen</span><span class="sxs-lookup"><span data-stu-id="2cc18-121">How to: Specify Database Data Types</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-database-data-types.md)  
 <span data-ttu-id="2cc18-122">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-123">Vorgehensweise: Darstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="2cc18-123">How to: Represent Computed Columns</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-computed-columns.md)  
 <span data-ttu-id="2cc18-124">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-125">Vorgehensweise: Angeben von privaten Speicherfeldern</span><span class="sxs-lookup"><span data-stu-id="2cc18-125">How to: Specify Private Storage Fields</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="2cc18-126">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-127">Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="2cc18-127">How to: Represent Columns as Allowing Null Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="2cc18-128">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="2cc18-129">Vorgehensweise: Zuordnen von Vererbungshierarchien</span><span class="sxs-lookup"><span data-stu-id="2cc18-129">How to: Map Inheritance Hierarchies</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="2cc18-130">Beschreibt die erforderlichen Zuordnungen für das Definieren einer Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="2cc18-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="2cc18-131">: Angeben von Parallelitätskonfliktüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="2cc18-131">How to: Specify Concurrency-Conflict Checking</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="2cc18-132">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="2cc18-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc18-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cc18-133">See Also</span></span>  
 [<span data-ttu-id="2cc18-134">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="2cc18-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
