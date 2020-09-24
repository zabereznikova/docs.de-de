---
title: 'Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor'
ms.date: 03/30/2017
ms.assetid: ec28332f-9f3c-4e0a-baca-60f9141a68c0
ms.openlocfilehash: 5e61acc9de1ef2f00d5e81a3c3080a9dc46f074d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147696"
---
# <a name="how-to-customize-entity-classes-by-using-the-code-editor"></a><span data-ttu-id="b026e-102">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="b026e-102">How to: Customize Entity Classes by Using the Code Editor</span></span>

<span data-ttu-id="b026e-103">Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um Ihre Entitäts Klassen zu erstellen oder anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b026e-103">Developers using Visual Studio can use the Object Relational Designer to create or customize their entity classes.</span></span>  
  
 <span data-ttu-id="b026e-104">Sie können auch den Visual Studio-Code-Editor verwenden, um eigenen Zuordnungscode zu schreiben oder Code anzupassen, der bereits generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="b026e-104">You can also use the Visual Studio code editor to write your own mapping code or to customize code that has already been generated.</span></span> <span data-ttu-id="b026e-105">Weitere Informationen finden Sie unter [Attribut basierte Zuordnung](attribute-based-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="b026e-105">For more information, see [Attribute-Based Mapping](attribute-based-mapping.md).</span></span>  
  
 <span data-ttu-id="b026e-106">Die Themen in diesem Abschnitt beschreiben das Anpassen des Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="b026e-106">The topics in this section describe how to customize your object model.</span></span>  
  
 [<span data-ttu-id="b026e-107">Vorgehensweise: Angeben von Datenbanknamen</span><span class="sxs-lookup"><span data-stu-id="b026e-107">How to: Specify Database Names</span></span>](how-to-specify-database-names.md)  
 <span data-ttu-id="b026e-108">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-108">Describes how to use <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-109">Vorgehensweise: Darstellen von Tabellen als Klassen</span><span class="sxs-lookup"><span data-stu-id="b026e-109">How to: Represent Tables as Classes</span></span>](how-to-represent-tables-as-classes.md)  
 <span data-ttu-id="b026e-110">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b026e-110">Describes how to use <xref:System.Data.Linq.Mapping.TableAttribute>.</span></span>  
  
 [<span data-ttu-id="b026e-111">Vorgehensweise: Darstellen von Spalten als Klassenmember</span><span class="sxs-lookup"><span data-stu-id="b026e-111">How to: Represent Columns as Class Members</span></span>](how-to-represent-columns-as-class-members.md)  
 <span data-ttu-id="b026e-112">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b026e-112">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute>.</span></span>  
  
 [<span data-ttu-id="b026e-113">Vorgehensweise: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="b026e-113">How to: Represent Primary Keys</span></span>](how-to-represent-primary-keys.md)  
 <span data-ttu-id="b026e-114">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-114">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-115">Vorgehensweise: Zuordnen von Datenbankbeziehungen</span><span class="sxs-lookup"><span data-stu-id="b026e-115">How to: Map Database Relationships</span></span>](how-to-map-database-relationships.md)  
 <span data-ttu-id="b026e-116">Bietet Beispiele zur Verwendung des <xref:System.Data.Linq.Mapping.AssociationAttribute>-Attributs.</span><span class="sxs-lookup"><span data-stu-id="b026e-116">Provides examples of using the <xref:System.Data.Linq.Mapping.AssociationAttribute> attribute.</span></span>  
  
 [<span data-ttu-id="b026e-117">Vorgehensweise: Darstellen von Spalten als datenbankgeneriert</span><span class="sxs-lookup"><span data-stu-id="b026e-117">How to: Represent Columns as Database-Generated</span></span>](how-to-represent-columns-as-database-generated.md)  
 <span data-ttu-id="b026e-118">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-118">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-119">Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="b026e-119">How to: Represent Columns as Timestamp or Version Columns</span></span>](how-to-represent-columns-as-timestamp-or-version-columns.md)  
 <span data-ttu-id="b026e-120">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-120">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-121">Vorgehensweise: Angeben von Datenbankdatentypen</span><span class="sxs-lookup"><span data-stu-id="b026e-121">How to: Specify Database Data Types</span></span>](how-to-specify-database-data-types.md)  
 <span data-ttu-id="b026e-122">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-122">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-123">Vorgehensweise: Darstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="b026e-123">How to: Represent Computed Columns</span></span>](how-to-represent-computed-columns.md)  
 <span data-ttu-id="b026e-124">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-124">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-125">Vorgehensweise: Angeben von privaten Speicherfeldern</span><span class="sxs-lookup"><span data-stu-id="b026e-125">How to: Specify Private Storage Fields</span></span>](how-to-specify-private-storage-fields.md)  
 <span data-ttu-id="b026e-126">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-126">Describes how to use <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-127">Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="b026e-127">How to: Represent Columns as Allowing Null Values</span></span>](how-to-represent-columns-as-allowing-null-values.md)  
 <span data-ttu-id="b026e-128">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-128">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
 [<span data-ttu-id="b026e-129">Vorgehensweise: Zuordnen von Vererbungshierarchien</span><span class="sxs-lookup"><span data-stu-id="b026e-129">How to: Map Inheritance Hierarchies</span></span>](how-to-map-inheritance-hierarchies.md)  
 <span data-ttu-id="b026e-130">Beschreibt die erforderlichen Zuordnungen für das Definieren einer Vererbungshierarchie.</span><span class="sxs-lookup"><span data-stu-id="b026e-130">Describes the mappings required to specify an inheritance hierarchy.</span></span>  
  
 [<span data-ttu-id="b026e-131">Vorgehensweise: Angeben von Parallelitätskonfliktüberprüfungen</span><span class="sxs-lookup"><span data-stu-id="b026e-131">How to: Specify Concurrency-Conflict Checking</span></span>](how-to-specify-concurrency-conflict-checking.md)  
 <span data-ttu-id="b026e-132">Beschreibt die Verwendung von <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="b026e-132">Describes how to use <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b026e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b026e-133">See also</span></span>

- [<span data-ttu-id="b026e-134">SqlMetal.exe (Tool zur Codegenerierung)</span><span class="sxs-lookup"><span data-stu-id="b026e-134">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
